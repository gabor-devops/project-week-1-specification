# task #2: implement python project scaffolder

## pre-implementation task

- create an 5-10 length subtask list and time estimate for the following task
- if a subtask time estimate is more than 10 hours, break it down into smaller subtasks, if a subtask is less than 1 hour, merge it with another subtask.
- delegate all subtasks to team members

## specification

- create a python project scaffolder which creates a new python project in a new directory
- the scaffolder should be implemented as a python command line application
- the proposed folder structure is the following link:

```
helloworld/
│
├── docs/
├── helloworld/
│   ├── optional_modul_1/
│   │   ├── __init__.py
│   │   ├── optional_modul_1.py
│   ├── optional_modul_2/
│   │   ├── __init__.py
│   │   ├── optional_modul_2.py
│   ├── __init__.py
│   └── helloworld.py
│
├── tests/
│   ├── __init__.py
│   ├── helloworld_tests.py
│   ├── optional_modul_1_tests.py
│   └── optional_modul_2_tests.py
├── tools/
│
├── .gitignore
├── LICENSE
├── README.md
└── requirements.txt
```

- the scaffolder should create the folder structure above and place all the files in the correct locations, with the correct default content.
- use a .gitignore file which ignores the virtual environment folder, and the **pycache** folder, and any other artifacts which are not required to be committed to the git repository.
- the scaffolder should create the virtual environment, using venv. The requirements.txt file should be created also, and should contain the following packages: pytest, mypy
- the scaffolder should create a local git repository, and commit the initial files to the repository
- the scaffolder takes one parameter: the name of the project. (in the example above: helloworld) The name of the project should be used as the name of the directory, and anywhere it appers in the sample above.
- The content of the RAEDME.md file should be the following:

  ```
  # helloworld
  ```

- the scaffolder should be implemented in a way that it can be used on any platform (Windows, Linux, Mac OS X) without any modification.
- create automated deployment script which deploys the scaffolder to a clean Ubuntu 22.04 LTS Server.
- deploy the scaffolder to an Ubuntu 22.04 LTS Server, and test it there.
- document the scaffolder in a markdown and add it to the repository
- place the scaffolder and all files belong to it a separate folder in the repository:

  ```
  /tools/scaffolder
  ```
