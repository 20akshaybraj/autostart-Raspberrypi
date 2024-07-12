# Autostart a Python Script on Booting a Raspberry Pi
This repository provides a comprehensive guide on how to automatically run a Python script when a Raspberry Pi boots up. Automating the execution of a Python script on boot is a common requirement for projects involving Raspberry Pi. Whether you're developing a home automation system, a monitoring tool, or any other application, ensuring your script runs on boot can enhance reliability and reduce manual intervention.

## Setup

1. The first step is to create a directory named "autostart" in the ".config" directory. If not able to navigate to the ".config" directory, then right click on the mouse and click "show hidden". Now you will be able to locate the ".config" directory.
2. For scripts that require a virtual environment, create a file inside the autostart directory with any name you like, but it must end in ".desktop". Refer to the [aurostart_code.desktop]([www.google.com](https://github.com/20akshaybraj/python-autostart-on-raspberrypi/blob/main/autostart_code.desktop)) for the contents of the file. The second line of the file is:

    ```sh
    Exec=sudo bash /path/to/your/run_reboot.sh
    ```
    
    you can alter the given path to your path to the run_reboot.sh file in your raspberry pi.

3. For scripts that do not require a virtual environment and all the necessary modeules are installed outside the virtual environment, follow the same step of creating a file inside the autostart directory with any name you like, but it must end in ".desktop". Replace the second line of the file with the below line of code:

    ```sh
    Exec=python3 /path/to/your/python_script.py
    ```
    
    Save the file and then reboot the raspberry pi. The autorun must work.
    
4. For scripts that require a virtual environment, create a new file with any name you like, but it must end in ".sh" in the home. Refer to the [run_reboot.sh](https://github.com/20akshaybraj/python-autostart-on-raspberrypi/blob/main/run_reboot.sh) for the contents of the file. The first line of the file must be:

    ```sh
    #!/bin/bash
    ```
    
    followed by this you can write all the commands that you need to execute on the terminal to run your program say activating the virtual environmnet, and then running your python script.

   Example
   
    ```sh
    source /path/to/environment/bin/activate
    cd /path/to/python_script/directory
    python3 python_script.py
    ```

    Save the file and then reboot the raspberry pi. The autorun must work with activating the virtual environment.

5. For running multiple python scripts parallelly you can use the & operator in the terminal.

   Example

    ```sh
    python3 python_script1.py &
    python3 python_script2.py &
    ```
   
   
