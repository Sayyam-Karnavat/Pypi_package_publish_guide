## Project Structure
Look at the sample directories uploaded "Your_project_name"


## Step-by-Step Guide

### 1. Create `__init__.py`

Inside the nested `Your_Project_Name` folder directory, create an `__init__.py` file. This can be an empty file or you can import the functions from all the files you have created:

from .file1 import function1
from .file2 import function2


### 2. Project.toml

```
[build-system]
requires = ["setuptools>=61.0"]
build-backend = "setuptools.build_meta"

[project]
name = "Your_Project_Name"
version = "0.0.1"
authors = [
    { name="Your Name", email="your_email@gmail.com" },
]
description = "Short description"
readme = "README.md"
requires-python = ">=3.8"
classifiers = [
    "Programming Language :: Python :: 3",
    "License :: OSI Approved :: MIT License",
    "Operating System :: OS Independent",
]

[project.urls]
Homepage = "https://github.com/yourusername/"
Issues = "https://github.com/yourusername/issues"
```

### 3. Create README.md
Your_Project_Name
"Short description of your project"




### 4. Create a License
Copyright (c) [year] [fullname]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.



### 5. Build the Package
Execute the following commands in the directory where the pyproject.toml file is located:

a. Install Build Tools :- py -m pip install --upgrade build

b. Generate Distribution Archives:- py -m build
(This will generate .tar.gz and .whl files in the dist folder.)



### 6. Upload Your Package

a. (Install Twine): py -m pip install --upgrade twine

b. (Upload to PyPI): py -m twine upload dist/*


### Note :- If hitting the above command of upload  asks for API token then make sure to create a .pypirc file in “C:\Users\”Username” ” directory with following content using “NOTEPAD” only to avoid “\n” error conflicts.

```
[distutils]
index-servers =
    pypi
[pypi]
username = __token__ 
password = “your_api_token_from_pypi” 
```


### Access your model

pip install Your_Project_Name


### Some Tips
- If you have imported the function from the package itself, it might not work and will give an error.
- If any error is found after publishing and importing the package, instead of deleting the current project on PyPI, update the version of the package in pyproject.toml and reiterate the steps from “Build the Package”.
- If you get a “same file name error,” try deleting the old dist and wheel folders and run the command py -m build again.





