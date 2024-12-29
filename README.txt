# README.txt

```
# Backdoor Adversarial Machine Learning Attacks on IoT Traffic Using GCNs

# Description
This repository contains a dataset and code for analyzing the impact of backdoor adversarial machine learning attacks on IoT traffic. The dataset was created as part of ongoing research to understand misclassification and other vulnerabilities in IoT systems, particularly using Graph Convolutional Networks (GCNs). The dataset can also be used for broader research on attack detection and classification in the Internet of Medical Things (IoMT) and other IoT environments.

# Dataset Files Included
ICU_Env2_MQTT01.csv
ICU_Env2_MQTT02.csv
malaria_part_1.csv
malaria_part_10.csv
malaria_part_2.csv
malaria_part_3.csv
malaria_part_4.csv
malaria_part_5.csv
malaria_part_6.csv
malaria_part_7.csv
malaria_part_8.csv
malaria_part_9.csv
mqtt_bed1.csv
slowite.csv

# Feature Columns
The dataset contains the following feature columns:
frame.time_delta
frame.time_relative
frame.len
ip.src
ip.dst
tcp.srcport
tcp.dstport
tcp.flags
tcp.time_delta
tcp.len
tcp.ack
tcp.connection.fin
tcp.connection.rst
tcp.connection.sack
tcp.connection.syn
tcp.flags.ack
tcp.flags.fin
tcp.flags.push
tcp.flags.reset
tcp.flags.syn
tcp.flags.urg
tcp.hdr_len
tcp.payload
tcp.pdu.size
tcp.window_size_value
tcp.checksum
mqtt.clientid
mqtt.clientid_len
mqtt.conack.flags
mqtt.conack.val
mqtt.conflag.passwd
mqtt.conflag.qos
mqtt.conflag.reserved
mqtt.conflag.retain
mqtt.conflag.willflag
mqtt.conflags
mqtt.dupflag
mqtt.hdrflags
mqtt.kalive
mqtt.len
mqtt.msg
mqtt.msgtype
mqtt.qos
mqtt.retain
mqtt.topic
mqtt.topic_len
mqtt.ver
mqtt.willmsg_len
ip.proto
ip.ttl

# Usage Instructions
1. Download the repository ZIP file or clone the repository:
   - Clone: git clone https://github.com/mgeorgiades/UDA_FinalProject_georgiades.git
   - Download ZIP: Use the "Code" button on GitHub to download the ZIP file.

2. To automate the download and unzip process, use the following Python code:
import os
import requests
import zipfile

current_directory = os.getcwd()
GITHUB_ZIP_URL = "https://github.com/mgeorgiades/UDA_FinalProject_georgiades/archive/refs/heads/main.zip"
local_zip_path = os.path.join(current_directory, "UDA_FinalProject_georgiades.zip")
extraction_directory = os.path.join(current_directory, "UDA_FinalProject_georgiades")

response = requests.get(GITHUB_ZIP_URL, stream=True)
if response.status_code == 200:
    with open(local_zip_path, "wb") as zip_file:
        for chunk in response.iter_content(chunk_size=8192):
            zip_file.write(chunk)
    print(f"ZIP file downloaded successfully to {local_zip_path}")
else:
    raise Exception(f"Failed to download ZIP file. HTTP Status Code: {response.status_code}")

with zipfile.ZipFile(local_zip_path, 'r') as zip_ref:
    zip_ref.extractall(extraction_directory)
print(f"Files extracted to {extraction_directory}")

3. Combine the CSV files into a single dataset:
import pandas as pd

csv_directory = os.path.join(extraction_directory, "UDA_FinalProject_georgiades-main")
combined_output_path = os.path.join(current_directory, "UDA_FinalProject_georgiades.csv")

combined_data = []
for file_name in os.listdir(csv_directory):
    if file_name.endswith(".csv"):
        file_path = os.path.join(csv_directory, file_name)
        df = pd.read_csv(file_path, low_memory=False)
        combined_data.append(df)

combined_df = pd.concat(combined_data, ignore_index=True)
combined_df.to_csv(combined_output_path, index=False)
print(f"Combined dataset saved at {combined_output_path}")

# Disclaimer and Acknowledgment
The dataset used in this coursework is part of ongoing collaborative work between myself and one of the main authors and developers of IoT-Flock. The dataset was generated using IoTFlock by the author and was provided privately and directly to me for the purposes of ongoing research collaboration and for the completion of this coursework. Analysis of this dataset for the purposes of this coursework was done solely by me.

The dataset is distinct from publicly available resources and is not yet released for public access. Its sharing or distribution is prohibited until it is officially released by the authors under an appropriate license.

# Contact
For further inquiries, contact:
Dr. Michael Georgiades (mg723@ic.ac.uk)
```

