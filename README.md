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

# wix code changes

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

    fetch("https://0f59-34-80-29-194.ngrok-free.app/calculate",{
            method : 'POST',

});

# wix code changes 2


let currentBoxIndex = 0; const boxes = [ 
	"#LPQ1", "#LPQ2", "LPQ3", "LPQ4", "LPQ5", 
	"#LCQ1", "#LCQ2", "#LCQ3", "#LCQ4", "#LCQ5", 
	"#LMQ1", "#LMQ2", "#LMQ3", "#LMQ4", "#LMQ5"];

let studentAnswers = [];

function collectAnswers() {
    const currentPage = $w(boxes[currentPageIndex]);

const answer = currentPage.querySelector('input[type="radio"]:checked')?.value || 
// So we're storing the answer
userAnswers[currentPageIndex] = answer;

$w.onReady(function () 
{ 
	// Hide all pages except the first one ]
	pages.forEach((id, index) => 
	{ 
		if (index !== 0) $w(id).collapse(); });
		// to move to the next question
		$w("#LNext").onClick(() => 
		{
			collectAnswers(); 
		if (currentPageIndex < pages.length - 1) 
		{
        	$w(boxes[currentPageIndex]).hide(); // Hide current page
        	currentPageIndex++;
        	$w(boxes[currentPageIndex]).show(); // Show next page
    		}
	});

	$w("#LPrevious").onClick(() => 
	{
		collectAnswers(); 
		if (currentPageIndex < pages.length - 1) {
        $w(boxes[currentPageIndex]).hide(); // Hide current page uk
        currentPageIndex--;
        $w(boxes[currentPageIndex]).show(); // Show next page (or next question)
    }
});


function sendAnswersToBackend() {
    fetch("https://0f59-34-80-29-194.ngrok-free.app/main_code", {
        method: 'POST',
        headers: {
            'Content-Type': 'application/json',
        },
        body: JSON.stringify({
            answers: userAnswers 
        })
    })
    .then(response => response.json())
    .then(data => {
        console.log('Success:', data);
    })
    .catch((error) => {
        console.error('Error:', error);
    });
});
