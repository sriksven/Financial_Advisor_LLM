## Summary
The project addresses a critical gap in personal finance management, where traditional tools often fail to keep up with the rapidly changing and complex demands of modern financial planning. This challenge results in delayed, inaccurate, or generalized advice, which can hinder individuals from making optimal financial decisions. Leveraging advancements in Artificial Intelligence (AI), particularly Large Language Models (LLMs), this project aims to develop an AI-driven financial advisory tool capable of delivering real-time, personalized financial insights that cater to individual needs in areas like budgeting, investment analysis, and risk assessment.

### Project Goals and Background

The primary objective is to create a scalable, AI-powered financial assistant that provides expert-level financial guidance in real time. By fine-tuning LLMs on financial data, the tool delivers targeted advice for personal finance tasks, including credit management, investment strategies, and savings optimization. This project seeks to democratize access to high-quality financial advice, making it accessible to a broader audience, regardless of their financial literacy.

### Research Questions and Hypotheses
* #### How can LLMs improve the accuracy and timeliness of financial advice?
**Hypothesis:** Fine-tuning on financial datasets enhances the model’s contextual relevance, enabling it to offer precise, tailored recommendations.
* #### Can QLoRA (Quantized Low-Rank Adaptation) achieve efficient fine-tuning without high computational costs?
**Hypothesis:** Using QLoRA enables rapid adaptation to financial contexts, providing accurate, resource-efficient advice and making the model scalable.

#### Related Work and Datasets
The project builds on recent research in financial AI, particularly in real-time data retrieval and language processing, using advanced methods like Low-Rank Adaptation (LoRA) to improve accuracy and responsiveness. Two primary datasets serve as the foundation:
* **Alpaca News API:** Real-time financial news data that keeps the model up-to-date with market trends.
* **Hugging Face Finance-Alpaca Dataset:** A question-answer dataset focused on finance to train the model on common financial inquiries, providing it with essential background knowledge.

#### Methods
The tool’s development involves data collection, preprocessing, fine-tuning, and deployment. After data cleaning and embedding, the processed data is stored in a Vector Database (Qdrant) for efficient retrieval. LoRA is used to fine-tune the model to specialize in financial topics, ensuring responses remain relevant and contextually accurate. The model is then deployed using a RESTful API, with Gradio providing an intuitive user interface for interactions.

#### Results
Preliminary results indicate that the model successfully provides accurate, real-time financial advice tailored to individual queries. The combination of LLM fine-tuning and real-time retrieval enables a responsive, contextually aware financial assistant that adapts to dynamic user needs. This tool demonstrates the potential to make expert financial advice more accessible, empowering users to make informed decisions with ease and efficiency.

##. Methods and Technical Implementation
####a. Data Collection
* **Sources:** Financial data is collected from two key sources—the Alpaca News API, which provides real-time financial news articles, and the Hugging Face finance-alpaca dataset, a question-answer dataset focused on finance. These sources supply diverse and current financial information essential for building a reliable, contextually aware financial advisory model.

* **Purpose:** By using up-to-date and comprehensive financial data, the model can better understand trends, terminology, and financial context, enhancing its ability to provide accurate, relevant advice.

#### b. Data Processing
* **Cleaning and Preprocessing:** Raw financial data undergoes thorough cleaning and preprocessing to prepare it for model training.
* **Text Normalization:** The data is standardized by removing special characters, converting text to lowercase, and handling punctuation for consistency.
* **Tokenization:** Text data is broken down into tokens to facilitate embedding and storage in the vector database.
Embedding and Storage in Qdrant: Processed data is transformed into vector embeddings and stored in Qdrant, a vector database optimized for fast and efficient retrieval. This enables quick access to relevant information during model inference, ensuring that data is organized and readily available when needed.

#### c. Modeling
* **Fine-Tuning with LoRA (Low-Rank Adaptation):**
**LoRA Overview:** LoRA is used to fine-tune the language model, adjusting a minimal set of parameters that allow it to specialize in financial contexts without requiring complete retraining.
![adapters](https://github.com/user-attachments/assets/a7c5600d-48b8-426f-be95-6d4aea2cb0fb)

**Training:** Through LoRA adaptation, the model learns to interpret financial data, allowing it to deliver accurate and context-sensitive financial advice.
![LoRA and QLoRA](https://github.com/user-attachments/assets/49bc20cc-eccd-481b-847f-8beea9ed4a6e)


* **Performance Tracking:** Model performance is ![LoRA and QLoRA]
continuously monitored using MLFlow, a machine learning experiment management tool that tracks metrics and validates fine-tuning accuracy.

#### d.  Model Deployment
* **RESTful API:** The fine-tuned model is deployed via a RESTful API, providing real-time accessibility for user interaction.
User Interaction with Gradio: The API integrates with Gradio, an interactive interface where users can input financial questions and view responses. Gradio converts user queries into model-friendly formats, manages response displays, and supports real-time engagement.
* **Technical Functionality:** This setup allows users to interact smoothly with the model, which is capable of delivering instant, customized financial advice based on user input and real-time data retrieval.
* **Inference Pipeline**
The inference pipeline is optimized for handling real-time data retrieval and efficient model inference. By integrating Qdrant with RAG, the system ensures that each response generated by the model is up-to-date and contextually accurate.
**Outcome:** This approach provides a fast, responsive, and user-friendly experience, allowing users to receive tailored financial advice on demand.

#### Functionality of the Financial Advisory Tool
* **Overall Workflow:** The tool’s workflow begins with data ingestion, followed by cleaning and embedding in Qdrant for storage. LoRA fine-tunes the model, enabling it to provide context-aware financial insights, while RAG dynamically retrieves relevant data during inference.
* **User Experience:** The deployed model, accessible via a RESTful API and Gradio interface, allows users to ask financial questions and receive accurate advice quickly. The real-time data retrieval architecture ensures that the model’s responses incorporate the latest information.
* **Adaptability and Reliability:** The integration of real-time data and advanced language modeling techniques makes the tool adaptable to individual user needs, offering a scalable solution for delivering reliable financial guidance.

