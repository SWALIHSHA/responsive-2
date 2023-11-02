# responsive-2
from flask import Flask, render_template, request

app = Flask(__name__)

@app.route('/')
def index():
    return render_template('home.html')

@app.route('/', methods=['POST', 'GET'])
def getvalues():
    if request.method == 'POST':
        name = request.form['name']
        return f'You submitted the name: {name}'
    return 'Use the form to submit a name'

if __name__ == '__main__':
    app.run(debug=True)
