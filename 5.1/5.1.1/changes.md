#### lapi.c

###### lua_replace - [diff](changes.diff#L22) - [final](src/lapi.c#L199)
  - Prevents replacing the environment from a non Lua scope
    - Ex. calling luaopen_io

#### ldo.c

###### resume - [diff](changes.diff#L173) - [final](src/ldo.c#L383)
  - Prevents operating on errored threads
  - Only resets thread status when resuming from a yielded thread
    - Removes yield status before calling hooks

#### lgc.c

###### propagateall - [diff](changes.diff#L214) - [final](src/lgc.c#L323)
  - Returns size of blacked grey objects

###### atomic - [diff](changes.diff#L221) - [final](src/lgc.c#L540)
  - Updates GC estimate with results from propagateall 

###### singlestep - [diff](changes.diff#L230) - [final](src/lgc.c#L556)
  - When the estimate is greater than the cost of the finalizer and it is on the last userdata object, remove the cost

#### liolib.c

###### io_pclose - [diff](changes.diff#L251) - [final](src/liolib.c#99)
###### io_fclose - [diff](changes.diff#L260) - [final](src/liolib.c#107)
  - The file is always set to NULL, ignoring if the p/fclose call was successful

#### loslib.c

###### os_pushresult - [diff](changes.diff#L365) - [final](src/loslib.c#23)
  - Improper arguments for os_rename/remove will always attempt to print the file name, falling to "(null)"

#### lstate.c

###### lua_close - [diff](changes.diff#L481) - [final](src/loslib.c#199)
  - luai_userstateclose macro was moved after GC metamethod calls

#### lstrlib.c

###### addquoted - [diff](changes.diff#L506) - [final](src/lstrlib.c#695)
  - Adds quoted (%q) support for carriage return

#### lua.c

###### collectargs - [diff](changes.diff#L555) - [final](src/lua.c#259)
  - Command line arguments must match perfectly

#### luac.c

###### doargs - [diff](changes.diff#L629) - [final](src/luac.c#70)
  - Allows for the version to be printed after options are ended by '--'
