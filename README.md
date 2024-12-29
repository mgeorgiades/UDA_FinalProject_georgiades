# UDA_FinalProject_georgiades

UDA Final Project: Exploring Misclassification Effects of Backdoor Adversarial Machine Learning Attacks on IoT Traffic with GCNs

Overview  
This repository contains a dataset and associated files for the Unstructured Data Analysis (UDA) Final Project. The dataset was generated using the IoT-Flock framework and includes labeled MQTT traffic data for analysis, classification, and detection of adversarial attacks in IoT systems. This repository serves as a resource for ongoing research and coursework aimed at exploring IoT security challenges and solutions using advanced machine learning techniques.

Repository Contents  
This repository includes the following files:  
- ICU_Env2_MQTT01.csv: MQTT network traffic data from ICU environment (Benign).  
- ICU_Env2_MQTT02.csv: MQTT network traffic data from ICU environment (Benign).  
- malaria_part_1.csv – malaria_part_10.csv: Segmented network traffic data representing attack simulations labeled as "Malaria."  
- slowite.csv: MQTT attack simulation labeled as "Slowite."  
- mqtt_bed1.csv: MQTT traffic from IoT bed device (Benign).  
- README.md: Detailed project and dataset description.

Dataset Purpose  
The dataset serves as a basis for:  

1. Adversarial Attack Simulation and Detection:  
   Demonstrating the application of Graph Convolutional Networks (GCNs) for detecting backdoor and adaptive adversarial attacks in IoT-based MQTT traffic.  

2. Feature Engineering and Labeling:  
   Training machine learning models on binary and multi-class labeled datasets to distinguish between benign and malicious IoT traffic.  

3. Unstructured Data Analysis Techniques:  
   Exploring techniques to classify and analyze large-scale IoT network traffic datasets for security.

Download Instructions  
You can download the dataset manually or programmatically using Python.  

Manual Download:  
1. Visit the repository at https://github.com/mgeorgiades/UDA_FinalProject_georgiades.  
2. Click the "Code" button and select "Download ZIP."  
3. Extract the ZIP file into your working directory.

Programmatic Download:  
The following Python code allows you to download the ZIP file programmatically to your working directory:

import os  
import requests  

current_directory = os.getcwd()  
print(f"Current working directory: {current_directory}")  

GITHUB_ZIP_URL = "https://github.com/mgeorgiades/UDA_FinalProject_georgiades/archive/refs/heads/main.zip"  
local_zip_path = os.path.join(current_directory, "UDA_FinalProject_georgiades.zip")  

print(f"Downloading ZIP file from {GITHUB_ZIP_URL}...")  
response = requests.get(GITHUB_ZIP_URL, stream=True)  

if response.status_code == 200:  
    with open(local_zip_path, "wb") as zip_file:  
        for chunk in response.iter_content(chunk_size=8192):  
            zip_file.write(chunk)  
    print(f"ZIP file downloaded successfully and saved as {local_zip_path}")  
else:  
    raise Exception(f"Failed to download ZIP file. HTTP Status Code: {response.status_code}")  

Disclaimer and Acknowledgment  
The dataset used in this coursework is part of ongoing collaborative work between myself and one of the main authors and developers of IoT-Flock. The dataset was generated using IoT-Flock by the author and was provided privately and directly to me for the purposes of ongoing research collaboration and for the completion of this coursework. Analysis of this dataset for the purposes of this coursework was done solely by me.  

The dataset is distinct from publicly available resources and is not yet released for public access. Its sharing or distribution is strictly prohibited until it is officially released by the authors under an appropriate license.

Associated Public Resources  
1. IoT Healthcare Security Dataset  
Citation: Faisal Hussain, Syed Ghazanfar Abbas, Ghalib A. Shah, Ivan Miguel Pires, Ubaid U. Fayyaz, Farrukh Shahzad, Nuno M. Garcia, Eftim Zdravevski, "IoT Healthcare Security Dataset," IEEE DataPort, August 13, 2021, doi: 10.21227/9w13-2t13.  
Access: https://dx.doi.org/10.21227/9w13-2t13  

2. IoT-Flock Framework  
Citation: S. Ghazanfar, F. Hussain, A. U. Rehman, U. U. Fayyaz, F. Shahzad, and G. A. Shah, "IoT-Flock: An Open-source Framework for IoT Traffic Generation," 2020 International Conference on Emerging Trends in Smart Technologies (ICETST), Karachi, Pakistan, 2020, pp. 1–6, doi: 10.1109/ICETST49965.2020.9080732.  
Repository: https://github.com/ThingzDefense/IoT-Flock  

Citation  
If you use this dataset or its analysis in your research or coursework, please acknowledge it as follows:  
- Citation for IoT-Flock: S. Ghazanfar et al., IoT-Flock Framework for IoT Traffic Generation.  
- Personal Contribution: Dataset analysis and experiments conducted as part of coursework by Michael Georgiades.

Contact  
For any inquiries regarding this dataset or project:  
Contact Point: Dr. Michael Georgiades  
Email: mg723@ic.ac.uk  

--- 
