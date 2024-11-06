# KIT_FX20_FMC_001 BSP

## Overview

The Infineon Technologies EZ-USB™ FX20 family features a USB 3.2 Gen 2x2 device  controllers(CYUSB40XX, CYUSB308X) designed for high-performance applications. The Development  Kit (DVK) helps customers develop a wide range of USB 3.2 applications, such as seamless video  and audio streaming to a USB host using FPGA add-on boards and camera modules. It supports data  transfer via USB 20Gbps for AI, imaging, and emerging applications. Ideal for medical imaging,  industrial automation, high-speed data acquisition, VR/AR, advanced robotics, and smart surveillance,  the DVK is a versatile solution for both established and cutting-edge fields.



To use code from the BSP, simply include a reference to `cybsp.h`.

## Features

### Kit Features:

* USB 3.2 Gen 2x2: accessible through the USB-IF certified USB-C receptacle
* GPIO header: To interface IFX Digital MEMS microphone board, CAN transceiver board,             I2S Audio Class-D amplifier board, Arduino shield, and AUX I/O Opto-isolator board via             a GPIO accessory board
* FMC interface: One FMC HPC Mezzanine connector for external FPGA FMC boards with FX20,             compatible with both LPC and HPC FMC connectors. Additionally, one FMC HPC carrier             connector for connecting other add-on carrier boards to FPGA board via FX20 DVK.
* USB-FS interface: For serial logs

### Kit Contents:

* EZ-USB™ FX20 DVK (Base board and GPIO accessory board)
* Quick Start Guide

## BSP Configuration

The BSP has a few hooks that allow its behavior to be configured. Some of these items are enabled by default while others must be explicitly enabled. Items enabled by default are specified in the KIT_FX20_FMC_001.mk file. The items that are enabled can be changed by creating a custom BSP or by editing the application makefile.

Components:
* Device specific category reference (e.g.: CAT1) - This component, enabled by default, pulls in any device specific code for this board.

Defines:
* CYBSP_WIFI_CAPABLE - This define, disabled by default, causes the BSP to initialize the interface to an onboard wireless chip if it has one.
* CY_USING_HAL - This define, enabled by default, specifies that the HAL is intended to be used by the application. This will cause the BSP to include the applicable header file and to initialize the system level drivers.
* CYBSP_CUSTOM_SYSCLK_PM_CALLBACK - This define, disabled by default, causes the BSP to skip registering its default SysClk Power Management callback, if any, and instead to invoke the application-defined function `cybsp_register_custom_sysclk_pm_callback` to register an application-specific callback.

### Clock Configuration

| Clock    | Source    | Output Frequency |
|----------|-----------|------------------|
| FLL      | IMO       | 24.6 MHz         |
| PLL      | IMO       | 48.0 MHz         |
| CLK_HF0  | CLK_PATH1 | 150 MHz          |
| CLK_HF1  | CLK_PATH1 | 37 MHz           |
| CLK_HF2  | CLK_PATH2 | 48 MHz           |
| CLK_HF3  | CLK_PATH0 | 24 MHz           |
| CLK_HF4  | CLK_PATH1 | 150 MHz          |

### Power Configuration

* System Active Power Mode: LP
* System Idle Power Mode: Deep Sleep
* VDDA Voltage: 3300 mV
* VDDD Voltage: 3300 mV

See the [BSP Setttings][settings] for additional board specific configuration settings.

## API Reference Manual

The KIT_FX20_FMC_001 Board Support Package provides a set of APIs to configure, initialize and use the board resources.

See the [BSP API Reference Manual][api] for the complete list of the provided interfaces.

## More information
* [KIT_FX20_FMC_001 BSP API Reference Manual][api]
* [KIT_FX20_FMC_001 Documentation](https://www.infineon.com/cms/en/product/promopages/ez-usb-fx10)
* [Cypress Semiconductor, an Infineon Technologies Company](http://www.cypress.com)
* [Infineon GitHub](https://github.com/infineon)
* [ModusToolbox™](https://www.cypress.com/products/modustoolbox-software-environment)

[api]: https://infineon.github.io/TARGET_KIT_FX20_FMC_001/html/modules.html
[settings]: https://infineon.github.io/TARGET_KIT_FX20_FMC_001/html/md_bsp_settings.html

---
© Cypress Semiconductor Corporation (an Infineon company) or an affiliate of Cypress Semiconductor Corporation, 2019-2024.