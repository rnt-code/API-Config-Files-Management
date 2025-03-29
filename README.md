# API Config Files Management
## API for Windows configuration file management

This API allows for efficient management of configuration `.ini` files. It includes functions for reading, writing, and manipulating sections and keys within configuration files. It is designed to provide easy access to configuration data and modify it dynamically.

## Modules Overview

### Read Functions

These functions are used to read data from a configuration `.ini` file.

#### `read config ini data.vi`

This function reads all the data from a configuration `.ini` file and returns it in a cluster. The cluster contains three arrays:
- A 2D string array for the sections, where the first row stores the section names and the second row stores the number of keys in each section.
- A 1D string array for the key names.
- A 1D string array for the corresponding values.

#### `read keys per section.vi`

This function retrieves all keys and their corresponding values from a specified section in a configuration `.ini` file. Given the section name, the output is a cluster containing:
- A string for the section name.
- A 1D string array for the key names.
- A 1D string array for the corresponding values.

### Write Functions

These functions are used to write data to a configuration `.ini` file.

#### `write config ini data.vi`

This function writes the complete data from the input cluster to a configuration `.ini` file. The input cluster contains three arrays:
- A 2D string array for the sections, where the first row stores the section names and the second row stores the number of keys in each section.
- A 1D string array for the key names.
- A 1D string array for the corresponding values.

#### `write keys per section.vi`

This function writes all keys and their corresponding values to a specified section in a configuration `.ini` file. The input is a cluster containing:
- A string for the section name.
- A 1D string array for the key names.
- A 1D string array for the corresponding values.

### Remove Functions

These functions allow manipulation of keys in the configuration `.ini` file.

#### `remove all keys per section.vi`

This function removes all keys from a specified section in a configuration `.ini` file, given the section name. The result in the `.ini` file is the section without any keys, but the section itself remains.

### Open and Close Functions

These functions manage opening and closing configuration files.

#### `open config file.vi`

This function opens a configuration `.ini` file for reading or writing, given the file name as a string input. Internally, it uses the `Application Directory.vi` to return the app directory and constructs the full path for the configuration file. The function returns a Refnum to the opened configuration file.

#### `close config file.vi`

This function closes the currently opened configuration `.ini` file, destroying the associated Refnum. It ensures that the file is properly closed, and no further operations can be performed until the file is reopened.

## Usage Example

```labview
// Example code for using the API

