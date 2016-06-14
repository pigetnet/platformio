| /do/platformio/create                                |                                                                                                                                                                                                                                                               |
|:-----------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Info                                                 | [beta] [platformio] [init]                                                                                                                                                                                                                                    |
| Description                                          | Create an arduino sketch in /user/arduino                                                                                                                                                                                                                     |
| Usage                                                | /do/platformio/create folder                                                                                                                                                                                                                                  |
| Example                                              | /do/platformio/create blinkExample                                                                                                                                                                                                                            |
| Arguments                                            | 1:project_folder,                                                                                                                                                                                                                                             |
| Variables                                            | project_folder=$1, project_name=$(basename $project_folder),                                                                                                                                                                                                  |
| Modules                                              | cp /do/platformio/conf/arduino.ino /user/arduino/$project_folder/$project_name/$project_name.ino, cp /do/platformio/conf/gitignore /user/arduino/$project_folder/.gitignore, cp /do/platformio/conf/arduino.ini /user/arduino/$project_folder/platformio.ini, |
| System                                               | /system/makedir /user/arduino/$project_folder, /system/makedir /user/arduino/$project_folder/libraries, /system/makedir /user/arduino/$project_folder/$project_name,                                                                                          |
| 1. [PLATFORMIO] Create /user/arduino/$project_folder |                                                                                                                                                                                                                                                               |
| 1. Directory exists                                  |                                                                                                                                                                                                                                                               |

| /do/platformio/download                                        |                                                                                           |
|:---------------------------------------------------------------|:------------------------------------------------------------------------------------------|
| Info                                                           | [beta] [platformio] [update]                                                              |
| Description                                                    | Download sketch from github (by default pigetArduino)                                     |
| Usage                                                          | /do/platformio/download repo or /do/platformio/download username/repo                     |
| Example                                                        | /do/platformio/download radio2serial or /do/platformio/download pigetArduino/radio2serial |
| Arguments                                                      | 1:reponame,                                                                               |
| Variables                                                      | reponame=$1, username=${reponame%/*}, reponame=${reponame#*/},                            |
| System                                                         | /system/gitcloner $username/$reponame $projectDir,                                        |
| 1. [PLATFORMIO] Download $reponame --> /user/arduino/$reponame |                                                                                           |
| 1. Project already exists at /user/arduino/$reponame           |                                                                                           |

| /do/platformio/install                                                             |                                                                                                               |
|:-----------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------|
| Info                                                                               | [beta] [platformio] [install]                                                                                 |
| Description                                                                        | Install platformio                                                                                            |
| Usage                                                                              | /do/platformio/install                                                                                        |
| Softwares                                                                          | libmpc-dev, libelf1, libftdi1,                                                                                |
| Modules                                                                            | /do/platformio/update,                                                                                        |
| System                                                                             | /system/install libmpc-dev, /system/install libelf1, /system/install libftdi1, /system/makedir /user/arduino, |
| 1. [PLATFORMIO] Install                                                            |                                                                                                               |
| 1. This script is inspired by Russell Davis Tutorial $PICOLOR                      |                                                                                                               |
| 2. http://www.russelldavis.org/2015/08/01/platformio-on-the-raspberry-pi/ $PICOLOR |                                                                                                               |
| 3. Install dependencies                                                            |                                                                                                               |
| 7. Install platformio                                                              |                                                                                                               |

| /do/platformio/run      |                                                                                                                                                                                                |
|:------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Info                    | [beta] [platformio] [arduino]                                                                                                                                                                  |
| Description             | Compile and upload a sketch on an arduino                                                                                                                                                      |
| Usage                   | /do/platformio/run folder or /do/platformio/run folder (from /user/arduino) or /do/platformio/run folder port or /do/platformio/run folder port platform or /do/platformio/run folder platform |
| Example                 | /do/platformio/run radio2serial or /do/platformio/run /home/pi/blink or /do/platformio/run radio2serial /dev/ttyUSB1 nano or /do/platformio/run radio2serial nano                              |
| Arguments               | 1:dir,                                                                                                                                                                                         |
| Variables               | dir=$1, checkdev=$(dirname $2), checkdev=$(dirname $3), platform_name=$platform, port_name=$port,                                                                                              |
| 1. [UPLOAD] $dir        |                                                                                                                                                                                                |
| 1. $port_name           |                                                                                                                                                                                                |
| 2. $platform_name       |                                                                                                                                                                                                |
| 3. Folder doesnt exists |                                                                                                                                                                                                |

| /do/platformio/runNano   |                                                                                                                                  |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------------|
| Info                     | [beta] [platformio] [arduino]                                                                                                    |
| Description              | Compile and upload a sketch on an arduino nano                                                                                   |
| Usage                    | /do/platformio/runNano folder or /do/platformio/runNano folder (from /user/arduino) or /do/platformio/runNano folder port        |
| Example                  | /do/platformio/runNano radio2serial or /do/platformio/runNano /home/pi/blink or /do/platformio/runNano radio2serial /dev/ttyUSB1 |
| Modules                  | /do/platformio/run $@ "nano",                                                                                                    |

| /do/platformio/runUno   |                                                                                                                               |
|:------------------------|:------------------------------------------------------------------------------------------------------------------------------|
| Info                    | [beta] [platformio] [arduino]                                                                                                 |
| Description             | Compile and upload a sketch on an arduino nano                                                                                |
| Usage                   | /do/platformio/runUno folder or /do/platformio/runUno folder (from /user/arduino) or /do/platformio/runUno folder port        |
| Example                 | /do/platformio/runUno radio2serial or /do/platformio/runUno /home/pi/blink or /do/platformio/runUno radio2serial /dev/ttyUSB1 |
| Modules                 | /do/platformio/run $@ "uno",                                                                                                  |

| /do/platformio/test                     |                                                                               |
|:----------------------------------------|:------------------------------------------------------------------------------|
| Info                                    | [alpha] [platformio] [arduino] [test] [python]                                |
| Description                             | Run a python test                                                             |
| Usage                                   | /do/platformio/test folder or /do/platformio/test folder (from /user/arduino) |
| Example                                 | /do/platformio/test /home/pi/nrftest or /do/platformio/test nrftest           |
| Arguments                               | 1:dir,                                                                        |
| Variables                               | dir=$1,                                                                       |
| 1. No test founded at $dir/test/test.py |                                                                               |

| /do/platformio/update   |                              |
|:------------------------|:-----------------------------|
| Info                    | [beta] [platformio] [update] |
| Description             | Update platformio            |
| Usage                   | /do/platformio/update        |
| 1. [PLATFORMIO] Update  |                              |

