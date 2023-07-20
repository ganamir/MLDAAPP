<p align="center">
 <img src="https://github.com/ganamir/MLDAPP/assets/129692189/c684e3b2-9df1-4177-9abd-2e22ec30810f" height = "300">
</p>

<div align = "center"> 
<b>
<h1>
  MLDAAPP 
</h1>
</b>
</div>

<div align = "center"> 
<h4>
  Machine Learning Data Acquisition for Assesing Population Phenotypes based on <a href = "https://github.com/ultralytics/ultralytics">YOLOv8</a>. 
</h4>
</b>
</div>
<div align = "center">
<img alt="GitHub followers" src="https://img.shields.io/github/followers/ganamir"> <img alt="GitHub Repo stars" src="https://img.shields.io/github/stars/ganamir/MLDAPP"> <img alt="GitHub commit activity (branch)" src="https://img.shields.io/github/commit-activity/t/ganamir/MLDAPP"> <img alt="GitHub last commit (branch)" src="https://img.shields.io/github/last-commit/ganamir/MLDAPP/main">
</div>
<div align = "center">
<h4>
 | <a href = "https://github.com/ganamir/MLDAAPP/edit/main/README.md#key-features"> Key Features </a> | <a href = "https://github.com/ganamir/MLDAAPP/edit/main/README.md#how-to-use"> How to Use </a> | <a href = "https://github.com/ganamir/MLDAAPP/edit/main/README.md#mldaapp-csv-outputs"> Outputs </a> |
</h4>
</div>
<div align = "center"> <p> 
<img src = "https://github.com/ganamir/MLDAAPP/assets/129692189/20066b97-dc1e-4882-a588-8aff485404dc" hspace = "5" height = "100">
<img src = "https://github.com/ganamir/MLDAAPP/assets/129692189/0539cbaf-955e-475d-bd4b-30cc153a9956" hspace = "5" height = "100" >
<img src = "https://github.com/ganamir/MLDAAPP/assets/129692189/4fda3b16-6200-44b2-bba6-393d7475fb28" hspace = "5" height = "100" >
</p></div>

<div align = "center"> <p> 
 | <a href = "https://drive.google.com/drive/folders/1t6K05ucDLfYnNPZ0ddboAz4vdq3WrCOa?usp=sharing"> Fruit Flies </a> |
 <a href = "https://drive.google.com/drive/folders/1AO-t3DIOKdH7gkiKqyn4ymQ1XZr-srwZ?usp=sharing"> Hamsters </a> |
 <a href = "https://drive.google.com/drive/folders/1aQ10fsA_LZhURsEHc7x2JYWzwjXsw5a9?usp=sharing"> Bees </a> |
</p></div>

<div align = "center"> 

Copy me to drive:
<a href="https://colab.research.google.com/drive/1T-VKwfD3VGBhYVhGBEXpWB1HPT_pqOxV?usp=sharing">
 <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

</div>

# Key Features 

- Object Tracking (YOLOv8 x Tracker)
  - Maintaining object IDs
- Object Counts
  - Within every picture (or every frame if video)
  - Within user defined space
- Centoid Position of every object
  - Within every picture (or every frame if video)
- Object Centroid Position away from point q
  - Point q is a user defined position
- Object Centroid Distance away from initial position (t=0 position)
- Total Object Centroid Displacement
- Object Surface Area (only with segmentation model)

# How to use
<details>
<summary> Click to Expand </summary>
 <h2> Training Set Preparation </h2>
 <details>

 1. Head to [Roboflow](https://roboflow.com/), create an account and sign in.
 2. Create a Workspace, then create a New Project.
    > Depending on what YOLOv8 model you will be using, you will have to decide what project type you will need. (Object detection is the best/simplest way to begin using MLDAAPP)
 3. Once you have created the project, import the videos/photos that you would like to turn into your training set & begin annotating the objects of interest.
 4. Once done annotating, add all of your images to the Dataset using 70% Train - 30% Valid or 80% Train - 20% Valid methods.
    > Test set is not important, as I highly suggested creating a seperate video/picture data set with similar or different environmental settings to see how well the model performs.
 5. Then enter the "Generate" section and create the data set.
    > In preproccessing, remove (Resize) function, as we have found it to interfere with our results, especially when training to detect small objects.

    > Augementation is highly dependant on the data set, where some might find a huge improvement while other will not.

 6. Generate the set and click "Export Dataset > Format: YOLOv8 > Show Download Code ✔️ > Continue" And finally copy the Download code and keep it into the next section where you will be training and running the computer vision model. 
 </details>
 
  <h2> Training & Running YOLOv8 </h2>
 <details>

1. Copy the jupyter notebook that is associated with MLDAAPP into your own google colab drive.
   > ⚠️ Make sure to connect the GPU to reduce the time needed to train the custom model. At the top left corner click ``` Runtime > Change Runtime Time > Hardware accelerator ✔️GPU > GPU type: V100 > Save > Connect ``` If you are using a paid google colab version, highly recommend using A100 GPU which significantly reduces the time needed to train the models. 
3. Run the first: "Install & Import all of dependancies and functions" code block without modyifing anything.
   > ⚠️ A google drive notification will pop-up, simply accept it and log-in to your google account for a massive quality of life improvement when dealing with large or small data-files.
4. If used roboflow for annotating your training-data-set, import your training set into the training set block and run the commands.
   ```
   !pip install roboflow
   
   from roboflow import Roboflow
   rf = Roboflow(api_key="Test Code")
   project = rf.workspace("Test Code").project("Test Code")
   dataset = project.version(0).download("Test Code")
   ```

   > ⚠️ You should download a folder containing your annotated images with an imporant "data.yaml" file. Right click on the file and copy its directory which will be used to train your Custom Model.
 
5. To train your Custom Model:

   A. Select your model ``` modell = YOLO('Model of Your Choice') ```, choice being presented at [YOLOv8](https://github.com/ultralytics/ultralytics). Detection or Segmentation, nano or extra large model is up to you to decide. When done with the choice, simply insert the name instead of the place holder text.

   B. To train the custom model: ``` modell.train(data = "Insert Your Data.yaml in your training-data-set folder", epochs = 100, imgsz = [original photo/video w, h], batch = 3, project = "Directory to Output the Model") ```. YOLOv8 provides more [arguments](https://docs.ultralytics.com/modes/train/#arguments) that you can tinker around with, so it's best to familiarize yourself with them to make sure you are training the best model.

   > ⚠️ Be ware of the imgsz & batch options. If you are using a free google colab version, then the V100 GPU type might quickly run out of VRAM, promptly stopping your training. A rule of thumb is that the larger the image size the smaller the batch size should be. Though smaller batch sizes will significantly increase the time it takes to train the model.
   
   > 🛑 When deciding the "project" directory, I highly recommend creating a folder in your google drive directory, as google colab can very likely kick you off while you are training your model, and this way you can always return back and re-/finish training your model.  
7. Once you have trained the model select your "best.pt" model from the outputted folder post-training. ``` model = YOLO("Your best.pt file directory") ```. It's often located as such: ``` ./model_output_folder/train#/weights/best.pt ```

8. Once you are satisfied with your model now acquire your "Test" video to test how the model performs.
   > ⚠️ Best if the Test video was not part of the training-set as it will give you a better idea of the performance. 

9. If you need to modify your video to change video length/FPS/speed use the following command: ``` video_editing("video directory", t0, t1, fps, spd) ```. Additionally, add ``` frame = global_video ``` as it will assist you in the next step.
 
10. Now use your custom trained model to analyze the video of interest. If you had used step 8 to modify your video, simply run the "Model Usage" code block.
    - If you had not used step 8, simply upload your test video, right click to copy the directory, and add it to  ``` frame = "Test Video Directory" ```
    > ⚠️ [YOLOv8 arguments](https://docs.ultralytics.com/modes/predict/#inference-arguments) to tinker around to maximize your model efficacy and accuracy on the Test data.
 </details>
</details>

# MLDAAPP Scripts & .csv Outputs
<details>
 <summary> Click to Expand </summary>

1. In order to get essential metrics/coordinates for some of the calculations, MLDAAPP provides 3 ways to draw on the images:
   - ``` draw_dots(img, x1, y1) ``` allows to pin-point the nessesary coordinate for point q-object-distance calculations.
     > To set your custom q-coordinate simply add ``` q = [x1, y1] ``` with your own coordinates.
   - ``` draw_lines(img, x1, y1, x2, y2) ``` helps in calculating pixels_per_centimeter measurments if needed.
     > To get a somewhat accurate pixels/cms conversion it is helpful to have a ruler/object of a known size within the video frame. Then simply draw a line for the whole length of the object, and use the difference between point 1 & 2 as the pixel length and perform simple conversions to get your variable.  
   - ``` draw_polygons(img, x1, y1, x2, y2, x3, y3, x4, y4) ``` helps in determining the coordinates needed for object_within_area_counting metrics.
     > In order to calculate how many objects are within a certain space, it is important to set the correct coordinates for your space of interest. Once done drawing a polygon around your area, simply create variables as such ``` coords1/2/3/... = [[x1,y1],[x2,y2],[x3,y3],[x4,y4]] ``` 

2. Lastly run Data Extraction Block without modifying anything. This will create the dataframes with your outputs.
   > 🛑 If you are unhappy with the ID re-assignment, MLDAAPP provides the ability to manually modify the IDs. Simply return to the Data Extraction block, and move to the "Reassign IDs for _main_ dataframe" section. After running the block you should have seen the code output being a dataframe with numerical assignments for each of the IDs in each of the section. These numbers are simply the amount of times the object was tracked, so if you had a video with a lenght of 1800 frames, then you would ideally have all of your objects at an 1800 value for each of the sections. MLDAAPP provides 3 ways to filter the data:
   
   > A. rename IDs using ``` df5['ID'] = df5['ID'].replace([2],[1]) ```, here you turn ID 2 into ID 1. Make sure to turn higher ID values into lower ones, as doing it the other way may cause frame assignement problems.
   
   > B. Remove any columns under a certain presence threshold ``` df5 = df5.groupby('ID').filter(lambda x : len(x > ###)) ```. Substituing ### for any numerical threshold.
   
   > C. Removing any specific ID ``` df5 = df5[df5.ID != 1] ```, here you remove anything related to ID 1. 
4. In order to save these data frames into human-viewable objects use the last block to save the files.
   > ⚠️ Make sure to change the directory & names of the 3 saving files, maintaining .csv at the end of the file names. It should generally look like this ``` df#.to_csv('directory/filename.csv') ```
 
</details>






