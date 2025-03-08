# 2f2H-Dreams-Hack-code
from flask import Flask, request, jsonify
from flask_cors import CORS
from pyngrok import ngrok

app = Flask(__name__)
CORS(app)

@app.route('/calculate', methods = ['POST'])
def main_code() :
    data = request.get_json()
    
public_url = ngrok.connect(5000)
print(f"Public URL : {public_url}")

app.run(port=5000)
