# API Config Files Management
## API for Windows configuration file management

This API allows for efficient management of configuration `.ini` files. It includes functions for reading, writing, and manipulating sections and keys within configuration files. It is designed to provide easy access to configuration data and modify it dynamically.

## Modules Overview

### Read Functions

These functions are used to read data from a configuration `.ini` file.

#### `read config ini data.vi`

![imagen](https://github.com/user-attachments/assets/c1ad7138-d9c2-4a8b-b442-d1a231a78559)

This function reads all the data from a configuration `.ini` file and returns it in a cluster. The cluster contains three arrays:
- A 2D string array for the sections, where the first row stores the section names and the second row stores the number of keys in each section.
- A 1D string array for the key names.
- A 1D string array for the corresponding values.

#### `read keys per section.vi`

![imagen](https://github.com/user-attachments/assets/7db1cc2e-b21a-45d4-abe6-1afc83a4762d)

This function retrieves all keys and their corresponding values from a specified section in a configuration `.ini` file. Given the section name, the output is a cluster containing:
- A string for the section name.
- A 1D string array for the key names.
- A 1D string array for the corresponding values.

### Write Functions

These functions are used to write data to a configuration `.ini` file.

#### `write config ini data.vi`

![imagen](https://github.com/user-attachments/assets/d8947b49-ddb8-4e66-9ce7-d75a4374243f)

This function writes the complete data from the input cluster to a configuration `.ini` file. The input cluster contains three arrays:
- A 2D string array for the sections, where the first row stores the section names and the second row stores the number of keys in each section.
- A 1D string array for the key names.
- A 1D string array for the corresponding values.

#### `write keys per section.vi`

![imagen](https://github.com/user-attachments/assets/9a5a1392-240b-46c5-838d-368c747e9fb8)

This function writes all keys and their corresponding values to a configuration `.ini` file, given the section name. The input is a cluster containing:
- A string for the section name.
- A 1D string array for the key names.
- A 1D string array for the corresponding values.

### Remove Functions

These functions allow manipulation of keys in the configuration `.ini` file.

#### `remove all keys per section.vi`

![imagen](https://github.com/user-attachments/assets/ed994fab-5243-40e2-9670-c3758140ea1d)

This function removes all keys from a specified section in a configuration `.ini` file, given the section name. The result in the `.ini` file is the section without any keys, but the section itself remains.

### Open and Close Functions

These functions manage opening and closing configuration files.

#### `open config file.vi`

![imagen](https://github.com/user-attachments/assets/366d380d-8639-4ef9-81ed-920aa698df3b)

This function opens a configuration `.ini` file for reading or writing, given the file name as a string input. Internally, it uses the Aplication Directory.vi that returns the app directory, and build the full path for the configuration file. The function returns a Refnum to the opened configuration file.

#### `close config file.vi`

![imagen](https://github.com/user-attachments/assets/4376d467-c207-40d3-b17a-067f2d71cd86)

This function closes the currently opened configuration `.ini` file, destroying the associated Refnum. It ensures that the file is properly closed, and no further operations can be performed until the file is reopened.

---
### Controls

The API includes two controls for managing the clusters used in reading and writing configuration data.

#### `config data.ctl`

![imagen](https://github.com/user-attachments/assets/5733eb65-2a38-433f-81da-d549226ff76d)

This control represents the cluster used for reading and writing the complete configuration data. It contains:
- A 2D string array for the section names and their respective key counts.
- A 1D string array for the key names.
- A 1D string array for the corresponding values.

#### `section data.ctl`

![imagen](https://github.com/user-attachments/assets/15c8f33e-458a-4e19-ae61-d3298831e18f)

This control represents the cluster used for handling data related to a single section. It contains:
- A string for the section name.
- A 1D string array for the key names.
- A 1D string array for the corresponding values.

---

### Visual Representation

The infographics below show the organization of the config data.ctl and section data.ctl clusters in relation to the .ini file. On the right, the .ini file layout is displayed, showing sections with keys and their corresponding values. On the left, the clusters are depicted, illustrating how the arrays are structured within the clusters. The two graphics provide a clear comparison of how the data is organized in both the clusters and the .ini file.

![imagen](https://github.com/user-attachments/assets/43f39d7d-e7dc-40a9-b872-6d37c724f284)

![imagen](https://github.com/user-attachments/assets/7fd5a796-3ed2-4efa-8eb7-7ab852bb3bc2)


