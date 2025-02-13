# day_24
// TODO-лист для задач
//https://www.mycompiler.io/view/A6djGkFzeok
const toDoList = {
  list: [
{name: 'Сделать зарядку', status: 'To Do', priority: 'low'},
{name: 'Написать код', status: 'In progress', priority: 'high'},
{name: 'Прочитать книгу', status: 'Done', priority: 'medium'},
{name: 'Сделать задания', status: 'In progress', priority: 'high'},
{name: 'Ремонт автомобиля', status: 'To Do', priority: 'medium'},
],

  showList () {
     console.log('СПИСОК ЗАДАЧ: название, статус, приоритет');
         this.list.forEach(task => {
          console.log(`'${task.name}':'${task.status}':'${task.priority}'`)
      });
  },
  addTask (taskName, taskStatus, taskPriority) {
      this.list.push({name:taskName, status:taskStatus, priority:taskPriority });
        console.log ( `Задача: '${taskName}, ${taskStatus}, ${taskPriority}' добавлена!`)
  },
  deleteTask(taskName) {
    const massiveLength = this.list.length;
    this.list = this.list.filter(task => task.name !== taskName);

    if (this.list.length < massiveLength) {
      console.log(`Задача '${taskName}' удалена!`);
    } else {
      console.log(`Задача '${taskName}' не найдена!`);
    }
  },
  checkStatus(taskName) {
    const task = this.list.find(task => task.name === taskName);
      if (task) {
        console.log(`Задача '${taskName}' имеет статус: '${task.status}'`);
      } else {
        console.log(`Задача '${taskName}' не найдена!`);
      }
    }
}

toDoList.showList();
toDoList.addTask('Купить продукты', 'To Do', 'medium');
toDoList.addTask('Выучить 10 английских слов', 'To Do', 'high');
toDoList.deleteTask('Написать код');
toDoList.checkStatus('Ремонт автомобиля');
toDoList.deleteTask('Сделать задания');
