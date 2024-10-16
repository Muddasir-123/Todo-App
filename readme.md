const taskInput = document.getElementById('taskInput');
const addTaskBtn = document.getElementById('addTaskBtn');
const taskList = document.getElementById('taskList');

addTaskBtn.addEventListener('click', () => {
    const taskText = taskInput.value;
    if (taskText !== '') {
        const listItem = document.createElement('li');
        listItem.textContent = taskText;

        const deleteBtn = document.createElement('button');
        deleteBtn.textContent = 'Delete';
        deleteBtn.addEventListener('click', () => {
            listItem.remove();
        });

        listItem.appendChild(deleteBtn);
        taskList.appendChild(listItem);

        taskInput.value = '';
    }
});

taskList.addEventListener('click', (event) => {
    if (event.target.tagName === 'LI') {
        event.target.classList.toggle('completed');
    }
});


.container {
    text-align: center;
    margin: 20px;
}

input {
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
}

button {
    padding: 10px 20px;
    background-color: #4CAF50;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

ul {
    list-style: none;
    padding: 0;
}

li {
    margin: 10px 0;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
    width:80%;
}

.completed {
    text-decoration: line-through;
    opacity: 0.7;
}