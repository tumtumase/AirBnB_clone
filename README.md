# AirBnB Clone - The Console

## Project Description
This project is the first step towards building a full web application clone of AirBnB. This first step consists of a custom command-line interface for data management and the base classes for the storage of this data.

## Command Interpreter Description

### How to Start It
The command interpreter can be started by executing the command `./console.py`. The console can be used in both interactive and non-interactive mode. It prints a prompt **(hbnb)** and waits for the user input.

```bash
$ ./console.py
(hbnb) 
```

### How to Use It
* In interactive mode:

```bash
$ ./console.py
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  help  quit

(hbnb) quit
$
```

* In non-interactive mode:

```bash
$ echo "help" | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb)
$
```

### Commands
* **quit** - Exits the program
* **EOF** - Exits the program
* **help** - Displays all commands available
* **create** - Creates a new instance
* **destroy** - Destroys a specified instance
* **show** - Shows the information of a specified instance
* **all** - Shows all instances, or all instances of a class
* **update** - Updates an instance based on the class name and id

### Examples

```bash
$ ./console.py
(hbnb) create User
b6a6e15c-c67d-4312-9a75-9d084935e579
(hbnb) show User b6a6e15c-c67d-4312-9a75-9d084935e579
[User] (b6a6e15c-c67d-4312-9a75-9d084935e579) {'id': 'b6a6e15c-c67d-4312-9a75-9d084935e579', 'created_at': datetime.datetime(2024, 11, 20, 19, 2, 19, 830898), 'updated_at': datetime.datetime(2024, 11, 20, 19, 2, 19, 830898)}
(hbnb) all User
["[User] (b6a6e15c-c67d-4312-9a75-9d084935e579) {'id': 'b6a6e15c-c67d-4312-9a75-9d084935e579', 'created_at': datetime.datetime(2024, 11, 20, 19, 2, 19, 830898), 'updated_at': datetime.datetime(2024, 11, 20, 19, 2, 19, 830898)}"]
(hbnb) update User b6a6e15c-c67d-4312-9a75-9d084935e579 first_name "Betty"
(hbnb) show User b6a6e15c-c67d-4312-9a75-9d084935e579
[User] (b6a6e15c-c67d-4312-9a75-9d084935e579) {'id': 'b6a6e15c-c67d-4312-9a75-9d084935e579', 'created_at': datetime.datetime(2024, 11, 20, 19, 2, 19, 830898), 'updated_at': datetime.datetime(2024, 11, 20, 19, 2, 19, 830898), 'first_name': 'Betty'}
(hbnb) quit
$
```

## Models
The folder [models](./models) contains all the classes used in this project.

| File | Description | Attributes |
|------|-------------|------------|
| [base_model.py](./models/base_model.py) | BaseModel class for all other classes | id, created_at, updated_at |
| [user.py](./models/user.py) | User class for user information | email, password, first_name, last_name |
| [amenity.py](./models/amenity.py) | Amenity class for amenity information | name |
| [city.py](./models/city.py) | City class for location information | state_id, name |
| [state.py](./models/state.py) | State class for location information | name |
| [place.py](./models/place.py) | Place class for accommodation information | city_id, user_id, name, description, number_rooms, number_bathrooms, max_guest, price_by_night, latitude, longitude, amenity_ids |
| [review.py](./models/review.py) | Review class for user reviews | place_id, user_id, text |

## File Storage
The folder [engine](./models/engine/) manages the serialization and deserialization of all the data, following a JSON format.

A FileStorage class is defined in [file_storage.py](./models/engine/file_storage.py) with methods to follow this flow:
```<class 'BaseModel'> -> to_dict() -> <class 'dict'> -> JSON dump -> <class 'str'> -> FILE -> <class 'str'> -> JSON load -> <class 'dict'> -> <class 'BaseModel'>```

## Tests
All the code is tested with the unittest module. The test for the classes are in the [test_models](./tests/test_models/) folder.

## Authors
* **[Boitumelo Moeca]** - [Github](https://github.com/tumtumase)
* **[Team Member Name]** - [Github](https://github.com)
