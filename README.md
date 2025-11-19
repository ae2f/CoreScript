```
             ____   __     ____               ____            _       _   
   __ _  ___|___ \ / _| _ / ___|___  _ __ ___/ ___|  ___ _ __(_)_ __ | |_ 
  / _` |/ _ \ __) | |(_|_) |   / _ \| '__/ _ \___ \ / __| '__| | '_ \| __|
 | (_| |  __// __/|  _| _| |__| (_) | | |  __/___) | (__| |  | | |_) | |_ 
  \__,_|\___|_____|_|(_|_)\____\___/|_|  \___|____/ \___|_|  |_| .__/ \__|
                                                               |_|
```

# ae2f::CoreScript
> CMake Utility for project ae2f.  
> Supports library fetch & tent for installing

# Example usage (Simple)

Use this
```cmake
# Set this source directory as the tree root for project.
set(ae2f_ProjRoot ${CMAKE_CURRENT_SOURCE_DIR} CACHE STRING "Tree root for project")
set(ae2f_submod  .submod CACHE STRING "Relative path to submodule (subdirectory)")

# Directory to inject corescript
set(ae2f_CoreScript_Wh ./path/to/the/corescript)

# Execute git to fetch CoreScript when repository does not exist
if(NOT EXISTS ${ae2f_CoreScript_Wh})
    execute_process(
    COMMAND git clone https://codeberg.org/ae2f/CoreScript
    ${ae2f_CoreScript_Wh}
    )

# add subdirectory
add_subdirectory(${ae2f_CoreScript_Wh})

endif()
```
