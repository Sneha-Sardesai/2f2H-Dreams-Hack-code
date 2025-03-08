# 2f2H-Dreams-Hack-Python code
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

# Wix code

let currentBoxIndex = 0;
const boxes = [
	"#LPQ1", "#LPQ2", "LPQ3", "LPQ4", "LPQ5", 
	"#LCQ1", "#LCQ2", "#LCQ3", "#LCQ4", "#LCQ5",
	"#LMQ1", "#LMQ2", "#LMQ3", "#LMQ4", "#LMQ5"];

$w.onReady(function () {
    // Hide all boxes except the first one
    boxes.forEach((id, index) => {
        if (index !== 0) $w(id).collapse();
    });

    // Button click function to move to the next question
    $w("#LNext").onClick(() => {
        if (currentBoxIndex < boxes.length - 1) {
            $w(boxes[currentBoxIndex]).collapse(); // Hide current box
            currentBoxIndex++;
            $w(boxes[currentBoxIndex]).expand(); // Show next box
        }
    });

	$w("#LPrevious").onClick(() => {
        if (currentBoxIndex < boxes.length - 1) {
            $w(boxes[currentBoxIndex]).collapse(); // Hide current box
            currentBoxIndex--;
            $w(boxes[currentBoxIndex]).expand(); // Show next box
        }
    });
});
