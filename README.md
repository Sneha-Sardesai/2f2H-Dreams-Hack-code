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

# Backend python code

from flask import Flask, request, jsonify
from flask_cors import CORS
from pyngrok import ngrok

app = Flask(__name__)
CORS(app)

@app.route('/main_code', methods = ['POST'])
def main_code() :
	data = request.get('answers')
	student_answers = data.get('answers')
	values = [[answer] for answer in student_answers]
	body = {'values': values}
	
    
public_url = ngrok.connect(5000)
print(f"Public URL : {public_url}")

app.run(port=5000)

# Including all questions in Wix

// Next Button Click - Show Question 2, Hide Question 1
$w("#LNext").onClick(() => {
	showQuestion(2);
$w("#LNext").onClick(() => {
	showQuestion(3);
$w("#LNext").onClick(() => {
	showQuestion(4);
$w("#LNext").onClick(() => {
	showQuestion(5);
$w("#LNext").onClick(() => {
	showQuestion(6);
$w("#LNext").onClick(() => {
	showQuestion(7);
$w("#LNext").onClick(() => {
	showQuestion(8);
$w("#LNext").onClick(() => {
	showQuestion(9);
$w("#LNext").onClick(() => {
	showQuestion(1);

});

// Previous Button Click - Show Question 1, Hide Question 2
$w("#LPrevious").onClick(() => {
    showQuestion(8);
$w("#LNext").onClick(() => {
	showQuestion(2);
$w("#LNext").onClick(() => {
	showQuestion(3);
$w("#LNext").onClick(() => {
	showQuestion(4);
$w("#LNext").onClick(() => {
	showQuestion(5);
$w("#LNext").onClick(() => {
	showQuestion(6);
$w("#LNext").onClick(() => {
	showQuestion(7);
$w("#LNext").onClick(() => {
	showQuestion(8);
$w("#LNext").onClick(() => {
	showQuestion(9);
$w("#LNext").onClick(() => {
	showQuestion(1);

});

function showQuestion(QNum) 
{
   	if (QNum === 1) 
	{
        	toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], true);
        	toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], false);
		toggleQuestion(["#PQ3", "#PQ3Option1", "#PQ3Option2", "#PQ3Option3", "#PQ3Option4"], false);
	} 
	else if (QNum === 2) 
	{
        	toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], false);
        	toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], true);
		toggleQuestion(["#PQ3", "#PQ3Option1", "#PQ3Option2", "#PQ3Option3", "#PQ3Option4"], false);
    	}
	else if (QNum == 3)
	{
		
	
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

# More wix changes

let Questions = ["#LPQ1", "#LPQ2", "#LPQ3", "#LCQ1", "#LCQ2", "#LCQ3", "#LMQ1", "#LMQ2", "#LMQ3"];

// Next Button Click 
$w("#LNext").onClick(() => 
{
	for (let CurrentQ in Questions) 
	{
		if (CurrentQ == 8) 
		{
			showQuestion(0);
		}
		else
		{
			showQuestion(CurrentQ+1);
		}
	}

});

// Previous Button Click - Show Question 1, Hide Question 2
$w("#LPrevious").onClick(() => {
    showQuestion(8);
$w("#LNext").onClick(() => {
	showQuestion(2);
$w("#LNext").onClick(() => {
	showQuestion(3);
$w("#LNext").onClick(() => {
	showQuestion(4);
$w("#LNext").onClick(() => {
	showQuestion(5);
$w("#LNext").onClick(() => {
	showQuestion(6);
$w("#LNext").onClick(() => {
	showQuestion(7);
$w("#LNext").onClick(() => {
	showQuestion(8);
$w("#LNext").onClick(() => {
	showQuestion(9);
$w("#LNext").onClick(() => {
	showQuestion(1);

});

function showQuestion(QNum) 
{
   	if (QNum === 1) 
	{
        	toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], true);
        	toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], false);
		toggleQuestion(["#PQ3", "#PQ3Option1", "#PQ3Option2", "#PQ3Option3", "#PQ3Option4"], false);
	} 
	else if (QNum === 2) 
	{
        	toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], false);
        	toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], true);
		toggleQuestion(["#PQ3", "#PQ3Option1", "#PQ3Option2", "#PQ3Option3", "#PQ3Option4"], false);
    	}
	else if (QNum == 3)
	{
		
	
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

# More changes

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

-----------------------------------------------------------------------

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
-------------------------------------------------------------------------------------------------------------

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
------------------------------------------------------------------------------------------------------------

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
    fetch("https://cdc1-34-16-23-116.ngrok-free.app/main_code", {
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

------------------------------------------------------------------------------------------------------

let Questions = ["#LPQ1", "#LPQ2", "#LPQ3", "#LCQ1", "#LCQ2", "#LCQ3", "#LMQ1", "#LMQ2", "#LMQ3"];

// Next Button Click 
$w("#LNext").onClick(() => 
{
	for (let CurrentQ in Questions) 
	{
		if (CurrentQ == 8) 
		{
			showQuestion(0);
		}
		else
		{
			showQuestion(CurrentQ+1);
		}
	}

});

// Previous Button Click - Show Question 1, Hide Question 2
$w("#LPrevious").onClick(() => {
    showQuestion(8);
$w("#LNext").onClick(() => {
	showQuestion(2);
$w("#LNext").onClick(() => {
	showQuestion(3);
$w("#LNext").onClick(() => {
	showQuestion(4);
$w("#LNext").onClick(() => {
	showQuestion(5);
$w("#LNext").onClick(() => {
	showQuestion(6);
$w("#LNext").onClick(() => {
	showQuestion(7);
$w("#LNext").onClick(() => {
	showQuestion(8);
$w("#LNext").onClick(() => {
	showQuestion(9);
$w("#LNext").onClick(() => {
	showQuestion(1);

});

function showQuestion(QNum) 
{
   	if (QNum === 1) 
	{
        	toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], true);
        	toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], false);
		toggleQuestion(["#PQ3", "#PQ3Option1", "#PQ3Option2", "#PQ3Option3", "#PQ3Option4"], false);
	} 
	else if (QNum === 2) 
	{
        	toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], false);
        	toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], true);
		toggleQuestion(["#PQ3", "#PQ3Option1", "#PQ3Option2", "#PQ3Option3", "#PQ3Option4"], false);
    	}
	else if (QNum == 3)
	{
		toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], false);
        	toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], false);
		toggleQuestion(["#PQ3", "#PQ3Option1", "#PQ3Option2", "#PQ3Option3", "#PQ3Option4"], true);
	}
	else if (QNum  == 4)
	{
		toggleQuestion(["#CQ1", "#CQ1Option1", "#CQ1Option2", "#CQ1Option3", "#CQ1Option4"], true);
        	toggleQuestion(["#CQ2", "#CQ2Option1", "#CQ2Option2", "#CQ2Option3", "#CQ2Option4"], false);
		toggleQuestion(["#CQ3", "#CQ3Option1", "#CQ3Option2", "#CQ3Option3", "#CQ3Option4"], false);
	}
	else if (QNum == 5)
	{
		toggleQuestion(["#CQ1", "#CQ1Option1", "#CQ1Option2", "#CQ1Option3", "#CQ1Option4"], false);
        	toggleQuestion(["#CQ2", "#CQ2Option1", "#CQ2Option2", "#CQ2Option3", "#CQ2Option4"], true);
		toggleQuestion(["#CQ3", "#CQ3Option1", "#CQ3Option2", "#CQ3Option3", "#CQ3Option4"], false);

	}
	else if 
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

# wix final


let Questions = ["#LPQ1", "#LPQ2", "#LPQ3", "#LCQ1", "#LCQ2", "#LCQ3", "#LMQ1", "#LMQ2", "#LMQ3"];

// Next Button Click 
$w("#LNext").onClick(() => 
{
	for (let CurrentQ in Questions) 
	{
		if (CurrentQ == 8) 
		{
			showQuestion(0);
		}
		else
		{
			showQuestion(CurrentQ+1);
		}
	}

});

// Previous Button Click - Show Question 1, Hide Question 2
$w("#LPrevious").onClick(() => 
{
	for (let CurrentQ in Questions) 
	{
		if (CurrentQ == 0)
		{
			showQuestion(8);
		}
		else
		{
			showQuestion(CurrentQ-1);
		}
	}
});

function showQuestion(QNum) 
{
   	if (QNum === 0)
	{
        	toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], true);
        	toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], false);
		toggleQuestion(["#PQ3", "#PQ3Option1", "#PQ3Option2", "#PQ3Option3", "#PQ3Option4"], false);
	} 
	else if (QNum === 1)
	{
        	toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], false);
        	toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], true);
		toggleQuestion(["#PQ3", "#PQ3Option1", "#PQ3Option2", "#PQ3Option3", "#PQ3Option4"], false);
    	}
	else if (QNum == 2)
	{
		toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], false);
        	toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], false);
		toggleQuestion(["#PQ3", "#PQ3Option1", "#PQ3Option2", "#PQ3Option3", "#PQ3Option4"], true);
	}
	else if (QNum  == 3)
	{
		toggleQuestion(["#CQ1", "#CQ1Option1", "#CQ1Option2", "#CQ1Option3", "#CQ1Option4"], true);
        	toggleQuestion(["#CQ2", "#CQ2Option1", "#CQ2Option2", "#CQ2Option3", "#CQ2Option4"], false);
		toggleQuestion(["#CQ3", "#CQ3Option1", "#CQ3Option2", "#CQ3Option3", "#CQ3Option4"], false);
	}
	else if (QNum == 4)
	{
		toggleQuestion(["#CQ1", "#CQ1Option1", "#CQ1Option2", "#CQ1Option3", "#CQ1Option4"], false);
        	toggleQuestion(["#CQ2", "#CQ2Option1", "#CQ2Option2", "#CQ2Option3", "#CQ2Option4"], true);
		toggleQuestion(["#CQ3", "#CQ3Option1", "#CQ3Option2", "#CQ3Option3", "#CQ3Option4"], false);

	}
	else if (QNum == 5)
	{
		toggleQuestion(["#CQ1", "#CQ1Option1", "#CQ1Option2", "#CQ1Option3", "#CQ1Option4"], false);
        	toggleQuestion(["#CQ2", "#CQ2Option1", "#CQ2Option2", "#CQ2Option3", "#CQ2Option4"], false);
		toggleQuestion(["#CQ3", "#CQ3Option1", "#CQ3Option2", "#CQ3Option3", "#CQ3Option4"], true);
	}
	else if (QNum == 6)
	{
		toggleQuestion(["#MQ1", "#MQ1Option1", "#MQ1Option2", "#MQ1Option3", "#M1Option4"], true);
		toggleQuestion(["#MQ2", "#MQ2Option1","#MQ2Option2", "#MQ2Option3", "#MQ2Option4"], false);
		toggleQuestion(["#MQ3", "#MQ3Option1", "#MQ3Option2", "#MQ3Option3", "#MQ3Option4"], false);
	}
	else if (QNum == 7)
	{
		toggleQuestion(["#MQ1", "#MQ1Option1", "#MQ1Option2", "#MQ1Option3", "#M1Option4"], false);
		toggleQuestion(["#MQ2", "#MQ2Option1","#MQ2Option2", "#MQ2Option3", "#MQ2Option4"], true);
		toggleQuestion(["#MQ3", "#MQ3Option1", "#MQ3Option2", "#MQ3Option3", "#MQ3Option4"], false);
	}
	else if (QNum == 8)
	{
		toggleQuestion(["#MQ1", "#MQ1Option1", "#MQ1Option2", "#MQ1Option3", "#M1Option4"], false);
		toggleQuestion(["#MQ2", "#MQ2Option1","#MQ2Option2", "#MQ2Option3", "#MQ2Option4"], false);
		toggleQuestion(["#MQ3", "#MQ3Option1", "#MQ3Option2", "#MQ3Option3", "#MQ3Option4"], true);
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

# Wix final final

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

-----------------------------------------------------------------------

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
-------------------------------------------------------------------------------------------------------------

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
------------------------------------------------------------------------------------------------------------

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
    fetch("https://cdc1-34-16-23-116.ngrok-free.app/main_code", {
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

------------------------------------------------------------------------------------------------------

let Questions = ["#LPQ1", "#LPQ2", "#LPQ3", "#LCQ1", "#LCQ2", "#LCQ3", "#LMQ1", "#LMQ2", "#LMQ3"];

// Next Button Click 
$w("#LNext").onClick(() => 
{
	for (let CurrentQ in Questions) 
	{
		if (CurrentQ == 8) 
		{
			showQuestion(0);
		}
		else
		{
			showQuestion(CurrentQ+1);
		}
	}

});

// Previous Button Click - Show Question 1, Hide Question 2
$w("#LPrevious").onClick(() => 
{
	for (let CurrentQ in Questions) 
	{
		if (CurrentQ == 0)
		{
			showQuestion(8);
		}
		else
		{
			showQuestion(CurrentQ-1);
		}
	}
});

function showQuestion(QNum) 
{
   	if (QNum === 0)
	{
        	toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], true);
        	toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], false);
		toggleQuestion(["#PQ3", "#PQ3Option1", "#PQ3Option2", "#PQ3Option3", "#PQ3Option4"], false);
		toggleeQuestion(["#CQ1", "#CQ1Option1","#CQ1Option2","#CQ1Option3", "#CQ1Option4"], false);
        	toggleQuestion(["#CQ2", "#CQ2Option1", "#CQ2Option2", "#CQ2Option3", "#CQ2Option4"], false);
		toggleQuestion(["#CQ3", "#CQ3Option1", "#CQ3Option2", "#CQ3Option3", "#CQ3Option4"], false);
		toggleQuestion(["#MQ1", "#MQ1Option1", "#MQ1Option2", "#MQ1Option3", "#M1Option4"], false);
		toggleQuestion(["#MQ2", "#MQ2Option1","#MQ2Option2", "#MQ2Option3", "#MQ2Option4"], false);
		toggleQuestion(["#MQ3", "#MQ3Option1", "#MQ3Option2", "#MQ3Option3", "#MQ3Option4"], false);

	} 
	else if (QNum === 1)
	{
        	toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], false);
        	toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], true);
		toggleQuestion(["#PQ3", "#PQ3Option1", "#PQ3Option2", "#PQ3Option3", "#PQ3Option4"], false);
		toggleQuestion(["#CQ2", "#CQ2Option1", "#CQ2Option2", "#CQ2Option3", "#CQ2Option4"], false);
        	toggleQuestion(["#CQ2", "#CQ2Option1", "#CQ2Option2", "#CQ2Option3", "#CQ2Option4"], false);
		toggleQuestion(["#CQ3", "#CQ3Option1", "#CQ3Option2", "#CQ3Option3", "#CQ3Option4"], false);
		toggleQuestion(["#MQ1", "#MQ1Option1", "#MQ1Option2", "#MQ1Option3", "#M1Option4"], false);
		toggleQuestion(["#MQ2", "#MQ2Option1","#MQ2Option2", "#MQ2Option3", "#MQ2Option4"], false);
		toggleQuestion(["#MQ3", "#MQ3Option1", "#MQ3Option2", "#MQ3Option3", "#MQ3Option4"], false);
    	}
	else if (QNum == 2)
	{
		toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], false);
        	toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], false);
		toggleQuestion(["#PQ3", "#PQ3Option1", "#PQ3Option2", "#PQ3Option3", "#PQ3Option4"], true);
		toggleQuestion(["#CQ2", "#CQ2Option1", "#CQ2Option2", "#CQ2Option3", "#CQ2Option4"], false);
        	toggleQuestion(["#CQ2", "#CQ2Option1", "#CQ2Option2", "#CQ2Option3", "#CQ2Option4"], false);
		toggleQuestion(["#CQ3", "#CQ3Option1", "#CQ3Option2", "#CQ3Option3", "#CQ3Option4"], false);
		toggleQuestion(["#MQ1", "#MQ1Option1", "#MQ1Option2", "#MQ1Option3", "#M1Option4"], false);
		toggleQuestion(["#MQ2", "#MQ2Option1","#MQ2Option2", "#MQ2Option3", "#MQ2Option4"], false);
		toggleQuestion(["#MQ3", "#MQ3Option1", "#MQ3Option2", "#MQ3Option3", "#MQ3Option4"], false);
	}
	else if (QNum  == 3)
	{
		toggleQuestion(["#CQ2", "#CQ2Option1", "#CQ2Option2", "#CQ2Option3", "#CQ2Option4"], true);
        	toggleQuestion(["#CQ2", "#CQ2Option1", "#CQ2Option2", "#CQ2Option3", "#CQ2Option4"], false);
		toggleQuestion(["#CQ3", "#CQ3Option1", "#CQ3Option2", "#CQ3Option3", "#CQ3Option4"], false);
		toggleQuestion(["#MQ1", "#MQ1Option1", "#MQ1Option2", "#MQ1Option3", "#M1Option4"], false);
		toggleQuestion(["#MQ2", "#MQ2Option1","#MQ2Option2", "#MQ2Option3", "#MQ2Option4"], false);
		toggleQuestion(["#MQ3", "#MQ3Option1", "#MQ3Option2", "#MQ3Option3", "#MQ3Option4"], false);
		toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], false);
        	toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], false);
		toggleQuestion(["#PQ3", "#PQ3Option1", "#PQ3Option2", "#PQ3Option3", "#PQ3Option4"], false);
	}
	else if (QNum == 4)
	{
		toggleQuestion(["#CQ1", "#CQ1Option1", "#CQ1Option2", "#CQ1Option3", "#CQ1Option4"], false);
        	toggleQuestion(["#CQ2", "#CQ2Option1", "#CQ2Option2", "#CQ2Option3", "#CQ2Option4"], true);
		toggleQuestion(["#CQ3", "#CQ3Option1", "#CQ3Option2", "#CQ3Option3", "#CQ3Option4"], false);
		toggleQuestion(["#MQ1", "#MQ1Option1", "#MQ1Option2", "#MQ1Option3", "#M1Option4"], false);
		toggleQuestion(["#MQ2", "#MQ2Option1","#MQ2Option2", "#MQ2Option3", "#MQ2Option4"], false);
		toggleQuestion(["#MQ3", "#MQ3Option1", "#MQ3Option2", "#MQ3Option3", "#MQ3Option4"], false);
		toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], false);
        	toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], false);
		toggleQuestion(["#PQ3", "#PQ3Option1", "#PQ3Option2", "#PQ3Option3", "#PQ3Option4"], false);

	}
	else if (QNum == 5)
	{
		toggleQuestion(["#CQ1", "#CQ1Option1", "#CQ1Option2", "#CQ1Option3", "#CQ1Option4"], false);
        	toggleQuestion(["#CQ2", "#CQ2Option1", "#CQ2Option2", "#CQ2Option3", "#CQ2Option4"], false);
		toggleQuestion(["#CQ3", "#CQ3Option1", "#CQ3Option2", "#CQ3Option3", "#CQ3Option4"], true);
		toggleQuestion(["#MQ1", "#MQ1Option1", "#MQ1Option2", "#MQ1Option3", "#M1Option4"], false);
		toggleQuestion(["#MQ2", "#MQ2Option1","#MQ2Option2", "#MQ2Option3", "#MQ2Option4"], false);
		toggleQuestion(["#MQ3", "#MQ3Option1", "#MQ3Option2", "#MQ3Option3", "#MQ3Option4"], false);
		toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], false);
        	toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], false);
		toggleQuestion(["#PQ3", "#PQ3Option1", "#PQ3Option2", "#PQ3Option3", "#PQ3Option4"], false);
	}
	else if (QNum == 6)
	{
		toggleQuestion(["#MQ1", "#MQ1Option1", "#MQ1Option2", "#MQ1Option3", "#M1Option4"], true);
		toggleQuestion(["#MQ2", "#MQ2Option1","#MQ2Option2", "#MQ2Option3", "#MQ2Option4"], false);
		toggleQuestion(["#MQ3", "#MQ3Option1", "#MQ3Option2", "#MQ3Option3", "#MQ3Option4"], false);
		toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], false);
        	toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], false);
		toggleQuestion(["#PQ3", "#PQ3Option1", "#PQ3Option2", "#PQ3Option3", "#PQ3Option4"], false);
		toggleQuestion(["#CQ2", "#CQ2Option1", "#CQ2Option2", "#CQ2Option3", "#CQ2Option4"], false);
        	toggleQuestion(["#CQ2", "#CQ2Option1", "#CQ2Option2", "#CQ2Option3", "#CQ2Option4"], false);
		toggleQuestion(["#CQ3", "#CQ3Option1", "#CQ3Option2", "#CQ3Option3", "#CQ3Option4"], false);
	}
	else if (QNum == 7)
	{
		toggleQuestion(["#MQ1", "#MQ1Option1", "#MQ1Option2", "#MQ1Option3", "#M1Option4"], false);
		toggleQuestion(["#MQ2", "#MQ2Option1","#MQ2Option2", "#MQ2Option3", "#MQ2Option4"], true);
		toggleQuestion(["#MQ3", "#MQ3Option1", "#MQ3Option2", "#MQ3Option3", "#MQ3Option4"], false);
		toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], false);
        	toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], false);
		toggleQuestion(["#PQ3", "#PQ3Option1", "#PQ3Option2", "#PQ3Option3", "#PQ3Option4"], false);
		toggleQuestion(["#CQ2", "#CQ2Option1", "#CQ2Option2", "#CQ2Option3", "#CQ2Option4"], false);
        	toggleQuestion(["#CQ2", "#CQ2Option1", "#CQ2Option2", "#CQ2Option3", "#CQ2Option4"], false);
		toggleQuestion(["#CQ3", "#CQ3Option1", "#CQ3Option2", "#CQ3Option3", "#CQ3Option4"], false);

	}
	else if (QNum == 8)
	{
		toggleQuestion(["#MQ1", "#MQ1Option1", "#MQ1Option2", "#MQ1Option3", "#M1Option4"], false);
		toggleQuestion(["#MQ2", "#MQ2Option1","#MQ2Option2", "#MQ2Option3", "#MQ2Option4"], false);
		toggleQuestion(["#MQ3", "#MQ3Option1", "#MQ3Option2", "#MQ3Option3", "#MQ3Option4"], true);
		toggleQuestion(["#PQ1", "#PQ1Option1", "#PQ1Option2", "#PQ1Option3", "#PQ1Option4"], false);
        	toggleQuestion(["#PQ2", "#PQ2Option1", "#PQ2Option2", "#PQ2Option3", "#PQ2Option4"], false);
		toggleQuestion(["#PQ3", "#PQ3Option1", "#PQ3Option2", "#PQ3Option3", "#PQ3Option4"], false);
		toggleQuestion(["#CQ2", "#CQ2Option1", "#CQ2Option2", "#CQ2Option3", "#CQ2Option4"], false);
        	toggleQuestion(["#CQ2", "#CQ2Option1", "#CQ2Option2", "#CQ2Option3", "#CQ2Option4"], false);
		toggleQuestion(["#CQ3", "#CQ3Option1", "#CQ3Option2", "#CQ3Option3", "#CQ3Option4"], false);
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

#python code
from flask import Flask, request, jsonify
from flask_cors import CORS
from pyngrok import ngrok

app = Flask(_name_)
CORS(app)

@app.route('/main_code', methods = ['POST'])
def main_code() :
	data = request.get('answers')
	student_answers = data.get('answers')
	
    
public_url = ngrok.connect(5000)
print(f"Public URL : {public_url}")

# Run the Flask app
app.run(port=5000)
X=['B','B,'C','B','C','D','A','A','C']
for i in X:
   if(X[i]==student_answers[i]):
    print("correct")
  else:
   print("incorrect,the corect answer is",i)

