# Bagpy Analysis [Usage]
## Create an environment
```
conda create -n bagpy_analysis python=3.8
source activate bagpy_analysis
```

## Get the repo and prepare the tools
User can get the repo by the following command:
```
git clone this repo
cd bag_analysis_tool
```
Then, put your bagfile and supported .csv file into the folder and save it like:
```
bagpy_analysis_tool/
├── split_tool.py
├── analysis_tool.py
├── tool_algorthim.py
├── utils.py
├── your_bagfile.bag
├── bagfile_para.csv
├── requirements.py
```

## Requirements
```
pip install -r requirements.txt
```

## Bagfile Split Tool
### 1. Archetecture of the input parameter of the split tool
```
split_tool.py [-h] 
              [--bagfile BAGFILE]                       the dir of the bagfile
              [--parameter_file PARAMETER_FILE]         the dir of parameter file
              [--save_dir SAVE_DIR]                     the dir to save the outout
              [--outbag_name OUTBAG_NAME]               the dir to save the outout
              [--start_time START_TIME]                 the start time to split
              [--split_duration SPLIT_DURATION]         the split duration (seconds)
```
User can also use ```python split_tool.py -h``` to see the help.
### 2. Demo
User can run the demo by the following command:
```
python split_tool.py --bagfile your_bagfile_dir \
                --parameter_file your_parafile_dir \
                --save_dir ./split_result \
                --outbag_name ouput.bag \
                --start_time 1628031922 
                --split_duration 30 \
```
User can assign the save dir and the name of splitted bagfile, the start time to split and the duration, the duration is with the unit of second, then it will output the splitted bagfile in the assigned dir with the archetecture below:
```
bagpy_analysis_tool/
├── split_result/
│   └── output.bag
│   └── output_info.json
├── split_tool.py
├── analysis_tool.py
├── tool_algorthim.py
├── utils.py
├── your_bagfile.bag
├── bagfile_para.csv
```
The  ```output_info.json``` includes the information of the original bagfile (the topis, dimension and etc.) and the information of the output bagfile (the topis, dimension and etc.)

## Bagfile Analysis Tool
### 1. Archetecture of the input parameter of the analysis tool
```
analysis_tool.py [--bagfile1 BAGFILE1]                      the dir of bagfile 1
                 [--bagfile2 BAGFILE2]                      the dir of bagfile 2
                 [--parameter_file1 PARAMETER_FILE1]        the dir of parameter file 1
                 [--parameter_file2 PARAMETER_FILE2]        the dir of parameter file 2
                 [--save_dir SAVE_DIR]                      the dir to save the outout
```
User can also use ```python analysis_tool.py -h``` to see the help.
### 2. Demo
User can run the demo by the following command:
```
python analysis_tool.py --bagfile1 your_bagfile1\
                        --bagfile2 your_bagfile2\                     
                        --parameter_file1 your_parafile1\
                        --parameter_file2 your_parafile2\
                        --save_dir your_output_dir
```
User can assign the save dir and the name of splitted bagfile, the start time to split and the duration, the duration is with the unit of second, then it will output the splitted bagfile in the assigned dir with the archetecture below:
```
bagpy_analysis_tool/
├── output/
    └── output.json
    ├── v_ref_comparison.png
    ├── v_ref_difference.png
    ├── cmd_accel_comparison.png
    └── cmd_accel_difference.png
├── split_tool.py
├── analysis_tool.py
├── tool_algorthim.py
├── utils.py
├── your_bagfile1.bag
├── your_bagfile2.bag
├── bagfile1_para.csv
├── bagfile2_para.csv
```
The  ```output.json``` includes the information of the original bagfile and the comparison results.





