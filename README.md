# SemiHosting_ac6_Workbench

![SemiHosting](https://github.com/sinadarvi/SemiHosting_ac6_Workbench/blob/master/semihosting_Slider.jpg)
using printf() and scanf() function without any interface!!


if you remember, I taught you a way to use printf() function by UART interface, but how we can use printf() and scanf() without any interface ???

first you should get to know with SemiHosting, Semihosting is a neat way to redirect STDOUT and STDIN from an embedded system to a debug window on a PC. This allows you to output messages using printf functions without having to use/configure an RS232 or USB Virtual COM Port, and can also read input from the PC's keyboard via scanf functions.But how??

for simplicity we assume i made a project in ac6 and then i just go in the debugger Configuration i had made for my debug mode and then in "Startup" tab i add these like this picture below :

    monitor arm semihosting enable

![StartUp_tab](https://github.com/sinadarvi/SemiHosting_ac6_Workbench/blob/master/semihosting_startup_tab.jpg)
after that we should add Project, Properties, C/C++ Build, Settings, MCU GCC Linker, Miscellaneous, Linker flags like this : 

    -specs=nosys.specs -specs=nano.specs -specs=rdimon.specs -lc -lrdimon

![Miscellaneous](https://github.com/sinadarvi/SemiHosting_ac6_Workbench/blob/master/semihosting_ms.jpg)
and then you can just simply look at my main.c code that you can see above and then you can use this function to do as like this.
and then your result would be like this :
(printf and SD_printf from [SD_HAL_UART Library](https://github.com/sinadarvi/SD_HAL_UART))
![printf - SD_printf](https://github.com/sinadarvi/SemiHosting_ac6_Workbench/blob/master/semihosting_printf.jpg)

(and scanf and printf together )
![scanf](https://github.com/sinadarvi/SemiHosting_ac6_Workbench/blob/master/semihosting_scanf.jpg)

here we are !! and you can see this is very easy but so helpful...
Have Good Day ;)
