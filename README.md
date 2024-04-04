
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Grades Calculator</title>
    <style>
        body {
            font-family: fantasy;
            text-align: center;
            background-image: url("https://i.pinimg.com/736x/c3/f3/83/c3f3831034bebcb0ae6b4c29422bd293.jpg");
            background-repeat: no-repeat;
            background-size: cover;
            color: black;
           
           
        }
        .input-container {
            margin-bottom: 10px;
        }
        .input-label {
            display: inline-block;
            width: 200px;
        }
        .input-field {
            margin-left: 10px;
        }
        #total-grade {
            font-weight: bold;
        }
        
        
    </style>
</head>
<body>
    <h1>Grades Calculator</h1>
    <form id="grade-form">
        <div class="input-container">
            <label class="input-label" for="student-number">Student Number:</label>
            <input class="input-field" type="text" id="student-number" required>
        </div>
        <div class="input-container">
            <label class="input-label" for="student-name">Student Name:</label>
            <input class="input-field" type="text" id="student-name" required>
        </div>
        <div class="input-container">
            <label class="input-label" for="quiz">Quiz:</label>
            <input class="input-field" type="number" id="quiz" min="0" max="100" step="0.1" required>
        </div>
        <div class="input-container">
            <label class="input-label" for="recitation">Recitation:</label>
            <input class="input-field" type="number" id="recitation" min="0" max="100" step="0.1" required>
        </div>
        <div class="input-container">
            <label class="input-label" for="long-test">Long Test:</label>
            <input class="input-field" type="number" id="long-test" min="0" max="100" step="0.1" required>
        </div>
        <div class="input-container">
            <label class="input-label" for="project">Project:</label>
            <input class="input-field" type="number" id="project" min="0" max="100" step="0.1" required>
        </div>
        <div class="input-container">
            <label class="input-label" for="attendance">Attendance:</label>
            <input class="input-field" type="number" id="attendance" min="0" max="100" step="0.1" required>
        </div>
        <div class="input-container">
            <label class="input-label" for="exam">Exam:</label>
            <input class="input-field" type="number" id="exam" min="0" max="100" step="0.1" required>
        </div>
        <button type="button" id="calculate-btn">Calculate Total Grade</button>
    </form>
    <div id="result">
        <p>1st Semester Grade:</p>
        <p id="total-grade"></p>
    </div>
    <script>
        const form = document.getElementById("grade-form");
        const calculateBtn = document.getElementById("calculate-btn");
        const totalGradeEl = document.getElementById("total-grade");
    
        calculateBtn.addEventListener("click", () => {
            const quiz = parseFloat(document.getElementById("quiz").value) * 0.1;
            const recitation = parseFloat(document.getElementById("recitation").value) * 0.15;
            const longTest = parseFloat(document.getElementById("long-test").value) * 0.15;
            const project = parseFloat(document.getElementById("project").value) * 0.35;
            const attendance = parseFloat(document.getElementById("attendance").value) * 0.05;
            const exam = parseFloat(document.getElementById("exam").value) * 0.20;
    
            const totalGrade = quiz + recitation + longTest + project + attendance + exam;
            const totalGradePercentage = (totalGrade).toFixed(2)   + "%";
            totalGradeEl.textContent = totalGradePercentage;
        });
    </script>
    
</body>
</html>
