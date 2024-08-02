# Deep fake detection Django Application
## Requirements:

**Note :** Nvidia GPU is mandatory to run the application.
- CUDA version >= 10.0 for GPU
- GPU Compute Capability > 3.0 


You can find the list of requirements in [requirements.txt](https://drive.google.com/file/d/14svhmCnjrkUOkRfr3uuCmXYWjojuy5B8/view?usp=drive_link). Main requirements are listed below:

```
Python 
Django 
```

## Directory Structure

- ml_app -> Directory containing code in views.py file
- project_settings -> Contains Django settings and files to run in production
- static -> Contains all css, js and json files (for face-api)
- templates -> Template files for HTML

<b>Note:</b> Before running the project make sure you have created directories namely <strong>models, uploaded_images, uploaded_videos</strong> in the project root and that you have proper permissions to access them.

# Running application locally on your machine

#### Step 1 : Clone the repo and Navigate to Django Application

`git clone https://github.com/Abbishek01/DEEPFAKE_DETECTION_MODEL.git`

#### Step 2: Create virtualenv (optional)

`python -m venv venv`

#### Step 3: Activate virtualenv (optional)

`venv\Scripts\activate`

#### Step 4: Install requirements

`pip install -r requirements.txt`

#### Step 5: Install applications required for running requirements

`pytorch - (https://pytorch.org/)`
`cmake - (https://cmake.org/download/)`
`Microsoft C++ Build Tools - (https://visualstudio.microsoft.com/visual-cpp-build-tools/)`

#### Step 6: Copy Models

`Copy your trained model to the " models " folder i.e Django Application/models/`
https
- You can download our trained models from [Google Drive](https://drive.google.com/drive/folders/1RWCUoqoC5et2X4E7c1nSVfS9OHRjSTKi?usp=sharing)

### Step 7: Run project

`python manage.py runserver`

