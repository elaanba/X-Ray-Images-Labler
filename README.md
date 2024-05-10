# Acknowledge
Thank the original developer for the efforts he put into developing this app.
You can find the original application for the thoracic X-ray images labeler for spine cord segmentation here :
https://github.com/UW-CLEAR-Center/DICOM-Annotator

# Classification labler
This new customized version is for image classification tasks. You can put your target labels into the configuration file to adapt the app to your needs.
Before starting, put your images into the image folder.
and install the following packages:
pip install SimpleITK
pip install tifffile

# New version changes list
1- We put all files into one folder and changed import references to point to the local directory
2- We changed the application name from spine labeling app to labeling app ( main.py file )
3- For Multi-user use we added self.OstLabels = ["Normal", "Abnormal", "Borderline"]  to namerules.py file
4- We set the regions label "region_labels" to blik(configuration.csv file) 
5- We set image labels and description (configuration.csv file)
6 -we Disabled vertices to avoid plotting points (MyApp.py file)
7 - hardware_checkBox.hide() # we hidden the checkbox in region annotation (widget.py)
8 - remove spine order table choices from the start page (layout.py)
9 - We remove the label for regions not labeled widgets
10- remove the table and remove points buttons (layouts file )

 # How to open the app
- First, install Anaconda3. You can use conda_install.sh or you can go to https://docs.anaconda.com/anaconda/install/ for more details.

- The app is running in conda virtual environment. To install all required packages, run
$ conda create --name \<env> --file requirements.txt
- Activate the virtual environment.
$ conda activate \<env>
- Go into the folder where the DicomAnnotator folder stored
$ cd /path/to/dir
- Then run
$ export PYTHONPATH="\$PYTHONPATH:$PWD"
- Modify the configuration file (configurations.json)
- Run the app by
$ python DicomAnnotator/main.py

## How to merge result files
- Open merge_results.py.
- Input the result files' paths into result_paths and set the output merged file path (output_path).
- Run merge_results.py
$ python merge_results.py
- After running merge_results.py, the merged result file is generated.
	

# Optional arguments:
For example, 
$ python DicomAnnotator/main.py -h
##  -h
show this help message and exit.
##  -b
begin at which image, default is the first untouched image. The range should be 0 to (# of images - 1). Begin with the default image if out of the range.
##  -u
the max upper gray can be reached is {u * (grayscale of white of the images + 1) - 1} when window/level, default is 3.
##  -l
the lower upper gray can be reached is {- l * (grayscale of white of the images + 1)} when window/level, default is 2.
##  -d
whether turn on debug model.
##  -p
whether can place or remove points on images.

# Funding
This work was completed by investigators at the University of Washington's Clinical Learning, Evidence And Research (CLEAR) Center for Musculoskeletal Disorders and supported by a research grant from the National Institute of Arthritis and Musculoskeletal and Skin Diseases (NIAMS) of the National Institutes of Health, under Award Number P30AR072572.

# Citation
If you would like to use this code for a research project please use this acknowledgement below all publications. This helps us continue to support this program and continue to innovate.

DICOMAnnotator was developed through the University of Washington's Clinical Learning, Evidence And Research (CLEAR) Center for Musculoskeletal Disorders and supported by a research grant from the National Institute of Arthritis and Musculoskeletal and Skin Diseases (NIAMS) of the National Institutes of Health, under Award Number P30AR072572.
