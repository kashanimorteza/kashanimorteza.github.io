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
<a href="#Genaral">Genaral</a> - 
<a href="#database-module">Database Module</a> - 
<a href="#forex-module">Forex Module</a> 



<div class="md1"></div>

## General
#### Test
	import fxcmpy
	import socketio

	print(fxcmpy.__version__)
	print(socketio.__version__)

#### App1
	import fxcmpy 

	TOKEN = "8cf59d60ddcf4a13142d2310ff601ee611f760a6"

	con = fxcmpy.fxcmpy(access_token = TOKEN, log_level = 'error')
	print('Connected')

	instruments = con.get_instruments()
	print(instruments[:5])

	con.close()
	print('Dissconnected')
	
	
	



<div class="md0"></div>
	
## Database Module
#### database_config.json
	{
		"database": {
			"host":"localhost",
			"user":"root",
			"password":"123456",
			"database":"forex"        
		}
	}

#### database_module.py
	import mysql.connector
	from mysql.connector import Error
	import json


	class Database:      
		def __init__(self):
			try:
				self.config_file="config/database_config.json"              
					with open(self.config_file, 'r') as f:
					self.CONFIG = json.load(f)
					self.host=self.CONFIG['database']['host']
					self.user=self.CONFIG['database']['user']
					self.password=self.CONFIG['database']['password']
					self.database=self.CONFIG['database']['database']  
			except Error as e:
				print("Error: Database : __init__ ", e)    
		def Open(self):
			try:            
				self.connection = mysql.connector.connect(
					host=self.host, 
					user=self.user, 
					password=self.password)
				if  self.connection.is_connected():
					self.cursor = self.connection.cursor()
					print("-------------- [Connected to database server]")
			except Error as e:
					print("Error: Database : Open ", e)           
			def Close(self):
				try:
					if self.connection.is_connected():
						self.cursor.close()
						self.connection.close()
						print("-------------- [Disconnected from database server]")                
				except Error as e:
					print("Error: Database : Close ", e)           
			def Execute(self,command):
				try:
					self.cursor.execute(command)                                                
					self.connection.commit()
				except Error as e:
					print("Error: Database : Execute ", e) 
















<div class="md0"></div>
	
## Forex Module
#### forex_config.json
	{   
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
#### forex_module.py
	from datetime import datetime as dt
	from module import fxcm_rest_api_token as fxcm_rest_api
	from module import database_module as database
	import time


	class Forex:  
		def __init__(self):
			self.trader = fxcm_rest_api.Trader('19620ceba743f8ca9bdaf5fd128d93b9717e2fd1', 'demo')                                  

		def Open(self):
			self.trader.login()
			time.sleep(10) 

		def Close(self):
			self.trader.logout()              

		def DownloadHistory(self,instrument,timeFrame,dateFrom,dateTo):
			c =  self.trader.get_candles(instrument, timeFrame,10000,dateFrom,dateTo)   
			instrument=instrument.replace('/', '')       
			timeFrame=timeFrame.replace('M1', 'MO1')  

			db = database.Database()
			db.Open();  

			#Insert data to database
			if timeFrame=="tick":
				for candle in c['candles']:        
					if(candle != None): 
						cmd=f""
						db.Execute(cmd) 
			else :
				for candle in c['candles']:        
					if(candle != None): 
						cmd=f"INSERT INTO `forex`.`{instrument}_{timeFrame}` (`date`, `bidopen`, `bidclose`, `bidhigh`, `bidlow`, `askopen`, `askclose`, `askhigh`, `asklow`, `tickqty` ) VALUES ('{dt.fromtimestamp(candle[0])}',{candle[1]},{candle[2]},'{candle[3]}','{candle[4]}','{candle[5]}','{candle[6]}','{candle[7]}','{candle[8]}','{candle[9]}')"
						db.Execute(cmd) 

			db.Close()


			
	def CreateDatabaseTables():    
		timeFrameList = ["tick", "m1", "m5", "m15", "m30", "h1","h2", "h3", "h4", "h6", "h8", "D1", "W1", "MO1"]
		instrumentList = ['EURUSD', 'USDJPY', 'GBPUSD', 'USDCHF', 'EURCHF', 'AUDUSD', 'USDCAD', 'NZDUSD', 
					'EURGBP', 'EURJPY', 'GBPJPY', 'CHFJPY', 'GBPCHF', 'EURAUD', 'EURCAD', 'AUDCAD', 
					'AUDJPY', 'CADJPY', 'NZDJPY', 'GBPCAD', 'GBPNZD', 'GBPAUD', 'AUDNZD', 'USDSEK', 
					'EURSEK', 'EURNOK', 'USDNOK', 'USDMXN', 'AUDCHF','EURNZD', 'USDZAR', 'USDHKD', 
					'ZARJPY', 'USDTRY', 'EURTRY', 'NZDCHF', 'CADCHF', 'NZDCAD', 'TRYJPY', 'USDCNH', 
					'AUS200', 'ESP35', 'FRA40', 'GER30', 'HKG33', 'JPN225', 'NAS100', 'SPX500', 'UK100', 
					'US30', 'Copper', 'CHN50', 'EUSTX50', 'USDOLLAR', 'USOil', 'UKOil', 'SOYF', 'NGAS', 
					'Bund', 'XAUUSD', 'XAGUSD']

		db = database.Database()
		db.Open()

		try:

			#Create database
			print(f"Database droped : {db.database}")
			db.Execute(f"DROP  DATABASE IF EXISTS {db.database};")
			print(f"Database created : {db.database}")
			db.Execute(f"CREATE DATABASE IF NOT EXISTS {db.database};")

			#Create tables
			for i in instrumentList:
				for t in timeFrameList:
					if t == "tick":
						command = f"""
								CREATE TABLE IF NOT EXISTS `{db.database}`.`{i}_{t}` (
								`id` INT UNSIGNED NULL AUTO_INCREMENT,
								`date` DATETIME NOT NULL,
								`bid` FLOAT NOT NULL,
								`ask` FLOAT NOT NULL,
								`high` FLOAT NOT NULL,
								`low` FLOAT NOT NULL,
								UNIQUE INDEX `id_UNIQUE` (`id` ASC) VISIBLE,
								PRIMARY KEY(`date`))
								"""
					else:            
						command = f"""
								CREATE TABLE IF NOT EXISTS `{db.database}`.`{i}_{t}` (
								`id` INT UNSIGNED NULL AUTO_INCREMENT,
								`date` DATETIME NOT NULL,
								`bidopen` FLOAT NOT NULL,
								`bidclose` FLOAT NOT NULL,
								`bidhigh` FLOAT NOT NULL,
								`bidlow` FLOAT NOT NULL,                    
								`askopen` FLOAT NOT NULL,
								`askclose` FLOAT NOT NULL,
								`askhigh` FLOAT NOT NULL,
								`asklow` FLOAT NOT NULL,
								`tickqty` INT NOT NULL,                
								UNIQUE INDEX `id_UNIQUE` (`id` ASC) VISIBLE,
								PRIMARY KEY(`date`))
								"""
					db.Execute(command)        
					print(f"Table Created : {i}_{t}")
			db.Close()
		except Error as e:
			print("Error: Database : CreateDatabaseTables ", e) 		
#### main.py
	from datetime import datetime as dt
	from module import database_module as database
	from module import forex_module as forex


	def MyConvert(type,date): 
		if type==1:   
			return dt.timestamp(dt.strptime(date, "%Y/%m/%d %H:%M:%S"))
		else:
			return dt.fromtimestamp(date)        


	#----- Create databases and tables
	#forex.CreateDatabaseTables()

	#----- Set variables
	dateFrom = MyConvert(1,'1990/01/01 00:00:00')
	dateTo = MyConvert(1,'2020/01/01 00:00:00')
	instrument="USD/JPY"
	timeFrame="M1"

	#----- Download History
	fx = forex.Forex()
	fx.Open()
	print(f"-------------- Download Data : Start : {instrument} : {timeFrame} : {MyConvert(2,dateFrom)} : {MyConvert(2,dateTo)}")
	fx.DownloadHistory(instrument,timeFrame,dateFrom,dateTo)
	print(f"-------------- Download Data : End : {instrument} : {timeFrame} : {MyConvert(2,dateFrom)} : {MyConvert(2,dateTo)}")
	fx.Close()

