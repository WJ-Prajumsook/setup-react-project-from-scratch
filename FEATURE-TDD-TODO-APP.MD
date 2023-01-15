# My Todo App with TDD

Table of Contents:
- [Topics](#topics)
- [User Stories](#user-stories)
  - [A view to login](#a-view-to-login)
  - [A view to signup](#a-view-to-signup)
  - [A view to see all tasks](#a-view-of-all-tasks)
  - [A view to see in progress tasks](#a-view-of-in-progress-tasks)
  - [A view to see completed tasks](#a-view-of-completed-tasks)
  - [A view to see today's tasks](#a-view-of-today-tasks)
  - [A view to see tomrrow's tasks](#a-view-of-tomorrow-tasks)
  - [A view to see this month's tasks](#a-view-of-this-month-tasks)
  - [A view to add task](#a-view-to-add-a-task)
  - [A view to edit task](#a-view-to-edit-a-task)
  - [A view to delete task](#a-view-to-delete-a-task)

## `Topics`
- A view to login
- A view to signup
- A view of My All Tasks
- A view of In Progress Tasks
- A view of Completed Tasks
- A view of Today Tasks
- A view of Tomorrow Tasks
- A view of This month Tasks
- A view to add a Task
- A view to edit a Task
- A view to delete a Task

## `User stories`

### `A view to login`
As a user, I have the following requirements:
- Given that I navigate to http://...., I want to see a form to put
in the username and password.
- Given that I tapped on the "Login" button, I want to be navigated to my to-do items list page.
- Given that I don't have an account and I want to register, I want to be navigated to signup page when I tapped on the "Signup" link.

### `A view to signup`
As a user, I have the following requirements:
- Given that I navigate to Signup page, I want to see a form to put in the username, email, password and confirm password.
- I want to be navigated to login page when I tapped on the "Sign up" button so that I can login.
- I want to go back to Login page when I tapped on "Login" link.

### `A view of all tasks`
As a logged in user, I have the following requirements:
- Given that I logged in, I want to see a list of all tasks.
- I want to add a task to the list.

### `A view of in progress tasks`
As a logged in user, I have the following requirements:
- I have tapped the menu(In Progress) and I want to see a list of all in progress tasks.

### `A view of completed tasks`
As a logged in user, I have the following requirements:
- I have tapped the menu(Completed) and I want to see a list of all completed tasks.

### `A view of today tasks`
As a logged in user, I have the following requirements:
- I have tapped the menu(Today) and I want to see a list of all todays tasks.

### `A view of tomorrow tasks`
As a logged in user, I have the following requirements:
- I have tapped the menu(Tomorrow) and I want to see a list of all tomorrows tasks.

### `A view of this month tasks`
As a logged in user, I have the following requirements:
- I have tapped the menu(Month) and I want to see a list of all this months tasks.

### `A view to add a task`
As a logged in user, I have the following requirements:
- Given that I tapped the add (+) button, I want to see a form to put in the details of a task item (Title, Description and Date).
- I want to add a task item to the list of tasks by tapping on the "Add New Task" button.

### `A view to edit a task`
As a logged in user, I have the following requirements:
- Given that I tapped the edit button in the task, I want to see a form with task details so that I can make changes.
- I want to save chages by tapping on the "Save Task" button.

### `A view to delete a task`
As a logged in user, I have the following requirements:
- Given that I tapped the delete button in the task, I want to see a confirmation so that I can cancel or continue delete a task.
- I want to close the confirmation when I tapped on cancel button.
- I want to delete task from the list when I tapped on delete button.
