## In Ansible, if one of task failes..it fail in that task step itself..it will not go to the next task

- we can handle this using **ignore_error = yes**
- if i give this command in playbook, eventhough some error in the step it will ignore the step and continue to run the other tasks.

- we can also use the error based runs
- let say i have 2 task, if one of the task is check the docker is installed or not..if not in the next step install the docker..
- for this in step 1, we can use **ignore_error = yes** to ignore the error and we can store the output of the task in register **register: output**.
- in the 2nd step, u can use when -- > output.failed == true
- in this output we have json structure, in that we have failed value that shows whether it is passed or not.based on the condition we can run the 2ns step.

- ignore specific error using **failed_when**
- store the result in result check for the specific error