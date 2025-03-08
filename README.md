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

#slight changes

let currentBoxIndex = 0;
const sections = [
    "#LPQ1", "#LPQ2", "#LPQ3", "#LPQ4", "#LPQ5", 
    "#LCQ1", "#LCQ2", "#LCQ3", "#LCQ4", "#LCQ5",
    "#LMQ1", "#LMQ2", "#LMQ3", "#LMQ4", "#LMQ5"
];

// Array to store answers
let userAnswers = [];

// Function to collect answers
function collectAnswers() {
    const currentSection = $w(sections[currentBoxIndex]);

    // Assuming each section has a question with multiple choice or text input
    const answer = currentSection.querySelector('input[type="radio"]:checked')?.value || // For radio buttons
                   currentSection.querySelector('input[type="checkbox"]:checked')?.value || // For checkboxes
                   currentSection.querySelector('input[type="text"]').value; // For text inputs

    // Store the answer
    userAnswers[currentBoxIndex] = answer;
}

$w.onReady(function () {
    // Hide all sections except the first one
    sections.forEach((id, index) => {
        if (index !== 0) $w(id).hide();
    });

    // Button click function to move to the next section
    $w("#LNext").onClick(() => {
        collectAnswers(); // Collect the answer before moving to the next section

        if (currentBoxIndex < sections.length - 1) {
            $w(sections[currentBoxIndex]).hide(); // Hide current section
            currentBoxIndex++;
            $w(sections[currentBoxIndex]).show(); // Show next section
        }

        // Send answers to backend after each question or at the end
        sendAnswersToBackend();
    });

    // Button click function to go back to the previous section
    $w("#LPrevious").onClick(() => {
        collectAnswers(); // Collect the answer before going back

        if (currentBoxIndex > 0) {
            $w(sections[currentBoxIndex]).hide(); // Hide current section
            currentBoxIndex--;
            $w(sections[currentBoxIndex]).show(); // Show previous section
        }
    });
});

// Function to fetch the link and send answers to the backend (Python)
function sendAnswersToBackend() {
    // Fetch the Python server link
    fetch("https://0f59-34-80-29-194.ngrok-free.app/calculate", {
        method: 'POST',
        headers: {
            'Content-Type': 'application/json',
        },
        body: JSON.stringify({
            answers: userAnswers // Send the collected answers as JSON
        })
    })
    .then(response => response.json())  // Assuming your Python backend returns JSON
    .then(data => {
        console.log('Success:', data); // Log the response from the backend
        // Optionally, you could process this data (e.g., show results or redirect)
    })
    .catch((error) => {
        console.error('Error:', error); // Log any errors in the fetch request
    });
}

# wix changes

$w.onReady(function () 
{
	// Show Question 1 Elements
	$w("#PQ1, #PQ1Option1, "#PQ1Option2", "#PQ1Option3", "#PQ1Option4").expand();
	$w("#PQ1, #PQ2Option1, "#PQ2Option2", "#PQ2Option3", "#PQ2Option4").collapse();
	
	// Next Button Function
	$w("#LNext").onClick(() => 
	{
		// Hide Question 2
		$w("#PQ1, #PQ1Option1, "#PQ1Option2", "#PQ1Option3", "#PQ1Option4").collapse();
		$w("#PQ1, #PQ2Option1, "#PQ2Option2", "#PQ2Option3", "#PQ2Option4").expand();
	});
	
	// Previous Button Function
	$w("#Previous").onClick(() => 
	{
		// Hide Question 1
		$w("#PQ1, #PQ1Option1, "#PQ1Option2", "#PQ1Option3", "#PQ1Option4").expand();
		$w("#PQ1, #PQ2Option1, "#PQ2Option2", "#PQ2Option3", "#PQ2Option4").collapse();
	});
});

#wix changes -- toggle questions

$w.onReady(function () {
    // Show Question 1, Hide Question 2 at Start
    showQuestion(1);

    // Next Button Click - Show Question 2, Hide Question 1
    $w("#LNext").onClick(() => {
        showQuestion(2);
    });

    // Previous Button Click - Show Question 1, Hide Question 2
    $w("#LPrevious").onClick(() => {
        showQuestion(1);
    });

    function showQuestion(questionNumber) {
        if (questionNumber === 1) {
            toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], true);
            toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], false);
        } else if (questionNumber === 2) {
            toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], false);
            toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], true);
        }
    }

    function toggleQuestion(elements, show) {
        elements.forEach(id => {
            if (show) {
                $w(id).expand();
            } else {
                $w(id).collapse();
            }
        });
    }
});

# wix changes save user input 

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

// Next Button Click - Show Question 2, Hide Question 1
$w("#LNext").onClick(() => {
    showQuestion(2);
});

// Previous Button Click - Show Question 1, Hide Question 2
$w("#LPrevious").onClick(() => {
    showQuestion(1);
});

function showQuestion(questionNumber) {
    if (questionNumber === 1) {
        toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], true);
        toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], false);
    } else if (questionNumber === 2) {
        toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], false);
        toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], true);
    }
}

function toggleQuestion(elements, show) {
    elements.forEach(id => {
        if (show) {
            $w(id).expand();
        } else {
            $w(id).collapse();
        }
    });
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

