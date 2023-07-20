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
 
go to roboflow and do stuff

  
 </details>
 
  <h2> Model-Script Usage </h2>
 <details>

1. Copy the jupyter notebook that is associated with MLDAAPP into your own google colab drive.
   > ⚠️ Make sure to connect the GPU to reduce the time needed to train the custom model. At the top left corner click ``` Runtime > Change Runtime Time > Hardware accelerator ✔️GPU > GPU type: V100 ``` If you are using a paid google colab version, highly recommend using A100 GPU which significantly reduces the time needed to train the models. 
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

   B. To train the custom model: ``` modell.train(data = "Insert Your Data.yaml in your training-data-set folder", epochs 200, imgsz = [w, h], batch = 5, project = "Directory to Output the Model") ```. YOLOv8 provides more [arguments](https://docs.ultralytics.com/modes/train/#arguments) that you can tinker around with, so it's best to familiarize yourself with them to make sure you are training the best model.

   > ⚠️ Be ware of the imgsz & batch options. If you are using a free google colab version, then the V100 GPU type might quickly run out of VRAM, promptly stopping your training. A rule of thumb is that the larger the image size the smaller the batch size should be. Though smaller batch sizes will significantly increase the time it takes to train the model.
6. Once you have trained the model select your "best.pt" model from the outputted folder post-training. ``` model = YOLO("Your best.pt file directory") ```. It's often located as such: ``` ./model_output_folder/train#/weights/best.pt ```

7. Once you are satisfied with your model now acquire your "Test" video to test how the model performs.
   > ⚠️ Best if the Test video was not part of the training-set as it will give you a better idea of the performance. 
 
 </details>
</details>

# MLDAAPP .csv Outputs
<details>
 <summary> Click to Expand </summary>
 
</details>






