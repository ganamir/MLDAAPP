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

- Open the following [Google Colab](https://colab.research.google.com/drive/1T-VKwfD3VGBhYVhGBEXpWB1HPT_pqOxV?usp=sharing) link then ![image](https://github.com/ganamir/MLDAAPP/assets/129692189/3fb04c3d-4198-440f-a8ce-69124d4ef5cf) and make sure that you have a GPU connected (Runtime > Change runtime type > Hardware accelerator: ### GPU > ![image](https://github.com/ganamir/MLDAAPP/assets/129692189/bf78551c-d5ea-4cdc-b9d2-0bd4880e073d)
)

- Once connected, simply execute this cell by clicking the start button. ![image](https://github.com/ganamir/MLDAAPP/assets/129692189/cab7e894-02a7-4f1d-86d7-a4b94544322c)

## Data-set Annotation and Training: 
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

### Train your model
Once satisfied, move on to "Train your model" code block, and insert your model of choice (```yolov8x.pt``` or ```yolov8x-seg.pt```), more information at [Models Section](https://docs.ultralytics.com/models/yolov8/#supported-tasks-and-modes) or the FAQ.
Then insert your data.yaml file directory into the specified space, and make sure to change ```imgsz = [w,h] ``` to your desired dimensions (typically used 640x640, or higher resolutions such as 1920x1080 for better detail for small object detection), and add ```project = ""``` directory to save your model in a desired space (Highly recommend saving your model in a google drive folder, as to make sure that no outages and disconnections result in the losing of your trained algorithm).

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



# FAQ
**Where can I get the pre-trained models?**
- At the top of the GitHub "Pre-trained data-sets" leads to the appropriate models.

**My counts are innacurate although it's well trained, why?**
 - Make sure to iterate the ``` conf = ### ``` function to best fit your model to your data.

**Tracking in videos is innacurate and some individuals get reassigned, what can I do about it?**
 - We provide an additional subsection in MLDAAPP, "Manual Video Analysis," where you can individually analyze a video through your trained algorithm, manually re-assign IDs in a video, and extract that data as needed. Unfortunately, no tracker is perfect.

# Deep Dive:
<details>
<summary> ⬇️Click to Expand </summary> 

 # ---- How to use ----
<details>
<summary> ⬇️Click to Expand </summary> 
 <h2> -- Training Set Preparation -- </h2>
<details><summary> - 🔽 - </summary>


 1. Head to [Roboflow](https://roboflow.com/), create an account and sign in and begin annotating your training-set.
    > ⚠️Sometimes roboflow website is not performing as well as it could, so if any issues arise simply restart the page. 


 <details> <summary> ➡️Important Steps to using Roboflow⬅️ </summary>
<div align = "center"> ⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️ </div>
 ___

A. Create a new workspace ``` + Workspace > Academia > "Arbitrary Workspace name"```

B. Create New Project ``` Project Type: Object Detection (Bounding Box) > "Arbitrary name for you detection object" > "Arbitrary name for your project name" ```

C. Select your training set videos/photos then drag and drop in the given menu.

   > 🛑 Depending on the difficult of your scenic composition, you will have to add more data to your training-set. To begin with, aim for ~150-200 pictures with a varying background composition. Try to have a wide range of scenarios present in your data, as it will train the most accurate model.

D. Once uploaded your images click "Save and Continue"
   > 🛑 In the event that uploading does not finish and it is stuck at the infinite upload screen (more than a couple of mins depends on the file size), simply restart the page and try again.

E. Click Assign Images then Start Annotating.

   > 🛑 Roboflow provides multiple tools to assist with annotating images specifically designed to work with "Instance Segmentation" Data, these tools are "Smart Polygon" and "Polygon tool." The former significantly cuts down on the time needed to annotate the object, so I suggest that you familiarize yourself with it. The latter allows for a more manual control over what needs to be annotated. Either way both tools do a great job at creating the data-set. But for a simple Object Detection data set, simply use a bounding box tool.

F. When satisfied with the amount of annotations click on the arrow at the top left corner & click "Add # images to Dataset" located at the top right corner. Finally proceed to step#3.
___
</details>


 3. Once done annotating, add all of your images to the Dataset using 70% Train - 30% Valid or 80% Train - 20% Valid methods.
    > Test set is not important, as I highly suggested creating a seperate video/picture data set with similar or different environmental settings to see how well the model performs.
 4. Then enter the "Generate" section and create the data set.
    > In preproccessing, remove (Resize) function, as we have found it to interfere with our results, especially when training to detect small objects.

    > Augementation is highly dependant on the data set, where some might find a huge improvement others will not.

 5. Generate the set and click "Export Dataset > Format: YOLOv8 > Show Download Code ✔️ > Continue" And finally copy the Download code and keep it into the next section where you will be training and running the computer vision model.
</details>
 
  <h2> Training & Running YOLOv8 </h2>
 <details> <summary> - 🔽 - </summary>

 1. Copy the jupyter notebook that is associated with MLDAAPP into your own google colab drive. 
 
 (Click this:
 <a href="https://colab.research.google.com/drive/1T-VKwfD3VGBhYVhGBEXpWB1HPT_pqOxV?usp=sharing">
 <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
 </a>)

   > ⚠️ Make sure to connect the GPU to reduce the time needed to train the custom model. At the top left corner click ``` Runtime > Change Runtime Time > Hardware accelerator ✔️GPU > GPU type: T4 > Save > Connect ``` If you are using a paid google colab version, highly recommend using A100 GPU which significantly reduces the time needed to train the models. 
2. Run the first: "Install & Import all of dependancies and functions" code block without modyifing anything.
   > ⚠️ A google drive notification will pop-up, simply accept it and log-in to your google account for a massive quality of life improvement when dealing with large or small data-files. So when using ``` project = ... ``` line, always try to save/export to your google drive folder, as being disconnected while using google colab is a common occurence.  
3. If used roboflow for annotating your training-data-set, import the code that you had copied instead of this placeholder code block and run the block.
   ```
   !pip install roboflow
   
   from roboflow import Roboflow
   rf = Roboflow(api_key="Test Code")
   project = rf.workspace("Test Code").project("Test Code")
   dataset = project.version(0).download("Test Code")
   ```

4. Now you will install a folder containing your annotated images with an important "data.yaml" file. Open the folder icon that is located on the left side of the interface, and there you will locate the newly downloaded folder with your traning-set named "NameName-#" Open the folder and double left click the data.yaml file and make sure that it looks similar to what is shown below. If it does, simply right click on the "data.yaml" file and copy its directory through "Copy Path" option.

> ⚠️Make sure that the "data.yaml" looks somewhat similar to what is shown below, especially pay attention to the leading directory of test, train and val lines. It is important that "../" is present prior to test & train & valid directories as otherwise the training algorithm won't be able to find your training data. 
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
 
5. To train your Custom Model:

   A. Select your model ``` modell = YOLO('Model of Your Choice') ```, choice being presented at [YOLOv8](https://github.com/ultralytics/ultralytics). Detection or Segmentation, nano or extra large model is up to you to decide. When done with the choice, simply insert the name instead of the place holder text.
   > ⚠️ Highly recommend starting with any of the [Segmentation Models](https://docs.ultralytics.com/tasks/segment/), as MLDAAPP was designed to be used with them in mind.
   
   > 🛑 Model names are case sensetive, so make sure to write them similar to: "yolov8x-seg.pt," substituting x for your model size of choice.

   B. To train the custom model: ``` modell.train(data = "Insert Your Data.yaml in your training-data-set folder", epochs = 100, imgsz = [original photo/video w, h], batch = 3, project = "Directory to Output the Model") ```. YOLOv8 provides more [arguments](https://docs.ultralytics.com/modes/train/#arguments) that you can tinker around with, so it's best to familiarize yourself with them to make sure you are training the best model.

   > ⚠️ Be ware of the imgsz & batch options. If you are using a free google colab version, then the T4 GPU type might quickly run out of VRAM, promptly stopping your training. A rule of thumb is that the larger the image size the smaller the batch size should be. Though smaller batch sizes will significantly increase the time it takes to train the model.
   
   > ⚠️ Epochs are how many generations the model will be trained for. On the slower GPUs it takes about 2 to 5 minutes on a 150 - 200 image data set. So make sure to iterate on that value.

   > 🛑 When deciding the "project" directory, I highly recommend creating a folder in your google drive directory, as google colab will very likely kick you off while you are training your model, and this way you can always return back and re-/finish training your model.
   
   > 🛑 Change the [w,h] options according to the original video/photo resolution used to train the models. Higher is not always better, so try to downsample the resolution of your data until the object becomes difficult to spot. Otherwise try to maintain the same resolution between your models and the data that you feed it, so if the model is trained on w=1920, try to feed it data that is of the same resolution. 

6. Once you have trained the model select your "best.pt" model from the outputted folder post-training. ``` model = YOLO("Your best.pt file directory") ```. It's often located as such: ``` ./model_output_folder/train#/weights/best.pt ```

### Analyzing Videos:
- Once you are satisfied with your model now acquire your "Test" video to test how the model performs.
   > ⚠️ Best if the Test video was not part of the training-set as it will give you a better idea of the performance. 

- If you need to modify your video to change video length/FPS/speed/resolution use the following command: ``` video_editing("video directory", t0, t1, fps, spd, w) ```. Additionally, add ``` frame = global_video ``` as it will assist you in the next step.
 
- Now use your custom trained model to analyze the video of interest. If you had used step 8 to modify your video, simply run the "Model Usage" code block.
    - If you had not used step 8, simply upload your test video, right click to copy the directory, and add it to  ``` frame = "Test Video Directory" ```
    > ⚠️ [YOLOv8 arguments](https://docs.ultralytics.com/modes/predict/#inference-arguments) to tinker around to maximize your model efficacy and accuracy on the Test data.
    
### Analyzing Photos: (Only for single class counts)
- Similar to Video analysis, you simply have to acquire your photo set after training the model. Once uploaded, head to the bottom of the google colab page and look for "PHOTO MODEL USAGE."

- Once found, insert the directory of your photo folder instead of the placeholder text and run the analysis.

- The model should have saved all the annotated photo results to a folder in a similar fashion as the video analysis. Head to that folder and look whether you are satisfied with the AI annotations and count.

- If model performance is satisfactory, you can use the code cell under the model usage to save the counted data to a .csv file.  

 </details>
</details>



# MLDAAPP Scripts & .csv Outputs
<details>
 <summary> ⬇️Click to Expand </summary>

1. In order to get essential metrics/coordinates for some of the calculations, MLDAAPP provides 3 ways to draw on the images:
   > 🛑 Although may not be essential for some people, still run this code block as the lack of variables may prevent the data-extraction block from running. 
   - ``` draw_dots(img, x1, y1) ``` allows to pin-point the nessesary coordinate for point q-object-distance calculations.
     > To set your custom q-coordinate simply add ``` q = [x1, y1] ``` with your own coordinates.
   - ``` draw_lines(img, x1, y1, x2, y2) ``` helps in calculating pixels_per_centimeter measurments if needed.
     > To get a somewhat accurate pixels/cms conversion it is helpful to have a ruler/object of a known size within the video frame. Then simply draw a line for the whole length of the object, and use the difference between point 1 & 2 as the pixel length and perform simple conversions to get your variable.  
   - ``` draw_polygons(img, x1, y1, x2, y2, x3, y3, x4, y4) ``` helps in determining the coordinates needed for object_within_area_counting metrics.
     > In order to calculate how many objects are within a certain space, it is important to set the correct coordinates for your space of interest. Once done drawing a polygon around your area, simply create variables as such ``` coords1/2/3/... = [[x1,y1],[x2,y2],[x3,y3],[x4,y4]] ``` 

2. Lastly run Data Extraction Block without modifying anything. This will create the dataframes with your outputs.
   > 🛑 If you are unhappy with the ID re-assignment, MLDAAPP provides the ability to manually modify the IDs. Simply return to the Data Extraction block, and locate the "Reassign IDs" section. After running the block you should have seen the code output being a dataframe with numerical assignments for each of the IDs in each of the section. These numbers are simply the amount of times the object was tracked, so if you had a video with a lenght of 1800 frames, then you would ideally have all of your objects at an 1800 value for each of the sections. MLDAAPP provides 3 ways to filter the data:
   
   > A. rename IDs using ``` df5['ID'] = df5['ID'].replace([2],[1]) ```, here you turn ID 2 into ID 1. Make sure to turn higher ID values into lower ones, as doing it the other way may  cause frame assignment problems.
   
   > B. Down at the bottom of the code cell you may locate an ID Removal section which will assist in removing any columns under a certain presence threshold ``` df5 = df5.groupby('ID').filter(lambda x : len(x > ###)) ```. Substituing ### for any numerical threshold. Or removing any specific ID ``` df5 = df5[df5.ID != 1] ```, here you remove anything related to ID 1.

3. In order to save these data frames into human-viewable objects, use the last block to save the files.
   > ⚠️ Make sure to change the directory & names of the 3 saving files, maintaining .csv at the end of the file names. It should generally look like this ``` df#.to_csv('directory/filename.csv') ```
 
</details>







