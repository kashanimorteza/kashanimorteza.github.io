<style>
.md0{padding-bottom: 150px;}
.md1{padding-bottom: 75px;}
.md2{padding-bottom: 50px;}
.md3{padding-bottom: 25px;}
.md4{padding-bottom: 5px;}
.md5{padding-bottom: 10px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
.red{color:#E74C3C}
.blue{color:#3498DB}
.green{color:##28B463}
table{border: 0px solid black;}
</style>

# [<span style="color:black;">Flask</span>](Index.md)

<div class="md3"></div>

[Basic](Basic.md) |
[Structure](Structure.md) | 
[Script](Script.md) | 
[Script](Flask.md)

<div class="md3">
<a href="#diagram">Diagram</a> - 
<a href="#resource">Resource</a> - 
<a href="#install">Install</a> - 
<a href="#interpretation">Interpretation</a> - 
<a href="#package-manager">Package manager</a> - 
<a href="#question">Question</a>  
</div>





## Diagram

<div class="md1">

![] (Diagram/Flask.jpeg)

</div>








<div class="md1"></div>

## Resource

#### General

<a href="https://palletsprojects.com/" target="_blank">Flask</a>







## Install

<div class="md1">

#### Windows

#### Linux	

</div>





## Run

<div class="md1">

#### General

	ipython

	flask run : only run app.py | wsgi.py


#### Windows

	set FLASK_APP=main.py
	flask run
	unset FLASK_APP

	Debug
	-------
	set FLASK_ENV=development
	flask run
	unset FLASK_ENV

#### Linux	

	Way 1
	-------
	export FLASK_APP=main.py
	flask run
	unset FLASK_APP

	Way 2
	-------
	FLASK_APP=main.py flask run

	Debug
	-------
	export FLASK_ENV=development
	flask run
	unset FLASK_ENV

</div>





## Script

<div class="md1">

#### View

	@app.route('/a')
	def a():
		return ('<h1>Hello world</h1>') 


	@app.route('/b/<string:data>')        
	def b(data):
		return (f'<h1>{data}</h1>')           


	@app.route('/c/<path:data>')
	def c(data):
		return (f'<h1>{data}</h1>')   




#### Templates	

	------------------Example 1 
	app = flask.Flask(__name__)
	@app.route('/d')
	def d():
		return flask.render_template('d.html')


	------------------Example 2

	app = flask.Flask(__name__,template_folder='myTemplateFolder')
	@app.route('/e')
	def e():
		return flask.render_template('e.html')

	
	------------------Example 3
	
	app = flask.Flask(__name__)
	@app.route('/f')
	def f():
		myVariable = 'morteza'
		return flask.render_template('f.html',data = myVariable)

	app.run("0.0.0.0", "80", debug=True)
		
	<html>
		<head></head>
		<body>
		<h1>{{ data }}</h1>
		</body>
	</html>


	------------------Example 4

	import flask
	app = flask.Flask(__name__)
	@app.route('/f')
	def f():
		myVariable = 'morteza'
		return flask.render_template('f.html',data = myVariable)
	app.run("0.0.0.0", "80", debug=True)	
		
	<html>
		<head></head>
		<body>
		<h1>
			{% if data=='morteza' %}
				aaaa
			{% else %}
				bbb        
			{% endif %}
			</h1>
		</body>
	</html>


	------------------Example 5

	import flask
	app = flask.Flask(__name__)
	@app.route('/g')
	def g():
		myVariable = ['reza', 'morteza', 'ahmad']
		return flask.render_template('g.html',data = myVariable)
	app.run("0.0.0.0", "80", debug=True)	
		
	<html>
		<head></head>
		<body>
		<h1>        
			{% for d in data %}
			{{ d }}     
			{% endfor %}
			</h1>
		</body>
	</html>



	------------------Example 6 WTF

    from flask import Flask,render_template, request
    from flask_wtf import FlaskForm
    from wtforms import TextField,PasswordField
    from wtforms.validators import DataRequired

    app = Flask(__name__)

    app.config['SECRET_KEY'] = 'sdfdsfdsfdsfsdfs'

    @app.route('/g', methods=['GET', 'POST'])
    def g():
        login_form = Login(request.form)
        if not login_form.validate_on_submit() : 
            return render_template('g.html', data=login_form) 
        else:
            return 'ok'

    class Login(FlaskForm):
        username = TextField(validators=[DataRequired()])
        password = PasswordField(validators=[DataRequired()])

    app.run("0.0.0.0", "80", debug=False)


    <html>
        <head></head>
        <body>
            <form action="{{ url_for('g') }}" method="POST">
                {{ data.hidden_tag() }}
                <br> 
                {{ data.username.label}} : {{ data.username() }}
                <br> 
                {{ data.password.label}} : {{ data.password() }}
                <input type="submit" value="Login">            
            </form>
        </body>
    </html>



</div>












## Question

<div class="md1">

</div>
