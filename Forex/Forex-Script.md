<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.md4{margin-top: 5px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
</style>


# [<span style="color:black;">Forex Script</span>](Forex.md)
[Basic](Forex-Basic.md) | 
[Concept](Forex-Concept.md) | 
[Script](Forex-Script.md)


<div class="md3"></div>
<a href="#download-data">Download Data</a>


<div class="md1"></div>

## Download Data

#### fxcm_rest.json

	{
		"app-config": {
			"multiThreading": "",
			"createDatabase" : "",
			"debug": "True",
			"access_token": "22e82a9502d5261b2e059b93da6aafd2030bf03a",
			"database" : "sqlserver-server",  
			"threadCount" : "30",
			"threadSleep" : "1",
			"threadNext" : "10",
			"timeFrames" : ["M1", "W1", "D1", "H8", "H6", "H4","H3", "H2", "H1", "m30", "m15", "m5", "m1"],
			"instruments" : ["EUR/USD", "USD/JPY", "GBP/USD", "USD/CHF", "EUR/CHF", "AUD/USD", "USD/CAD", "NZD/USD", "EUR/GBP", "EUR/JPY", "GBP/JPY", "CHF/JPY", "GBP/CHF", "EUR/AUD", "EUR/CAD", "AUD/CAD", "AUD/JPY", "CAD/JPY", "NZD/JPY", "GBP/CAD", "GBP/NZD", "GBP/AUD", "AUD/NZD", "USD/SEK", "EUR/SEK", "EUR/NOK", "USD/NOK", "USD/MXN", "AUD/CHF", "EUR/NZD", "USD/ZAR", "USD/HKD", "ZAR/JPY", "USD/TRY", "EUR/TRY", "NZD/CHF", "CAD/CHF", "NZD/CAD", "TRY/JPY", "USD/CNH", "USOil", "UKOil", "XAU/USD", "XAG/USD"],
			"instruments2" : ["AUS200", "ESP35", "FRA40", "GER30", "HKG33", "JPN225", "NAS100", "SPX500", "UK100", "US30", "Copper", "CHN50", "EUSTX50", "USDOLLAR", "US2000", "SOYF", "NGAS", "USOilSpot", "UKOilSpot", "WHEATF", "CORNF", "Bund","EMBasket", "JPYBasket", "BTC/USD", "BCH/USD", "ETH/USD", "LTC/USD", "XRP/USD", "CryptoMajor", "EOS/USD", "XLM/USD", "ESPORTS", "BIOTECH", "CANNABIS", "FAANG", "CHN.TECH", "CHN.ECOMM", "USEquities"]
		}, 
		"database": {
			"mysql-local": {
				"type":"mysql", 
				"host":"localhost",        
				"user":"root",
				"password":"123456",
				"database":"forex"        
			},
			"mysql-server": {
				"type":"mysql", 
				"host":"localhost",        
				"user":"root",
				"password":"Morteza901773",
				"database":"forex"        
			},
			"postgresql-local": {
				"type":"postgresql", 
				"host":"localhost",        
				"user":"postgres",
				"password":"123456",
				"database":"forex"  
			},
			"postgresql-server": {
				"type":"postgresql", 
				"host":"35.247.34.55",        
				"user":"postgres",
				"password":"Morteza901773",
				"database":"forex"  
			},
			"sqlserver-local": {
				"type":"sqlserver", 
				"host":"localhost",        
				"user":"root",
				"password":"123456",
				"database":"forex"  
			},
			"sqlserver-server": {
				"type":"sqlserver", 
				"host":"34.83.197.33",         
				"user":"sqlserver",
				"password":"Morteza901773",
				"database":"forex"  
			}     
		},     
		"environments": {
			"demo": {
				"trading": "https://api-demo.fxcm.com",
				"port": 443
			},
			"real": {
				"trading": "https://api.fxcm.com",
				"port": 443
			}
		},
		"logpath": "./logfile.txt",
		"_debugLevels": "Levels are (from most to least logging) DEBUG, INFO, WARNING, ERROR, CRITICAL",
		"debugLevel": "ERROR",
		"subscription_lists": "#Determines default subscription list of item updates to listen to",
		"subscription_list": ["Offer","Account","Order","OpenPosition","ClosedPosition", "LeverageProfile","Summary",
			"Properties"]
	}


#### main.py

	from module import forex_module
	import datetime as d
	from datetime import datetime as dt
	import json
	import threading
	import time

	#----- Get and Set variables
	config_file="config/fxcm_rest.json"              
	with open(config_file, 'r') as f:
		CONFIG = json.load(f)
		debug = bool(CONFIG['app-config']['debug'])
		access_token = CONFIG['app-config']['access_token'] 
		database = CONFIG['app-config']['database'] 
		timeFrames = CONFIG['app-config']['timeFrames'] 
		instruments = CONFIG['app-config']['instruments']
		multiThreading = bool(CONFIG['app-config']['multiThreading'])
		threadCount = int(CONFIG['app-config']['threadCount'])
		threadSleep = int(CONFIG['app-config']['threadSleep'])
		threadNext = int(CONFIG['app-config']['threadNext'])
		createDatabase = bool(CONFIG['app-config']['createDatabase'])
	dateFrom = dt.strptime('2002/01/01 00:00:00', '%Y/%m/%d %H:%M:%S')
	dateTo = dt.strptime(str(d.datetime.now().strftime("%Y/%m/%d %H:%M:%S")), '%Y/%m/%d %H:%M:%S')
	fx = forex_module.Forex(access_token, database, debug)
	threadLock = threading.Lock()
	threads = []
	limit = threadCount
	keep=True
	item = 0

	#----- Create Database and tables
	if createDatabase : fx.CreateDatabase(instruments, timeFrames)


	#----- MultiThreading
	if multiThreading :        
		#Create threads
		for timeFrame in timeFrames: 
			for instrument in instruments:         
				threads.append([threading.Thread(name=f"{instrument}_{timeFrame}", target=fx.Update, args=(instrument, timeFrame, dateFrom, dateTo, )), False])
				if debug : print(f"Thread {instrument}_{timeFrame} Created")
		#Run threads
		fx.Open()    
		while keep:
			if threadCount ==0 : time.sleep(2*threadNext)
			for x in range(threadCount):             
				time.sleep(threadSleep)     
				threads[item][0].start()
				threads[item][1] = True                        
				if debug : print(f"Thread {threads[item][0].name} Started ...")
				item +=1
			time.sleep(threadNext)        
			itemAlive = 0
			alive = 0        
			for tread in threads:
				if tread[1]==True  and  tread[0].is_alive() :
					itemAlive +=1
				alive +=1       
				if alive >= item : break 
			threadCount = limit - itemAlive

		fx.Close()    

	#----- Without MultiThreading
	if multiThreading !=True : 
		fx.Open() 
		for timeFrame in timeFrames:         
			for instrument in instruments: 
				fx.Update(instrument, timeFrame, dateFrom, dateTo)
		fx.Close()	

#### database_module.py

	import mysql.connector
	import psycopg2
	import pyodbc 
	import json

	class Database:      
		def __init__(self, db_instanc, verbose):
			self.verbose = verbose
			config_file="config/fxcm_rest.json"              
			with open(config_file, 'r') as f:
				CONFIG = json.load(f)
				self.type=CONFIG['database'][db_instanc]['type'] 
				self.host=CONFIG['database'][db_instanc]['host']
				self.user=CONFIG['database'][db_instanc]['user']
				self.password=CONFIG['database'][db_instanc]['password']
				self.database=CONFIG['database'][db_instanc]['database']
			if self.type=="mysql": self.db = Mysql(self.host, self.user, self.password, self.database, self.verbose)
			if self.type=="postgresql": self.db = Postgresql(self.host, self.user, self.password, self.database, self.verbose)
			if self.type=="sqlserver": self.db = Sqlserver(self.host, self.user, self.password, self.database, self.verbose)
		def Open(self): self.db.Open()        
		def Close(self): self.db.Close()   
		def Execute(self, command): self.db.Execute(command)          
		def GetDataOne(self, command): return self.db.GetDataOne(command)        
		def DropDatabase(self, dbName): self.db.DropDatabase(dbName)   
		def CreateDatabase(self, dbName): self.db.CreateDatabase(dbName)  
		def CreateTable(self, tbType, dbName, tbName): self.db.CreateTable(tbType, dbName, tbName)
		def GetLastDate(self, tbType, dbName, tbName): return self.db.GetLastDate(tbType, dbName, tbName)
		def Insert(self, tbType, dbName, tbName, value): return self.db.Insert(tbType, dbName, tbName, value)    
		def InsertBulk(self, tbType, dbName, tbName, value): return self.db.InsertBulk(tbType, dbName, tbName, value) 




	class Mysql:      
		def __init__(self, host,user, password, database, verbose):      
				self.host=host
				self.user=user
				self.password=password
				self.database=database 
				self.verbose=verbose
		def Open(self):            
			self.connection = mysql.connector.connect(host=self.host, user=self.user, password=self.password)
			self.connection.autocommit=True          
			self.cursor = self.connection.cursor() 
		def Close(self):        
			self.cursor.close()
			self.connection.close()  
		def Execute(self, cmd):        
			self.cursor.execute(cmd)                                                        
		def GetDataOne(self, cmd):        
			self.cursor.execute(cmd)                                                        
			return self.cursor.fetchone()
		def GetLastDate(self, tbType, dbName, tbName): 
			return self.GetDataOne(f"SELECT max(date) FROM `{dbName}`.`{tbName}`")
		def DropDatabase(self,dbName): 
			self.Open()
			self.Execute(f"DROP DATABASE IF EXISTS {dbName};")
			self.Close()
			if self.verbose : print(f"Database {dbName} Droped")        
		def CreateDatabase(self,dbName): 
			self.Open()
			self.Execute(f"CREATE DATABASE IF NOT EXISTS {dbName};")
			self.Close()
			if self.verbose : print(f"Database {dbName} Createded")
		def CreateTable(self, tbType, dbName, tbName):                    
			if tbType == "tick": self.Execute(f"CREATE TABLE IF NOT EXISTS `{dbName}`.`{tbName}` (`id` int unsigned NOT NULL AUTO_INCREMENT,`date` datetime NOT NULL,`bid` float NOT NULL,`ask` float NOT NULL,`high` float NOT NULL,`low` float NOT NULL,PRIMARY KEY (`date`),UNIQUE KEY `id_UNIQUE` (`id`)) ENGINE = InnoDB DEFAULT CHARACTER SET = utf8 COLLATE = utf8_unicode_ci;")   
			if tbType != "tick": self.Execute(f"CREATE TABLE IF NOT EXISTS `{dbName}`.`{tbName}` (`id` int unsigned NOT NULL AUTO_INCREMENT,`date` datetime NOT NULL,`bidopen` float NOT NULL,`bidclose` float NOT NULL,`bidhigh` float NOT NULL,`bidlow` float NOT NULL,`askopen` float NOT NULL,`askclose` float NOT NULL,`askhigh` float NOT NULL,`asklow` float NOT NULL,`tickqty` float NOT NULL,PRIMARY KEY (`date`),UNIQUE KEY `id_UNIQUE` (`id`)) ENGINE = InnoDB DEFAULT CHARACTER SET = utf8 COLLATE = utf8_unicode_ci;") 
			if self.verbose : print(f"Table {tbName} Createded")           
		def Insert(self, tbType, dbName, tbName, value):
			count = 0 
			if tbType == "tick" :        
				for candle in value:        
					if(candle != None):
						self.Execute(f"INSERT INTO `{dbName}`.`{tbName}` (`date`, `bid`, `ask`, `high`, `low`) VALUES ('{dt.fromtimestamp(candle[0])}',{candle[1]},{candle[2]},'{candle[3]}','{candle[4]}'')")
						count+=1
			if tbType != "tick" :                               
				for index, row in value:
					if(index != None):
						self.Execute(f"INSERT INTO `{dbName}`.`{tbName}` (`date`, `bidopen`, `bidclose`, `bidhigh`, `bidlow`, `askopen`, `askclose`, `askhigh`, `asklow`, `tickqty` ) VALUES ('{str(index)}',{row[0]},{row[1]},'{row[2]}','{row[3]}','{row[4]}','{row[5]}','{row[6]}','{row[7]}','{row[8]}')")
						count+=1
			return count                  

	class Postgresql:
		def __init__(self, host,user, password, database, verbose):
			self.host=host
			self.user=user
			self.password=password
			self.database=database 
			self.verbose=verbose
		def Open(self, openType=False): 
			if openType : self.connection = psycopg2.connect(host=self.host, user=self.user, password=self.password)
			if openType !=True : self.connection = psycopg2.connect(host=self.host, user=self.user, password=self.password, database=self.database)
			self.connection.set_isolation_level(0)
			self.cursor = self.connection.cursor()        
		def Close(self):                
			self.cursor.close()
			self.connection.close()                                
		def Execute(self, cmd) : 
			self.cursor.execute(cmd)  
		def GetDataOne(self, cmd):
			self.cursor.execute(cmd)                                                        
			return self.cursor.fetchone()
		def GetLastDate(self, tbType, dbName, tbName): 
			return self.GetDataOne(f"SELECT max(date) FROM {dbName}.public.{tbName}")
		def DropDatabase(self, dbName):
			self.Open(True)     
			self.Execute(f"DROP DATABASE IF EXISTS {dbName}") 
			self.Close()
			if self.verbose : print(f"Database {dbName} Droped")
		def CreateDatabase(self, dbName):
			self.Open(True)        
			self.Execute(f"Create DATABASE  {dbName}")
			self.Close()        
			if self.verbose : print(f"Database {dbName} Createded")
		def CreateTable(self, tbType, dbName, tbName):        
			if tbType == "tick" : self.Execute(f"CREATE TABLE {tbName}  (id serial UNIQUE NOT NULL,date TIMESTAMP UNIQUE NOT NULL PRIMARY KEY,bid decimal,ask decimal,high decimal,low decimal)") 
			if tbType != "tick" : self.Execute(f"CREATE TABLE {tbName}  (id serial UNIQUE NOT NULL,date TIMESTAMP UNIQUE NOT NULL PRIMARY KEY,bidopen decimal,bidclose decimal,bidhigh decimal,bidlow decimal,askopen decimal,askclose decimal,askhigh decimal,asklow decimal,tickqty decimal)") 
			if self.verbose : print(f"Table {tbName} Createded")
		def Insert(self, tbType, dbName, tbName, value):
			count = 0 
			if tbType == "tick" :        
				for candle in value:        
					if(candle != None):
						self.Execute(f"INSERT INTO {tbName} (date, bid, ask, high, low) VALUES ('{dt.fromtimestamp(candle[0])}',{candle[1]},{candle[2]},'{candle[3]}','{candle[4]}'')")
						count+=1
			if tbType != "tick" :                               
				for index, row in value:
					if(index != None):
						self.Execute(f"INSERT INTO {tbName} (date, bidopen, bidclose, bidhigh, bidlow, askopen, askclose, askhigh, asklow, tickqty) VALUES ('{str(index)}',{row[0]},{row[1]},'{row[2]}','{row[3]}','{row[4]}','{row[5]}','{row[6]}','{row[7]}','{row[8]}')")
						count+=1
			return count

	class Sqlserver:
		def __init__(self, host,user, password, database, verbose):
			self.host=host
			self.user=user
			self.password=password
			self.database=database 
			self.verbose=verbose
		def Open(self, openType=True):
			self.connection = pyodbc.connect('Driver={SQL Server};SERVER=' + self.host + ';UID=' + self.user +';PWD='+ self.password, autocommit=True)             
			self.cursor = self.connection.cursor()
		def Close(self):                
			self.cursor.close()
			self.connection.close()                                
		def Execute(self, cmd) : 
			pass
			self.cursor.execute(cmd)   
		def GetDataOne(self, cmd):
			self.cursor.execute(cmd)                                                        
			return self.cursor.fetchone()
		def GetLastDate(self, tbType, dbName, tbName): 
			return self.GetDataOne(f"SELECT max([date]) FROM {dbName}.dbo.{tbName}")
		def DropDatabase(self, dbName): 
			self.Open()        
			self.Execute(f"DROP DATABASE IF EXISTS {dbName}")         
			self.Close()
			if self.verbose : print(f"Database {dbName} Droped")
		def CreateDatabase(self, dbName): 
			self.Open()
			self.Execute(f"CREATE DATABASE {dbName}")  
			self.Close()
			if self.verbose : print(f"Database {dbName} Createded")        
		def CreateTable(self, tbType, dbName, tbName):
			if tbType == "tick" : self.Execute(f"CREATE TABLE {dbName}.dbo.{tbName} ([id] INT IDENTITY (1, 1) NOT NULL,[date] DATETIME PRIMARY KEY NOT NULL,[bid] float NOT NULL,[ask] float NOT NULL,[high] float NOT NULL,[low] float NOT NULL);") 
			if tbType != "tick" : self.Execute(f"CREATE TABLE {dbName}.dbo.{tbName} ([id] INT IDENTITY (1, 1) NOT NULL, [date] DATETIME PRIMARY KEY NOT NULL, [bidopen] float NOT NULL, [bidclose] float NOT NULL, [bidhigh] float NOT NULL, [bidlow] float NOT NULL, [askopen] float NOT NULL, [askclose] float NOT NULL, [askhigh] float NOT NULL, [asklow] float NOT NULL, [tickqty] float NOT NULL)")
			if self.verbose : print(f"Table {tbName} Createded")
		def Insert(self, tbType, dbName, tbName, value):
			count = 0 
			if tbType == "tick" :        
				for candle in value:        
					if(candle != None):
						self.Execute(f"INSERT INTO {dbName}.dbo.{tbName} ([date], [bid], [ask], [high], [low]) VALUES ('{dt.fromtimestamp(candle[0])}','{candle[1]}', '{candle[2]}', '{candle[3]}', '{candle[4]}')")
						count+=1
			if tbType != "tick" :                               
				for index, row in value:
					if(index != None):
						self.Execute(f"INSERT INTO {dbName}.dbo.{tbName} ([date], [bidopen], [bidclose], [bidhigh], [bidlow], [askopen], [askclose], [askhigh], [asklow], [tickqty]) VALUES ('{str(index)}', '{row[0]}','{row[1]}','{row[2]}','{row[3]}','{row[4]}','{row[5]}','{row[6]}','{row[7]}','{row[8]}')") 
						count+=1
			return count
		def InsertBulk(self, tbType, dbName, tbName, value):
			count = 0 
			if tbType == "tick" :        
				for candle in value:        
					if(candle != None):
						self.Execute(f"INSERT INTO {dbName}.dbo.{tbName} ([date], [bid], [ask], [high], [low]) VALUES ('{dt.fromtimestamp(candle[0])}','{candle[1]}', '{candle[2]}', '{candle[3]}', '{candle[4]}')")
						count+=1
			if tbType != "tick" :  
				cmd=f"INSERT INTO {dbName}.dbo.{tbName} ([date], [bidopen], [bidclose], [bidhigh], [bidlow], [askopen], [askclose], [askhigh], [asklow], [tickqty]) VALUES "                           
				for index, row in value:
					if(index != None):
						cmd += f"('{str(index)}', '{row[0]}', '{row[1]}', '{row[2]}', '{row[3]}', '{row[4]}', '{row[5]}', '{row[6]}', '{row[7]}', '{row[8]}'),"
						count+=1
				cmd = cmd[:-1]                                                        
				self.Execute(cmd)
			return count  
        
	
#### forex_module.py

	import datetime as d
	import time
	from datetime import datetime as dt
	import fxcmpy
	import module.database_module as database  
	from mysql.connector import Error


	def speed(func):
		def wrapper(*args, **kwargs):
			start_time = time.time() 
			result = func(*args, **kwargs)        
			print(f"Time : {'{:.0f}'.format(time.time() - start_time)} Seccond")
			return result
		return wrapper


	class Forex:
		def __init__(self, access_token,db_instanc, verbose): 
			self.access_token =  access_token
			self.db_instanc =  db_instanc        
			self.item = 0 
			self.verbose = verbose

		def Open(self): self.con = fxcmpy.fxcmpy(access_token = self.access_token, log_level = 'error')        
		def Close(self): self.con.close()  
		def Instrument(self): return self.con.get_instruments() 

		@speed    
		def Update(self, instrument, timeFrame, dateFrom, dateTo):                        
			#----- Some Changes            
			myDay = {"M1": 10000, "W1": 10000, "D1": 10000, "H8": 5100, "H6": 3600, "H4": 2660, "H3": 2000, "H2": 1200,"H1": 600, "m30": 300, "m15": 200, "m5": 50, "m1": 15} 
			myMin = {"M1": 46080, "W1": 10080, "D1": 1440, "H8": 480, "H6": 360, "H4": 240, "H3": 180, "H2": 120,"H1": 60, "m30": 30, "m15": 15, "m5": 5, "m1": 1}
			number=10000
			count_instrument = 0                         
			item=1
			First=False      
			myInstrument=instrument.replace('/', '')
			myInstrument=myInstrument.replace('.', '')
			myTimeFrame=timeFrame.replace('M1', 'MO1')
			db = database.Database(self.db_instanc, self.verbose)
			#----- Download History                      
			db.Open()
			lastDate=db.GetLastDate(timeFrame, db.database, f"{myInstrument}_{myTimeFrame}")[0]   
			if lastDate is None : 
				First=True
				myDateTo = dateFrom          
			else : myDateTo = lastDate    
			if (myDateTo + d.timedelta(minutes = +(1*myMin.get(timeFrame)))) < dateTo:
				while (myDateTo + d.timedelta(minutes = +(1*myMin.get(timeFrame)))) < dateTo:
					if First:
						myDateTo = dateFrom+d.timedelta(minutes=-myMin.get(timeFrame))
						First=False
					start_time = time.time()
					myDateFrom = myDateTo + d.timedelta(minutes = +myMin.get(timeFrame))
					myDateTo = myDateFrom + d.timedelta(days = +myDay.get(timeFrame))            
					if myDateFrom > dateTo : break
					if myDateTo > dateTo : myDateTo = dateTo         
					count = self.DownloadHistory(instrument, timeFrame, number, myDateFrom, myDateTo, db)                                                 
					print(f"-----{item}-----{instrument}-----{timeFrame}-----({myDateFrom})-({myDateTo})-----{count}-----{'{:.0f}'.format(time.time() - start_time)}")  
					count_instrument += count
					item+=1
				print(f"Download Finish-----{instrument}-----{timeFrame}-----({myDateTo})-----{count_instrument}")
			else:            
				print(f"Full-----{instrument}-----{timeFrame}-----{lastDate}")
			db.Close()                
		
		def DownloadHistory(self, instrument, timeFrame, number, dateFrom, dateTo, db):
			count = 0
			#----- Download History                                    
			c = self.con.get_candles(instrument=instrument, period=timeFrame, number=number,start=dateFrom, end=dateTo)                          
			#----- Some Changes  
			myInstrument=instrument.replace('/', '')
			myInstrument=myInstrument.replace('.', '')                          
			myTimeFrame=timeFrame.replace('M1', 'MO1')                  
			#----- Insert data to database 
			if timeFrame == "tick": count = db.Insert(timeFrame, db.database, f"{myInstrument}_{myTimeFrame}", c['candles'])
			if timeFrame != "tick": count = db.Insert(timeFrame, db.database, f"{myInstrument}_{myTimeFrame}", c.iterrows())
			#----- Return 
			return count      
		
		@speed
		def CreateDatabase(self, instruments, timeFrames):                               
			#----- Drop and Create Database
			db = database.Database(self.db_instanc, self.verbose)
			db.DropDatabase(db.database)
			db.CreateDatabase(db.database)
			#----- Create Tables    
			db.Open()
			for i in instruments:
				for t in timeFrames:
					i=i.replace('/', '')       
					i=i.replace('.', '') 
					t=t.replace('M1', 'MO1') 
					db.CreateTable(t, db.database, f"{i}_{t}")                    
			db.Close()                                                  
			print(f"-------------- {len(instruments) * len(timeFrames)} Table Created")