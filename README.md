# m3l1
from flask import Flask
import random

listas_consejos=["Según un estudio realizado en 2018, más del 50% de las personas de entre 18 y 34 años se consideran dependientes de sus smartphones","Según un estudio de 2019, más del 60% de las personas responden a mensajes de trabajo en sus smartphones en los 15 minutos siguientes a salir del trabajo","Una forma de combatir la dependencia tecnológica es buscar actividades que aporten placer y mejoren el estado de ánimo"]
 
app = Flask(__name__)

@app.route("/")
def index():
    return f'<h1>hola esta es mi pagina web y te voy a dar consejos sobre la dependencia tecnologica</h1><a href="/Nuevo_consejo">veamos un consejo al azar</a>'
@app.route("/Nuevo_consejo")
def listas():
    return f'<p>{random.choice(listas_consejos)}</p>'

app.run(debug=True)
