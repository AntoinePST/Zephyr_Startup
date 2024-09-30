
This is a simplified representation of the Zephyr repository architecture:

```c
zephyrproject/                       //WORKSPACE
   ├─── .venv/                       //Python virtual environments config
   ├─── .west/                       //west config
   │       └─── config
   │
   └─── app1/                        //User application 1
   │       └── src
   │       │      └── main.c      //main application file
   │       │
   │       ├── CMakeLists.txt     //links the app files directory
   │       ├── app.overlay        //devicetree overlay specification
   │       ├── prj.conf           //Kconfig (application-specific values)
   │       └─── VERSION           //app version info
   │
   └─── app2/ User application 2
   │       └── src
   │       │      └── main.c
   │       ├── […]
   │
   ├─── build/
   ├─── modules/
   ├─── tools/
   └──── zephyr/                //Zephyr repository application
	    ├── arch/                 //STM32 core handling related code
	    ├── boards/               //all supported board config
	    ├── cmake/                //cmake common script
	    ├── doc/
	    ├── drivers/              //Zephyr drivers
	    ├── dts/                  //device tree for SoCs
	    ├── include/
	    ├── kernel/               //kernel code
	    ├── lib/                  //built in libraries
	    ├── misc/
	    ├── modules/              //Kconfig files
	    ├── samples/              //samples applications
	    ├── scripts/
	    ├── share/
	    ├── snippets/
	    ├── soc/                  //common soc codes
	    ├── submanifests/
	    ├── subsys/               //sub system
      └── tests/                //test specific applications

```
>
> ## NOTE  
> *For more information you can refer to the Zephyr* **[Application Development](https://docs.zephyrproject.org/latest/develop/application/index.html#overview)** *page.*
> 
