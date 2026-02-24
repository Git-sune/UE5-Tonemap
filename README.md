@Copyright Gitsune

# UE5-Tonemap

Working AgX tonemapping implementation for Unreal Engine 5.7 (tested with version UE5.73 on MacBook)

## Installation

Download and copy all files into following directory 
```[your UE5 Directory]/Engine/Shaders/Private```

Open your Unreal Engine project and execute following command in the console (default location is in the bottom bar, next to CMD)
```RecompileShaders changed```


## Switch Tonemapper
Since the change apply to all your projects (since we are changing internal shaders inside the editor) you can switch back by
opening the file ```TonemapCommon.ush``` and change ```USE_TONEMAP 1``` to ```USE_TONEMAP 0``` in the following line and use ```RecompileShaders changed``` again.

```
#ifndef USE_TONEMAP
	#define USE_TONEMAP 1 // 0=ACES (default), 1=AgX, 2=GT7 (not yet implemented), else=custom (not yet implemented)
#endif
```

## Custom Tonemapper

AgX is found in an isolated file ```AgXTonemap.ush```, feel free to modify the code (or use it as your starting point)


## Implementations

- ACES1.0 (UE5 default)
- AgX implemented
- GT7 not yet implemented

##Credits
AgX tonemapping implementation based on [Troy Sobotka's AgX]([https://choosealicense.com/licenses/mit/](https://github.com/sobotka/AgX) formulation.


