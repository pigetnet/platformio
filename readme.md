| /do/platformio/create   |                                           |
|:------------------------|:------------------------------------------|
| Description             | Create an arduino sketch in /user/arduino |
| Example                 | /do/platformio/create blinkExample        |
| Info                    | [beta] [platformio] [init]                |
| Arguments               | 1:project_folder,                         |

| /do/platformio/download   |                                                                                           |
|:--------------------------|:------------------------------------------------------------------------------------------|
| Description               | Download sketch from github (by default pigetArduino)                                     |
| Example                   | /do/platformio/download radio2serial or /do/platformio/download pigetArduino/radio2serial |
| Info                      | [beta] [platformio] [update]                                                              |
| Arguments                 | 1:reponame,                                                                               |

| /do/platformio/install   |                               |
|:-------------------------|:------------------------------|
| Description              | Install platformio            |
| Info                     | [beta] [platformio] [install] |

| /do/platformio/run   |                                                                                                                                                                   |
|:---------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Description          | Compile and upload a sketch on an arduino                                                                                                                         |
| Example              | /do/platformio/run radio2serial or /do/platformio/run /home/pi/blink or /do/platformio/run radio2serial /dev/ttyUSB1 nano or /do/platformio/run radio2serial nano |
| Info                 | [beta] [platformio] [arduino]                                                                                                                                     |
| Arguments            | 1:dir,                                                                                                                                                            |

| /do/platformio/runNano   |                                                                                                                                  |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------------|
| Description              | Compile and upload a sketch on an arduino nano                                                                                   |
| Example                  | /do/platformio/runNano radio2serial or /do/platformio/runNano /home/pi/blink or /do/platformio/runNano radio2serial /dev/ttyUSB1 |
| Info                     | [beta] [platformio] [arduino]                                                                                                    |

| /do/platformio/runUno   |                                                                                                                               |
|:------------------------|:------------------------------------------------------------------------------------------------------------------------------|
| Description             | Compile and upload a sketch on an arduino nano                                                                                |
| Example                 | /do/platformio/runUno radio2serial or /do/platformio/runUno /home/pi/blink or /do/platformio/runUno radio2serial /dev/ttyUSB1 |
| Info                    | [beta] [platformio] [arduino]                                                                                                 |

| /do/platformio/test   |                                                                     |
|:----------------------|:--------------------------------------------------------------------|
| Description           | Run a python test                                                   |
| Example               | /do/platformio/test /home/pi/nrftest or /do/platformio/test nrftest |
| Info                  | [alpha] [platformio] [arduino] [test] [python]                      |
| Arguments             | 1:dir,                                                              |

| /do/platformio/update   |                              |
|:------------------------|:-----------------------------|
| Description             | Update platformio            |
| Info                    | [beta] [platformio] [update] |

