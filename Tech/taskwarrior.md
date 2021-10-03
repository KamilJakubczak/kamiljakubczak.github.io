# Taskwarrior


## Basic management

* task all                      - show all tasks
* task add 'message'            - add task
* task [id] done                - marks task as done
* task [id] delete              - deletes the task
* task edit
* task [id] info
* task undo
* task [id] purge               - total deletion

### Timetracking
* task [id] start
* task [id] stop


## Meta data for tasks

### Contexts

* task context define work project:work
* task context define fun project:fun or fun

### Tags

* task add +home +work         - add tag home and work to task
* task [id] mod -work           - remove tag work from task


### Projects

* task add project:Home test    - add a project with task
* task add project:Home.Fix     - add a sub project with task

### Priority

Only values H, M, L and empty

* task add pri:H                - add a task with high priority 

### Annotations

* task add Buy the milk
* task [id] annotate Buy milk in the shop

### Dates

* due date
* scheduled date    - the earliest opportunity to do the task
* wait data         - hides a task from task list until the date
* until date        - after which date the task will be irrelevant and deketed
