 marcin-ch /
STM32F469_TouchGFX_Valentines_Day_Heart 

![0_32F469IDISCOVERY_promo_853x465.png](/doc/github_readme_images/0_32F469IDISCOVERY_promo_853x465.png)

# Overview
This is a basic example of using [TouchGFX](https://www.st.com/en/embedded-software/x-cube-touchgfx.html) graphical framework optimized for STM32 microcontrollers. The evaluation board is STM32F469 Discovery kit (part number [32F469IDISCOVERY](https://www.st.com/en/evaluation-tools/32f469idiscovery.html)).

GUI (Graphical User Interface) contains simple text and animated image to imitate beating heart. To see the final result, please scroll down to the end of this page.

Creating GUI has been done in TouchGFX Designer which is part of TouchGFX, further details [here](https://support.touchgfx.com/4.18/docs/introduction/what-is-touchgfx). Afterwards, code generated by TouchGFX Designer has been opened in STM32CubeIDE and then built and flashed to the board. This approach allows you to update the project with changes not achievable within TouchGFX Designer, such as pins/clocks configuration and so on.

# Hardware
* STM32F469 Discovery kit (part number [32F469IDISCOVERY](https://www.st.com/en/evaluation-tools/32f469idiscovery.html))

# Software
* [TouchGFX](https://www.st.com/en/embedded-software/x-cube-touchgfx.html) 4.18.1 Designer
* [STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html) 1.8.0
* STM32Cube MCU Package for STM32F4 1.26.2 (relevant files will be populated automatically during creating project in TouchGFX Designer so this is transparent for the user)

# Workflow
## 🧾 Working with project in TouchGFX Designer
1. Install TouchGFX as follows (for more details please see TouchGFX installation [guide](https://support.touchgfx.com/4.18/docs/introduction/installation))
    * download [TouchGFX](https://www.st.com/en/embedded-software/x-cube-touchgfx.html)
      * it comes as *.zip* file
    * install *Utilities/PC_Software/TouchGFXDesigner/TouchGFX-4.18.1.msi*
      * all settings default
    * TouchGFX Designer (in my case TouchGFX **4.18.1** Designer) should be available on your Desktop now
2. Run TouchGFX Designer and create new project
    * hit **Create New** and choose evaluation board you will be working on, in my case STM32F469 Discovery kit (part number [32F469IDISCOVERY](https://www.st.com/en/evaluation-tools/32f469idiscovery.html))
    *  choose applications details as stated in the picture below and hit **Create**<br>
![1_TouchGFX_create_project.png](/doc/github_readme_images/1_TouchGFX_create_project.png)
3. Change screen name to *MainScreen* by double-clicking the default name on the left hand side
4. Add background using **Tiled Image** and resize it to cover whole canvas<br>
![2_TouchGFX_add_background_resized.png](/doc/github_readme_images/2_TouchGFX_add_background_resized.png)
    * change default name to *background*
    * change **Style** to *White Leather*<br>
![3_TouchGFX_modify_background.png](/doc/github_readme_images/3_TouchGFX_modify_background.png)
5. Add text
    * choose **Text Area** widget and change its properties as follows<br>
![4_TouchGFX_add_text.png](/doc/github_readme_images/4_TouchGFX_add_text.png)
6. **Run Simulator** to check how applications looks like<br>
![5_TouchGFX_run_simulator.png](/doc/github_readme_images/5_TouchGFX_run_simulator.png)
7. **Run Target** to flash the board directly from TouchGFX Designer (seems that this option requires [STM32CubeProgrammer](https://www.st.com/en/development-tools/stm32cubeprog.html) installed in default install location: *C:/Program Files/STMicroelectronics/STM32Cube/STM32CubeProgrammer*)<br>
![6_TouchGFX_run_target.png](/doc/github_readme_images/6_TouchGFX_run_target.png)

## 🧾 Keep working with project in STM32CubeIDE
1. Install STM32CubeIDE as follows
    * download [STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html)
      * it comes as *.zip* file
    * all installation settings default
    * STM32CubeIDE (in my case STM32CubeIDE **1.8.0**) should be available on your Desktop now
2. Go to *C:/TouchGFXProjects/Valentines_Day_Heart/STM32CubeIDE* and open *.project* (I have this file associated with STM32CubeIDE therefore double-click opens STM32CubeIDE straight away)
    * I have seen this method in one of ST tutorial, tested on my end and works like a charm
    * importing projects into STM32CubeIDE could be painful so let's make our lives as easy as possible
3. You will be prompted to define workspace's name, you can leave as it is
    * **please be advised**, you are working on files from *C:/TouchGFXProjects/Valentines_Day_Heart* (this is directory defined during creating project in TouchGFX Designer), i.e. project files have not been copied into the workspace
4. Hit hummer icon to build the project<br>
![8_STM32CubeIDE_build_project.png](/doc/github_readme_images/8_STM32CubeIDE_build_project.png)
5. Hit debug icon to flash and debug the board (once flashing is done, hit `Ctrl`+`F2` to terminate the debug session)<br>
![9_STM32CubeIDE_debug_project.png](/doc/github_readme_images/9_STM32CubeIDE_debug_project.png)
6. Application should be now up and running and you should see red text *Happy Valentine's Day!* on almost white background. 

## 🧾 Update project
1. Go back to TouchGFX Designer
2. Add **Animated Image** and adjust its properties
    * change default name to *heart_beating*
    * pick the images to be used as first and last in animation
      * they are provided in */doc* folder (*first.png* and *last.png*)
    * select **Loop Animation** to keep it looping forever
    * adjust **Update interval (ms)** to 600ms (this is totally random value and it has nothing with real human's pulse)
    * all should look like below
![11_TouchGFX_add_modify_animated_image.png](/doc/github_readme_images/11_TouchGFX_add_modify_animated_image.png)
3. Hit **Generate Code** to update the code for STM32CubeIDE<br>
![7_TouchGFX_generate_code.png](/doc/github_readme_images/7_TouchGFX_generate_code.png)
4. Go to STM32CubeIDE, project update should be done automatically, just hit debug icon, once flashing is done hit `Ctrl`+`F2` to terminate the debug session
    * if some reason application is not changed, hit `F5` to refresh the project and then hit debug icon and `Ctrl`+`F2` again

# Summary
![12_heart_beating.gif](/doc/github_readme_images/12_heart_beating.gif)

GUI application for Valentine's Day is up and running and even without touching code, what a magic!

## Remarks:
Tools used to create graphics and animation:
1. [GIMP](https://www.gimp.org/)
2. [Figma](https://www.figma.com)
3. [video to gif online tool](https://ezgif.com/video-to-gif) (movie recorded with phone (*.mp4*) and then converted to *.gif* with resizing to 480 pixels in width)

## How to use this repo (source code)
1. Clone the repo or download as *.zip* to your local disc drive
    * when clonning please use below command:
    ```console
    git clone https://github.com/marcin-ch/STM32F469_TouchGFX_Valentines_Day_Heart.git
    ```
2. Open */TouchGFX/Valentines_Day_Heart.touchgfx* (it should be opened in TouchGFX Designer)
3. Hit **Generate Code** to update the code for STM32CubeIDE<br>
![7_TouchGFX_generate_code.png](/doc/github_readme_images/7_TouchGFX_generate_code.png)
    * it creates pretty heavy content, for example *Middlewares/ST/touchgfx* (>180MB), therefore it is not possible to push all the code to this repo
    * hope that next versions of the TouchGFX will be backward compatible to be able to use this repo in the same manner 
4. Open */STM32CubeIDE/.project* (it should be opened in STM32CubeIDE)
5. Hit **Run** -> **Debug As** -> **STM32 Cortex-M C/C++ Application**, wait a while, once flashing is done hit `Ctrl`+`F2` to terminate the debug session, the appliacation should be up and running

## How to use this repo (binary file)
~~If you just want to check how the project looks like running on the board, you can flash binary file available in */doc/STM32F469I-DISCO.bin*. As STM32F469 Discovery kit enumerates as MSD (Mass Storage Device) when connected to PC through USB cable, you can simply drag-n-drop binary file to your board. Wait few moments when flashing is in progress, reset the board and you should see application working.~~

Generated *.bin* file is suprisingly large (>2GB!), perhaps it is some bug, I could not find any quick solution for that.
![13_STM32CubeIDE_convert_to_bin.png](/doc/github_readme_images/13_STM32CubeIDE_convert_to_bin.png)