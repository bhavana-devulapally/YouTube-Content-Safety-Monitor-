
# **YouTube Safety Index: A Retrieval and Classification System**

## **Overview**  
The YouTube Safety Index helps parents/guardians monitor and analyze YouTube content consumed by children, ensuring safer video consumption. Using Information Retrieval (IR) techniques and a BERT-based Machine Learning (ML) model, the system classifies and alerts users of potentially unsafe videos in real time.

---

## **Key Features**
- **YouTube Traffic Monitoring:** Captures YouTube traffic from the household network.  
- **Content Indexing:** Indexes video logs into **ElasticSearch** for efficient storage and search.  
- **Content Classification:** Classifies videos as **safe** or **unsafe** using a **BERT-based model**.  
- **Real-Time Alerts:** Notifies users via **SMTP email** and **Kibana alerts**.  
- **Actionable Dashboard:** Visualizes video safety status and insights in a user-friendly interface.

---

## **Installation Steps**
1. **Clone the Repository:**
   ```bash
   git clone https://github.com/your-repo/youtube-safety-index.git
   cd youtube-safety-index
   ```

2. **Install Dependencies:**  
   Install Python packages from `requirements.txt`:  
   ```bash
   pip install -r requirements.txt
   ```

3. **Set Up ElasticSearch & Kibana:**  
   - Install **ElasticSearch** and **Kibana** locally or on Docker.  
   - Configure ElasticSearch for indexing YouTube logs and Kibana for visualization.

4. **Configure YouTube API:**  
   - Create a project in **Google Cloud Console** and enable **YouTube Data API v3**.  
   - Set your API key as an environment variable:  
     ```bash
     export YOUTUBE_API_KEY="your_api_key"
     ```

5. **Run Traffic Capture:**  
   - Use **Postman Proxy** with SSL bumping to capture YouTube traffic.  
   - Redirect captured URLs and metadata to ElasticSearch.

---

## **Components**
1. **Traffic Capture:** Captures YouTube traffic using **Postman Proxy**.  
2. **ElasticSearch Indexing:** Indexes video metadata, URLs, timestamps, and IDs.  
3. **Metadata & Transcript Retrieval:** Uses the **YouTube Data API** to fetch video details and captions.  
4. **Content Categorization:**  
   - Classifies videos using a **BERT-based ML model**.  
   - Predefined lexicons detect profanity, violence, and abusive content.  
5. **Real-Time Alerts:**  
   - **Kibana alerts** and **SMTP email notifications** for unsafe content.

---

## **Model Performance**
| Metric         | Unsafe Videos (Class 0) | Safe Videos (Class 1) | Weighted Avg |
| -------------- | ----------------------- | --------------------- | ------------ |
| Precision      | 0.86                    | 0.77                  | -            |
| Recall         | 0.90                    | 0.69                  | -            |
| F1-Score       | 0.88                    | 0.73                  | 0.83         |
| Accuracy       | -                       | -                     | **83%**      |

---

## **Technologies Used**
- **Python:** Core programming language for scripts and model development  
- **BERT:** Pretrained model for content classification  
- **YouTube Data API v3:** Video metadata and caption retrieval  
- **ElasticSearch:** Fast indexing and retrieval of YouTube logs  
- **Kibana:** Data visualization and real-time alert setup  
- **Postman Proxy:** Captures YouTube traffic  
- **SMTP:** Email alerts for unsafe content  

---

## **How It Works**
1. **Traffic Capture:** Monitors household Wi-Fi and captures YouTube video data.  
2. **Data Indexing:** Processes and indexes the captured logs into **ElasticSearch**.  
3. **Metadata Retrieval:** Retrieves metadata and transcripts using the **YouTube API**.  
4. **Classification:** Classifies videos as safe or unsafe using the **BERT model**.  
5. **Alerts:** Notifies users through real-time **Kibana** and **SMTP alerts**.

---

## **Use Cases**
- **Parents/Guardians:** Monitor and receive alerts for unsafe content.  
- **Developers/Researchers:** Extend and experiment with content safety models.

---

## **License**
This project is licensed under the [MIT License](LICENSE).

---

## **Acknowledgements**
- **ElasticSearch** and **Kibana** for data indexing and visualization  
- **BERT** for text classification tasks  
- **YouTube Data API** for metadata retrieval  

