<p align="center">
 <img src="https://github.com/ganamir/MLDAPP/assets/129692189/c684e3b2-9df1-4177-9abd-2e22ec30810f" height = "300">
</p>

<h1 align="center"><b>MLDAAPP</b></h1>
<p align="center"><small>Phonetic: em-el-dap | /ɛm ɛl ˈdæp/</small></p>

<div align = "center"> 
<h4>
  Machine Learning Data Acquisition for Assesing Population Phenotypes based on <a href = "https://github.com/ultralytics/ultralytics">YOLOv8

   MLDAAPP is a utility based off of YOLOv8, which helps in converting/creating/extracting essential information from the analyzed data to be used in phenotyping.
  </a>
</h4>
</b>
</div>
<div align = "center">
<img alt="GitHub followers" src="https://img.shields.io/github/followers/ganamir"> <img alt="GitHub Repo stars" src="https://img.shields.io/github/stars/ganamir/MLDAPP"> <img alt="GitHub commit activity (branch)" src="https://img.shields.io/github/commit-activity/t/ganamir/MLDAPP"> <img alt="GitHub last commit (branch)" src="https://img.shields.io/github/last-commit/ganamir/MLDAPP/main">
</div>
<div align = "center">

</div>
<div align = "center"> <p> 
<img src = "https://github.com/ganamir/MLDAAPP/assets/129692189/20066b97-dc1e-4882-a588-8aff485404dc" hspace = "5" height = "100">
<img src = "https://github.com/ganamir/MLDAAPP/assets/129692189/0539cbaf-955e-475d-bd4b-30cc153a9956" hspace = "5" height = "100" >
<img src = "https://github.com/ganamir/MLDAAPP/assets/129692189/4fda3b16-6200-44b2-bba6-393d7475fb28" hspace = "5" height = "100" >
</p></div>

<div align = "center"> <p> Video Examples
 | <a href = "https://drive.google.com/drive/folders/1t6K05ucDLfYnNPZ0ddboAz4vdq3WrCOa?usp=sharing"> Fruit Flies </a> |
 <a href = "https://drive.google.com/drive/folders/1AO-t3DIOKdH7gkiKqyn4ymQ1XZr-srwZ?usp=sharing"> Hamsters </a> |
 <a href = "https://drive.google.com/drive/folders/1aQ10fsA_LZhURsEHc7x2JYWzwjXsw5a9?usp=sharing"> Bees </a> | 
 <a href = "https://drive.google.com/drive/folders/1Cik_RP02iHdTcI5X0fH4UrqCQYtgXdQ7?usp=sharing"> And the Rest <a/> |
 </p></div>

</div>
<div align = "center"> <p> 
<img src = "https://github.com/user-attachments/assets/ef31a024-393e-44b9-a1e6-31ca270638db" hspace = "5" height = "100">
<img src = "https://github.com/user-attachments/assets/80174883-6d2e-4e0e-8cb2-18f89c8a2dc7" hspace = "5" height = "100" >
<img src = "https://github.com/user-attachments/assets/cc56f401-a0b2-4f11-bc59-404cc73a6d30" hspace = "5" height = "100" >
</p></div>

<div align = "center"> <p> Pre-trained data-sets / Practice Data / Media Recipe
 | <a href = "https://drive.google.com/drive/folders/1WbZzdiBK329fIynr9Bp50CJXg14U6kiW?usp=sharing"> Fecundity Brown </a> |
 <a href = "https://drive.google.com/drive/folders/1gBcKWz25Pzf5bOMl8egwMLgMuFNa2KLq?usp=sharing"> Fecundity Charcoal </a> |
 <a href = "https://drive.google.com/drive/folders/1uckmLDCpvGtKHWd2GALrCm8y0Hoz6lBe?usp=sharing"> Drosophila Movement </a> | 
 </p></div>

# Key Features 

<p align="center">
  <img src="https://github.com/ganamir/MLDAAPP/assets/129692189/132e196e-6e85-41b2-a38a-078e4d415b0b" alt="MLDAAPP" width="65%" height="65%">
</p>

# Running YOLOV8 and MLDAAPP
- Head to [Roboflow](https://roboflow.com/) or [LabelStudio](https://github.com/HumanSignal/label-studio/) and annotate your training set, direct down the page to appropriate sections for step-by-step run down to labeling,training, and running YOLOv8 and extracting data with MLDAAPP.

- Open the following [Google Colab](https://colab.research.google.com/drive/1RF-X42pNAzs0zy94h3dpGjU_efzAwwzN?usp=sharing) link then ![image](https://github.com/ganamir/MLDAAPP/assets/129692189/3fb04c3d-4198-440f-a8ce-69124d4ef5cf) and make sure that you have a GPU connected (Runtime > Change runtime type > Hardware accelerator: ### GPU > ![image](https://github.com/ganamir/MLDAAPP/assets/129692189/bf78551c-d5ea-4cdc-b9d2-0bd4880e073d)
)

- Once connected, simply execute this cell by clicking the start button. ![image](https://github.com/ganamir/MLDAAPP/assets/129692189/cab7e894-02a7-4f1d-86d7-a4b94544322c)

<h1 align="center">1. Data-set Annotation and Training</h1>

<p align="center">
  <a href="https://www.youtube.com/watch?v=YWrF824WTb8">
    <img src="https://img.youtube.com/vi/YWrF824WTb8/hqdefault.jpg" alt="Watch the video">
  </a>
</p>
 
### Roboflow annotation (preferred method):
Create an account, create a project and upload your respective training data, annotate using bounding box tool (for object counting/tracking), or polygon tool (for object tracking/surface area).
Once finished annotating, export your data with appropriate augementations and desired photo resolution, then copy paste your generated install code from roboflow into MODEL SELECTION AND TRAINING column, under "Upload your Roboflow code and install your annotated data" cell and execute the block.

After installation of your training data, head to ![image](https://github.com/ganamir/MLDAAPP/assets/129692189/6b656640-afd4-48da-a131-d23ac3f2341e) graphic in the top left corner of the website, and locate data.yaml file in your downloaded annotated data-set directory. Open it, and make sure that it looks similar to the below code block. Pay high attention to test,train and val sections, as sometimes ```../``` is missing, not allowing YOLOv8 models to properly find the training directories. 
```
names:
- YourObjectName
nc: #
roboflow:
  license: CC BY 4.0
  project: Name
  url: https://universe.roboflow.com/name/name/dataset/#
  version: #
  workspace: name
test: ../test/images
train: ../train/images
val: ../valid/images
```

<h1 align="center"> 2. Train your model</h1>
<p align="center">
  <a href="https://www.youtube.com/watch?v=dpz2-19wE-8">
    <img src="https://img.youtube.com/vi/dpz2-19wE-8/hqdefault.jpg" alt="Watch the video">
  </a>
</p>

Once satisfied, move on to "Train your model" code block, and insert your model of choice (```yolov8x.pt``` or ```yolov8x-seg.pt```), more information at [Models Section](https://docs.ultralytics.com/models/yolov8/#supported-tasks-and-modes) or the FAQ.
Then insert your data.yaml file directory into the specified space, and make sure to change ```imgsz = [w,h] ``` to your desired dimensions (typically used 640x640, or higher resolutions such as 1920x1080 for better detail for small object detection), and add ```project = ""``` directory to save your model in a desired space (Highly recommend saving your model in a google drive folder, as to make sure that no outages and disconnections result in the losing of your trained algorithm).


<h1 align="center"> 3. Different Type Data Analysis </h1>
<p align="center">
<table align="center">
  <tr>
    <td align="center">
      <a href="https://www.youtube.com/watch?v=UzatX7C3N4U">
        <img src="https://img.youtube.com/vi/UzatX7C3N4U/0.jpg" width="250">
      </a>
    </td>
    <td align="center">
      <a href="https://www.youtube.com/watch?v=PjcwlIL_1UU">
        <img src="https://img.youtube.com/vi/PjcwlIL_1UU/0.jpg" width="250">
      </a>
    </td>
    <td align="center">
      <a href="https://www.youtube.com/watch?v=rGuyffBujUE">
        <img src="https://img.youtube.com/vi/rGuyffBujUE/0.jpg" width="250">
      </a>
    </td>
  </tr>
</table>
</p>

## Photo Analysis (Such as Fecundity Counts):
- Define your ```model = YOLO()``` with the best.pt file directory from your custom trained model.
- Insert your directory of your photos instead of "Your Photo Data Folder".
- Modify FileName.csv and ColumnName to your desired names and variables in ```save_to_csv("FileName.csv", "ColumnName", n)```.
- *IMPORANT*: Make sure to iterate on the ```conf = ###```, by increasing or decreasing the number. Lowering confidence allows for more detections, increasing it lowers them. Having a range of photos pre-counted as best as possible to fit the model by iterating conf best fits the data that you have. Maintaining similar photographic conditions between data-sets allows for the same confidence value to be best fit without iteration. 

## Automatic Video Analysis:
This is where you will be able to analyze your videos and extract various metrics from the videos. Highly recommend renaming your video files according to a unique name and/or potentially segregate each file into a seperate folder for cleanliness. The script should analyze all videos in bulk, and produce .csv files with appropriate metrics for each of the videos. 

### Calculate pixel per centimeter metric for MLDAAPP conversions:
Specify your ```directory_path = "" ``` with your folder of video files, and execute the cell block. Once a photo generates under the cell block, use ```draw_lines()``` command to draw a line across the generated frame along side an object of known size and calculate how many pixels are within a centimeter. 

### Run Video Analysis:

- First, define the model ```model = '' ```, insert the directory of your best.pt file that was generated after training your custom model.
- Second, insert your value into ```pixels_per_centimeter =``` variable. This is neccessary to calculate the appropriate conversions.
- Third, define your ```directory_path = "" ``` with your video file directory. This is incase if you didn't run the above cell block.
- Finally, depending on what format you video files are ".MP4, .MOV, etc." modify the code line ```if filename.endswith('.MOV'):``` with your own format.

You should now be able to execute the cell block, and the analysis will begin. 

### Video Outputs Explained:


<div align="center">

<table>
  <thead>
    <tr>
      <th>"Net" File Output</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Centroid_X_Total_diff</td>
      <td>Total centroid (center of object) displacement across all frames across x-axis</td>
    </tr>
    <tr>
      <td>Centroid_Y_Total_diff</td>
      <td>Total centroid (center of object) displacement across all frames across y-axis</td>
    </tr>
    <tr>
      <td>Total_Diff</td>
      <td>Total Centroid Displacement across x & y across all frames</td>
    </tr>
    <tr>
      <td>Total_diff_cm</td>
      <td>Total Centroid Displacement across x & y across all frames in cm</td>
    </tr>
  </tbody>
</table>

<br>

<table>
  <thead>
    <tr>
      <th>"Main" File Output</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Object_Name</td><td>Object name as trained by the algorithm (only useful if contains more than 1 group)</td></tr>
    <tr><td>ID</td><td>Unique ID of the tracked individual</td></tr>
    <tr><td>X# & Y#</td><td>Object vector coordinates</td></tr>
    <tr><td>Frame_Num</td><td>Frame ID / Number</td></tr>
    <tr><td>Centroid_X(_Y)</td><td>Calculated centroid of the object</td></tr>
    <tr><td>Origin_X(Y)</td><td>Starting coordinates of the unique ID</td></tr>
    <tr><td>ID_Orig_Distance</td><td>Distance of the centroid of the ID away from its Starting Position (in pixels)</td></tr>
    <tr><td>Centroid_X(Y)_diff</td><td>Centroid Axial Displacement from Previous Position (previous frame)</td></tr>
    <tr><td>Total_Centroid_diff</td><td>Total Centroid Displacement from Previous Position (previous frame)</td></tr>
    <tr><td>Total_Centroid_diff_cm</td><td>Total Centroid Displacement from Previous Position (in cm)</td></tr>
    <tr><td>Total_Area (only available in object segmentation)</td><td>Total Area of the object (calculated using shoelace method)</td></tr>
    <tr><td>Total_Area_cm² (only available in object segmentation)</td><td>Total Area of the object (cm²)</td></tr>
    <tr><td>Polygon#</td><td>Boolean, TRUE / FALSE - Shows if centroid of the ID is within the specified space</td></tr>
    <tr><td>ID_Q_Distance</td><td>Distance of the ID Centroid away from the specified point Q (in pixels)</td></tr>
  </tbody>
</table>

</div>






# FAQ
**Where can I get the pre-trained models?**
- At the top of the GitHub "Pre-trained data-sets" leads to the appropriate models.

**My counts are innacurate although it's well trained, why?**
 - Make sure to iterate the ``` conf = ### ``` function to best fit your model to your data.

**Tracking in videos is innacurate and some individuals get reassigned, what can I do about it?**
 - We provide an additional subsection in MLDAAPP, "Manual Video Analysis," where you can individually analyze a video through your trained algorithm, manually re-assign IDs in a video, and extract that data as needed. Unfortunately, no tracker is perfect.








