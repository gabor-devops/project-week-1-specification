## task #3: python command line inventory manager application: invman

## pre-implementation task

- create an 10-20 length subtask list and time estimate for the following task
- if a subtask time estimate is more than 10 hours, break it down into smaller subtasks, if a subtask is less than 1 hour, merge it with another subtask.
- delegate all subtasks to team members

## general requirements

- besides of the [general requirements in README.md](../README.md), the following requirements are also applicable for this task
- use the same folder stucture which is defined in scaffolder task
- create functions and methods, preferably no more than 10 lines of code in each one
- write parametrized pytest unit tests for all functions and methods, and ensure that the code coverage as high as possible.
- _optional_: use [rich](https://github.com/Textualize/rich) library to create the console interface

## specification

**invman** is a CLI application, which allows user to persist data in inventory of hosts, software installations, and networks. The application should be implemented in a way that it can be used on any platform (Windows, Linux, Mac OS X) without any modification.

- design CLI for the application: the application should provide a command-line interface (CLI) for users to interact with it. The CLI should allow users to perform all of the functionality described below.
- persistance: the application stores data for each entity in separate CSV files. Each file should contain columns for relevant information, such as hostname, IP address, OS, etc.
- the application should provide a command-line interface (CLI) for users to interact with it. The CLI should allow users to perform CRUD operations on each entity, as well as search for records based on specific criteria.
- CRUD Operations: For each entity, the application should allow users to perform the following CRUD operations:

  - create: users should be able to add new records to the CSV file for each entity. the application should prompt users to enter relevant information for each field for the particular entity.
  - read: Users should be able to view existing records for each entity. The application should allow users to specify which records they want to view (e.g., all records, or by id).
  - update: users should be able to modify existing records for each entity given by its id. the application should prompt users to enter relevant information for each field for that particular entity.
  - delete: users should be able to delete existing records for each entity given by its id. the application should prompt users to confirm the deletion before proceeding, but also should provide a command-line option to skip the confirmation.

- list: the application should allow users to list for records based on specific entity and criteria. users should be able to specify the entity they want to list and the list criteria.
- the following list criteria should be supported:
  - all: list all records for the given entity
  - by id: list records for the given entity by id, where id could be a comma-separated list of ids, or a range of ids (e.g., 1-5) or the combination of both (e.g., 1-5,7,9-11)
  - by field: list records for the given entity by a specific field value
  - by multiple fields: list records for the given entity by multiple field values
- error handling: The application should handle errors gracefully, including incorrect user input, missing or invalid CSV files, etc. The application should display helpful error messages to the user.
- validation: The application should validate user input to ensure that required fields are not empty, fields have valid data types, etc. the application should display validation errors.
- export: the application should allow users to export the inventory data into a JSON. the fields in the JSON should be the same as the fields in the CSV files, but use camelCase instead of snake_case.
- import: the application should allow users to import inventory data from a JSON file. the fields in the JSON should be the same as the fields in the CSV files, but the JSON file will be use camelCase instead of snake_case.

## entity specifications

The host entity should have the following attributes:

- id: an integer that uniquely identifies the host
- hostname: a string that identifies the host
- ip address: a string that represents the IP address of the host
- op: a string that represents the operating system installed on the host
- cpu: a string that represents the type of CPU installed on the host
- memory: an integer that represents the amount of memory installed on the host
- disk space: an integer that represents the amount of available disk space on the host
- networks: a list of integers that refer to the id of the the networks that the host is connected to

the software entity should have the following attributes:

- id: an integer that uniquely identifies the software
- name: a string that identifies the software
- version: a string that represents the version of the software
- publisher: a string that represents the publisher of the software
- installation date: a date that represents the date when the software was installed
- hostid: an integer that refers to the host where the software is installed

the network entity should have the following attributes:

- id: an integer that uniquely identifies the network
- name: a string that identifies the network
- ip address: a string that represents the IP address of the network
- subnet mask: a string that represents the subnet mask of the network
- gateway: a string that represents the gateway of the network

## sample CLI specification #1, with subcommands

note: this is just a partial sample, you should design your own CLI, which allows to perform all functionality described above.

```
Usage: inventory.py [OPTIONS] COMMAND SUBCOMMAND [ARGS]...

Options:
  --help  Show this message and exit.
  --version  Show the version and exit.

Commands:
  add       Add a new entity to the inventory
  delete    Delete an entity from the inventory
  update    Update an entity in the inventory
  list      List all entities in the inventory
  export  Export the inventory to a JSON file
  import  Import the inventory from a JSON file


Subcommands:
  host      Manage host entities
  network   Manage network entities
  software  Manage software entities

```

## sample CLI specification #2, without subcommands

note: this is just a partial sample, you should design your own CLI, which allows to perform all functionality described above.

```
Usage: inventory.py [OPTIONS] COMMAND [ARGS]...

Options:
  -e, --entity TEXT        Name of the entity to operate on [host|network|software]
  -a, --all                List all entities in the inventory
  --id TEXT            ID(s) or field range of the entity to operate on
  --help               Show this message and exit.
  --version  Show the version and exit.

Commands:
  add     Add a new entity to the inventory
  delete  Delete an entity from the inventory
  update  Update an entity in the inventory
  list    List entities in the inventory
  export  Export the inventory to a JSON file
  import  Import the inventory from a JSON file



```
