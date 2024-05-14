Here's a basic documentation for your To-Do List project:

---

# To-Do List

A simple web application to manage your daily tasks.

## Table of Contents

- [Description](#description)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Credits](#credits)
- [License](#license)

## Description

The To-Do List web application allows users to add, remove, and mark tasks as completed. It provides a simple and intuitive interface for managing tasks effectively.

## Features

- Add tasks: Enter a task description and click the "Add" button to add it to the list.
- Remove tasks: Click on the task to remove it from the list.
- Mark tasks as completed: Click on a task to toggle its completion status.

  HTML

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ToDoList</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">

        <div class="todoapp">
            <h2>To-Do List <img src="images/icon.png"> </h2>
            <div class="row">
                <input type="text" id="input-box" placeholder="add your text">
                <button onclick="addTask()">Add</button>
            </div>
            <ul id="list-Container">
                <!-- <li class="checked">Task 1</li>
                <li>Task 2</li>
                <li>Task 3</li> -->
            </ul>
        </div>

    </div>
    <script src="script.js"></script>
</body>
</html>

CSS 

*{
    margin: 0;
    padding: 0;
    font-family: 'Poppins', sans-serif;
    box-sizing: border-box;
}
.container{
    width: 100%;
    min-height: 100vh;
    background: linear-gradient(135deg, #153677, #4e085f);
    padding: 10px;
}
.todoapp{
    width: 100%;
    max-width: 540px;
    background: #fff;
    margin: 100px auto 20px;
    padding: 40px 30px 70px;
    border-radius: 10px;
}
.todoapp h2{
    color: #002765;
    display: flex;
    align-items: center;
    margin-bottom: 20px;
}
.todoapp h2 img{
    width: 30px;
    margin-left: 10px;
}
.row{
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: #edeef0;
    border-radius: 30px;
    padding-left: 20px;
    margin-bottom: 25px;
}
input{
    flex: 1;
    border: none;
    outline: none;
    background: transparent;
    padding: 10px;
}
button{
    border: none;
    outline: none;
    padding: 16px 50px;
    background: #ff5954;
    color: #fff;
    font-size: 16px;
    cursor: pointer;
    border-radius: 40px;
}
ul li {
    list-style: none;
    font-size: 17px;
    padding: 12px 8px 12px 50px;
    user-select: none;
    cursor: pointer;
    position: relative;
}
ul li::before{
    content: ' ';
    position: absolute;
    height: 28px;
    width: 28px;
    border-radius: 50px;
    background-image: url(images/unchecked.png);
    background-size: cover;
    background-position: center;
    top: 12px;
    left: 8px;
}
ul li.checked{
    color: #555;
    text-decoration: line-through;
}
ul li.checked::before{
    background-image: url(images/checked.png);
}
ul li span {
    position: absolute;
    right: 0;
    top: 5px;
    width: 40px;
    height: 40px;
    font-size: 22px;
    color:#555;
    line-height: 40px;
    text-align: center; 
    border-radius: 50%;
}
ul li span:hover{
    background: #edeef0;
}

Javascript

const inputBox = document.getElementById("input-box");
const listContainer = document.getElementById("list-Container");

function addTask(params) {
    if(inputBox.value === ''){
        alert("you must write something!");
    }
    else{
        let li = document.createElement('li');
        li.innerHTML = inputBox.value;
        listContainer.appendChild(li);

        let span = document.createElement("span");
        span.innerHTML = "\u00d7";
        li.appendChild(span);
    }
    inputBox.value = '';
    saveData();
}

listContainer.addEventListener("click", function(e){
    if(e.target.tagName === "LI"){
        e.target.classList.toggle("checked");
        saveData();
    }
    else if(e.target.tagName === "SPAN"){
        e.target.parentElement.remove();
        saveData();
    }
}, false);

function saveData() {
    localStorage.setItem("data", listContainer.innerHTML);
}
function showTask() {
    listContainer.innerHTML = localStorage.getItem("data");
}
showTask();

## Installation

1. Clone the repository or download the source code.
2. Open the `index.html` file in your web browser.

## Usage

1. Enter a task description in the input field.
2. Click the "Add" button to add the task to the list.
3. Click on a task to mark it as completed. Click again to undo.
4. Click on the "×" button next to a task to remove it from the list.
5. Your tasks will be saved locally in your browser's storage, so they will persist even after closing the browser.

## Credits

This project was created by Hussain ksmd.

## License

This project is licensed under the [MIT License].

---
## Potential updates

This project has room for upadate like
-
1) Can add the editing option after the task is added.
2) Can add the date feature in the task.
3) Insted of using Browser local storage can use database.
4) Can give the sign-up and login page for this program.
5) Can transform this To-Do list into Goal tracking program.
6) Can provide the remainder for the task deadlines.
