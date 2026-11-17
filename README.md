# AI-Based Network Intrusion Detection System

A machine-learning network intrusion detection system (NIDS) with a Streamlit dashboard. It learns to tell normal network traffic from attack traffic using the CIC-IDS2017 dataset, and lets you try the trained model on simulated traffic flows.

> Built as part of the AICTE x VOIS for Tech Cybersecurity with Gen AI internship programme (Edunet Foundation).

## What it does

- Trains a **Random Forest** classifier on labelled network-flow data (CIC-IDS2017) from inside the dashboard, using the **Train Model Now** button.
- Shows the model's **test accuracy** after training.
- Includes a **Live Traffic Simulator**: enter flow features, click **Analyze Traffic**, and the model classifies the flow as **normal** or **intrusion**.

## Screenshots

| Normal traffic | Intrusion detected |
|---|---|
| ![Normal traffic](screenshots/dashboard-normal-traffic.png) | ![Intrusion detected](screenshots/dashboard-intrusion-detected.png) |

## Tech stack

| Area | Tools |
|---|---|
| Language | Python |
| ML | scikit-learn (Random Forest) |
| Data | Pandas, NumPy |
| UI | Streamlit |
| Dataset | [CIC-IDS2017](https://www.unb.ca/cic/datasets/ids-2017.html) (Canadian Institute for Cybersecurity) |

## Dataset

Uses CIC-IDS2017 network-flow CSVs. The version used here is the Friday afternoon DDoS capture:
`Friday-WorkingHours-Afternoon-DDos.pcap_ISCX.csv`.

The dataset is large and is **not included** in this repo. Download it from the link above and place the CSV in the project folder.

## How to run

```bash
# 1. Clone
git clone https://github.com/AbhignaMN/Network_Intrusion_Detection_System.git
cd Network_Intrusion_Detection_System

# 2. Install dependencies
pip install streamlit pandas numpy scikit-learn

# 3. Add the dataset CSV (see above) to this folder

# 4. Start the app
streamlit run nids_main.py
```

Open http://localhost:8501, click **Train Model Now** in the sidebar, then use the Live Traffic Simulator.

## Using the simulator

Enter values for these flow features and click **Analyze Traffic**:

- Flow Duration
- Total Forward Packets
- Total Backward Packets
- Total Length of Forward Packets
- Total Length of Backward Packets

## Results

- Test accuracy: **<FILL IN from the "Model trained! Accuracy" message>**
- Training data: **<FILL IN: number of rows / attack vs normal split>**

## Limitations

- The simulator takes manually entered values; it does not capture live packets from a network.
- The model is trained on a single day of CIC-IDS2017 (DDoS traffic), so it is not expected to detect other attack types.
- It is a learning project, not a production security tool.

## Future work

- Train on multiple CIC-IDS2017 days to cover more attack types (port scan, brute force, web attacks).
- Add precision, recall and a confusion matrix, since accuracy alone can mislead on imbalanced data.
- Feed the model from real packet captures.
- Save and load the trained model instead of retraining each session.

## Author

**Abhigna M N**: [GitHub](https://github.com/AbhignaMN) | [LinkedIn](https://linkedin.com/in/abhigna-m-n-0a8752295)

