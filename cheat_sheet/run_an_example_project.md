
## NOTE  
*If you are following this tutorial from the beginning you can skip the first steps. Go directly to step 3.*

`1` - Go to your Zephyr Repository:

```shell
cd Zephyr_Repo
```

`2` - Activate the python virtual environment:

```shell
source zephyrproject/.venv/Scripts/activate
```

`3` - Go to the Zephyr workspace application:

```shell
cd zephyrproject
```

`4` - Build the blinky example for the board of your choice (in my case it will be a NUCLEO-U575ZI):

```shell
west build -p always -b nucleo_u575zi zephyr/samples/basic/blinky
```


## NOTE  
*You can find all the ST supported board in the folder `.../zephyrproject/zephyr/boards/st/`*


## NOTE  
*For more information on the `west` command and its arguments, please visit* **[this](https://docs.zephyrproject.org/latest/develop/west/index.html)** *page.*

`5` - Connect your board and flash the application:

```shell
west flash
```

**Now you should see the User LED blinking.**


### Troubleshooting

If the flash command (*west flash*) doesn't work, verify if CubeProgrammer is added in the `boards\st\xxxxxx\board.cmake`.\
It is needed to put it in first position like this:

```c
board_runner_args(stm32cubeprogrammer "--port=swd" "--reset-mode=hw")

include(${ZEPHYR_BASE}/boards/common/stm32cubeprogrammer.board.cmake)
```
