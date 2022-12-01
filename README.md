# IIS2MDC
Simple IIS2MDC Magnetometer Driver

To use, include .c and .h files in your project.

The user must:

1. Create a IIS2MDC_Handle_t instance.
2. Create a IIS2MDC_InitSettings_t struct with the desired device settings. It is recommended the user reference the data sheet for setting details.
3. Provide a Low Level IO Driver structure "IIS2MDC_IO_t". At a minimum, this must include a "Read", "Write", and "GetTick" function. Unused function pointers should be set to NULL. If the user does not provide an IO Init function, the GPIO and communication bus must be initialized already.
4. Pass the created IIS2MDC_Handle_t instance, IIS2MDC_InitSettings_t instance, and IIS2MDC_IO_t instance to the function "IIS2MDC_Init" function.

Note that the data read from the device will not be calibrated; the user must do this themselves. 
