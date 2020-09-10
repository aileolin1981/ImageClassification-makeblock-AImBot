# ImageClassification-makeblock-AImBot
ImageClassification makeblock AImBot. 
Use AI Image Classification to control makeblock mBot.

# Standard Operation Procedure
## Image Classification
Use Google Teachable Machine to training image classification AI model.  
https://teachablemachine.withgoogle.com/train/image  

Define 5 classes as "GO", "BACK", "Right", "Left", and "OTHER"(stop).  
Use the "webcam" button to capture each class image.  

After preparing all images for each class, press "Train Model" to train your own model.  
***Note: Do NOT switch the Tab.      

When training done, export your model as Tensorflow.js format and download it.  
There are three files "metadata.json", "model.json", and "weights.bin" in your download.  
And then copy the javascript code which provide from export diagram as classification.js

<img width="350px" height="250px" src="README_PIC/Google Teachable Machine export diagram.png" />

Prepare one simple HTML index.html to be your User Interface.  
Reference this repository index.html, classification.js, and downloaded AI model which in CF_MODEL folder.  
You can do classification for the 5 classes which you defined.  

## Control the mBot
Download the "webbluetooth_mBot.js" as mBot control lib and include in your project.  
Define different action for 5 classification, and do the determination in the function "predict()" of classification.js.  
Finial, use webblue to connect the mBot, please reference in the function "connect_mBot()" of webbluetooth_mBot.js.    

When all thing done, you can control the mBot via image classification.  
