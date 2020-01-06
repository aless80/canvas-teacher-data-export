# Description
This script can be used by teachers to download data about courses and student submissions from Instructure Canvas Learning Management System [Canvas LMS](https://www.instructure.com/canvas/).  


# Getting Started
## Dependencies
To run the program, install the dependencies listed in the requirements.txt file:  
`pip install -r requirements.txt --user`  
These include canvasapi and requests.

## Canvas API
To export data from Canvas LMS you need two pieces of information: 
* API KEY, which can be generated in your Canvas log in page as described in [this post](https://community.canvaslms.com/docs/DOC-14409-4214861717)
* API URL i.e. your organization's Canvas Base URL, which is the URL of your Canvas LMS page where you log in to

You need administration privileges on the courses you want to export. 

## Running the script
`python export.py`

## Optional Configuration
This script will prompt the user for getting the API URL and API KEY. 
However, you can configure create a .env in this repository using the example file example_dotenv:
`cp example_dotenv .env`

The parameters that can be configured in .env are:
- Canvas API URL
- Canvas API key
- Comma separated list of Course IDs that should be skipped
- Output directory (default: "export")


# Export
The exported data include raw json data that can be downloaded using [Canvas API](https://canvasapi.readthedocs.io/en/latest/index.html), and submission attachments to submissions. 
In particular, the exported json files include: courses, assignments, submissions. The rubrics and full rubric assessments are included in the exported files

# Possible further development
* Consider to save announcements, discussions, pages, modules, other attachment files
* Consider to implement anonymization

# Credits
[David Katsandres](https://github.com/davekats)'s script [canvas-student-data-export](https://github.com/davekats/canvas-student-data-export). 