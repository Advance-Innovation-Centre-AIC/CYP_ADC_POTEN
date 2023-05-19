# On board potentiometer ADC read

# This is hardware command for easy use

This is a minimal starter application for Infineon MCU devices.
which include

- CY8CKIT-062s2-43012
- CY8CKIT-028-SENSE.
## Requirements
- [ModusToolbox™ software](https://www.infineon.com/modustoolbox) v3.0 or later (tested with v3.0)
- CY8CKIT-062s2-43012
- CY8CKIT-028-SENSE.
- Programming language: C
- Associated parts: All [PSoC™ 6 MCU](https://www.infineon.com/cms/en/product/microcontroller/32-bit-psoc-arm-cortex-microcontroller/psoc-6-32-bit-arm-cortex-m4-mcu) parts, [XMC7000 MCU](https://www.infineon.com/cms/en/product/microcontroller/32-bit-industrial-microcontroller-based-on-arm-cortex-m/), and [AIROC™ CYW20829 Bluetooth® LE SoC](https://www.infineon.com/cms/en/product/promopages/airoc20829)
## Supported toolchains (make variable 'TOOLCHAIN')
- GNU Arm® embedded compiler v10.3.1 (`GCC_ARM`) - Default value of `TOOLCHAIN`
- Arm® compiler v6.16 (`ARM`)
- IAR C/C++ compiler v9.30.1 (`IAR`)
## ADC read functions

These functions will use the ADC to read the potentiomete on CY8CKIT-062S2043012 following this

**poten_read()**

Read the potrntiometer on CY8CKIT board

## How to use

Import this application to your modus project and go to file main.c
BSP and device are already configured all you need is to program your function in main() under for;; loop.

For example, the following code is to read the potentiometer value and print it on OLED.


        for (;;)
        {
           
            //read value from potentiometer and display on OLED
            microVolts = poten_read();
            char stringBuffer[20];
            sprintf(stringBuffer, "%ld\r\n", microVolts);
            oled_print_top(stringBuffer);
            Cy_SCB_UART_PutString(UART_HW, stringBuffer);
            Cy_SysLib_Delay(100);
        }

when you finish writing your code go to

- Build Application
- wait for your program to finish building
- go to Launch > [Your app name] debug (KitProg3_Miniprog4)

you should see the value of potentiometer shpwing on the OLED screen.

