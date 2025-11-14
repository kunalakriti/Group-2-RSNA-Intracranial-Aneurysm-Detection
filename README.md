# Group-2-RSNA-Intracranial-Aneurysm-Detection
Group 2 ML project on RSNA Intracranial Aneurysm Detection

RSNA Intracranial Aneurysm Detection Project

We're building a system to automatically find and map intracranial aneurysms from 3D medical scans (CTA scans, to be exact). This file will walk you through how to get the code running on your machine.

1.  (Prerequisites) 

Python: We're using Python 3.8 or newer. This is what all our scripts are written in.

Python Libraries: We are using bunch of Python libraries which are:

pytorch (or tensorflow): This is for building and training our deep learning models.

monai (or similar tools like nibabel): This helps us read, write, and work with the 3D medical images.

numpy & pandas: For handling all the data and numbers efficiently.

scikit-learn: For calculating performance metrics.

kaggle: This is super handy for downloading the dataset directly from the competition.

...and a few others for visualization and progress bars (matplotlib, tqdm).

A Good GPU (Highly Recommended!):
We're working with large 3D scans, which takes a lot of computing power. For training the model, you'll really want a CUDA-enabled GPU (like an NVIDIA card). It'll make the difference between training in hours versus days.

[ 2. How to Get It Running ]

Step 1: Get the Code
First, you'll need to download the project code. If you're using Git, just clone the repository:
git clone [https://github.com/kunalakriti/Group-2-RSNA-Intracranial-Aneurysm-Detection]
...and then cd into the new project folder.

Step 2: Set Up Your Workspace (Virtual Environment)
It's a very good practice to create a clean "virtual environment" for the project. This keeps all its specific libraries (the ones from requirements.txt) separate from your other Python projects.

Step 3: Install All the Libraries
Now that your environment is active, just run this command:
pip install -r requirements.txt
This will read the requirements.txt file and install all the libraries we need.

Step 4: Download the Dataset
This project needs data! You'll have to download it from the RSNA Intracranial Aneurysm Detection Challenge on Kaggle.
Link: [https://www.kaggle.com/code/kunalakriti/predict-aneurysm]

Step 5: Pre-process the Data
The raw scans need to be normalized and resized so our model can understand them. We have a script for this. Run something like:
python preprocess.py --data_dir data/ --output_dir data/processed/

This will create a new data/processed/ folder with the ready-to-use scans.

Step 6: Train Your Model!
This is the fun part. It's time to teach the AI. You'll run the training script. You can usually specify which model you want to train (like our 3D U-Net) and for how long (epochs).

python train.py --model 3d_unet --data_dir data/processed/ --epochs 100 --batch_size 4

This will start the training process and save the best-performing model in a models/ folder.

Step 7: See How It Did (Evaluation)
Once you have a trained model, you can test it on the validation or test data to see how well it performs.
python evaluate.py --model_path models/best_model.pth --test_dir data/processed/test/

This will give you scores like the Dice Coefficient and F1-score, which tell us how accurate the aneurysm detection is.

That's the basic workflow! If you run into any problems, double-check the folder paths and make sure all the libraries from requirements.txt are installed.
