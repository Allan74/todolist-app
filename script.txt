const taskInput = document.getElementById('taskInput');
const addTaskBtn = document.getElementById('addTaskBtn');
const taskList = document.getElementById('taskList');

// Add a task
addTaskBtn.addEventListener('click', () => {
  const taskText = taskInput.value.trim();

  if (taskText) {
    const li = document.createElement('li');
    li.innerHTML = `
      <span>${taskText}</span>
      <input type="checkbox" class="completeTask">
    `;

    taskList.appendChild(li);
    taskInput.value = '';

    // Mark task as complete
    const checkbox = li.querySelector('.completeTask');
    checkbox.addEventListener('change', () => {
      if (checkbox.checked) {
        li.classList.add('completed');
      } else {
        li.classList.remove('completed');
      }
    });
  }
});

