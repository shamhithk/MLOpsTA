# ![Google Cloud](https://avatars.githubusercontent.com/u/2810941?s=60&v=4) Google Cloud Vertex AI
## Overview:
Vertex AI is a machine learning (ML) platform that lets you train and deploy ML models and AI applications, and customize large language models (LLMs) for use in your AI-powered applications. Vertex AI combines data engineering, data science, and ML engineering workflows, enabling your teams to collaborate using a common toolset and scale your applications using the benefits of Google Cloud. For folks using different cloud services, it is similar to AWS SageMaker, Azure ML Studio, etc.
Please refer to the official documentation for more detailed concepts and working of the services 

## How to setup Vertex AI in GCP console
After creating your project in GCP, search for /Vertex AI in search bar, and then you'll be landed in the homepage where you have to enable all recommended APIs to start using Vertex AI services as shown in the image below.
![Screenshot 2024-09-20 at 12 55 14 PM](https://github.com/user-attachments/assets/c604c64e-fe4a-4dd1-8b6d-e520757fb5eb)



Further, a brief introduction to all the services in Vertex AI is provided section-wise.

## Tools:
### Model Garden: 
Model Garden in Vertex AI is a feature within Google Cloud's Vertex AI platform that offers a curated collection of pre-trained and fine-tunable machine learning and language models. These models are designed to help developers and data scientists accelerate their AI/ML projects by providing ready-to-use models for various tasks, such as natural language processing (NLP), computer vision, and more. You can filter these models by modalities( artifact format), providers and the features models support. Keep in mind while testing LLM’s might not be expensive, deploying few closed models is a lot more expensive usually few thousand dollars per month. Always be sure to check the price before deploying LLM.

![Screenshot 2024-09-20 at 12 53 58 PM](https://github.com/user-attachments/assets/681b725b-1491-4e61-bbfc-e999e6a02dc8)



## Pipelines: 
Vertex AI Pipelines lets you automate, monitor, and govern your machine learning (ML) systems in a serverless manner by using ML pipelines to orchestrate your ML workflows. You can batch-run ML pipelines defined using the Kubeflow Pipelines or the TensorFlow Extended (TFX) framework. To learn how to choose a framework for defining your ML pipeline, see Interfaces to define a pipeline.

You can build pipelines in Kubeflow and migrate the files to Vertex AI pipelines. The key difference between the 2 is how they handle storage. Kubeflow uses Kubernetes resources whereas Vertex AI uses cloud storage.

You can create custom pipelines, use default templates from the template gallery, or upload YAML / XML pipeline files. To run the pipeline you have to give a place to store the outputs of the particular pipeline, usually cloud storage in GCP for this case.


![Screenshot 2024-09-20 at 1 03 51 PM](https://github.com/user-attachments/assets/5dad7b86-f1af-466a-9f89-1db2aefdf817)





Below is an example of the pipeline “LLM -text generation evaluation pipeline from the template gallery”. You can store individual components of a pipeline to use later for other projects too.

![Screenshot 2024-09-20 at 8 19 38 PM](https://github.com/user-attachments/assets/3289aabc-27ce-486e-b3f6-a38d3f8b10ef)




## Notebooks:
### Colab Enterprise:
As the name says Colab enterprise is the enterprise -grade version of Google Colab, a cloud based Jupyter notebook environment. It is designed to meet the needs of business by providing enhanced security, collaboration features and integration with enterprise tools and data sources. Frameworks and compute resource of our choice can be selected depending on the use-case
<img width="1502" alt="Screenshot 2024-09-21 at 3 21 03 PM" src="https://github.com/user-attachments/assets/44371d12-4ef3-4964-9119-0e90a602f9b3">
### Workbench: 
Vertex AI Workbench is part of Google Cloud's Vertex AI platform, which provides tools and services for building, deploying, and managing ML models at scale. Workbench serves as an integrated environment where you can:
- Develop and experiment with ML models using JupyterLab.
- Access and process large datasets stored in Google Cloud services.
- Collaborate with team members in real-time.
- Seamlessly transition from prototyping to production.


## Vertex AI Studio:
Use Vertex AI Studio to design, test, and customize your prompts sent to Google's Gemini and PaLM 2 large language models (LLM). You can view the Gemini API in Vertex AI and Vertex AI API code used to generate the responses.
From Vertex AI Studio, you can complete the following:
Test models using provided prompt samples
Design and manage your prompts
Compare prompt output by model
Evaluate your prompts against select quality metrics
Tune models to get tailored responses
Ground model output to Vertex AI Search or Google Search
Get the Vertex AI API code to implement your work
 
<img width="1491" alt="Screenshot 2024-09-21 at 3 22 01 PM" src="https://github.com/user-attachments/assets/7da92546-9891-4b2f-bd19-86d930bc167e">
Unfortunately, you can’t access all features on your free google account. Tuning and Advanced parameter features are available if you upgrade your free-trial account to standard billing account.

Vertex AI studio prompt categories:
From the Vertex AI Studio you can test and customize prompts for different generative AI models.
- Freeform: Test text and multimodal prompts using a variety of models. To learn about the models, see Gemini models.
- Chat: Try out multi-turn prompts using a variety of language models. To learn about the models, see Gemini models.
- Translation: Perform translation.
- Vision: Test image model generation using Imagen on Vertex AI.
- Speech: Perform text-to-speech and speech-to-text conversions. This is done using the Chirp model. To learn more about Chirp, see Chirp: Universal speech model.




Tuning (fine-tuning): This is one of the ways to enhance LLM responses, usually works best when you have large labelled data. Resource-extensive method, considered after prompt engineering and RAG. Approaches like Parameter-efficient-finetuning and Full-finetuning are available in tuning features. Vertex AI Agent Builder is something to look into if you’re building LLM applications.

## Data
### Feature Store
Vertex AI Feature Store is a managed, cloud-native feature store service that's integral to Vertex AI. It streamlines your ML feature management and online serving processes by letting you manage your feature data in a BigQuery table or view. You can then serve features online directly from the BigQuery data source.

The workflow to set up and start online serving using Vertex AI Feature Store can be summarized as follows:

- Prepare your data source in BigQuery.

- Optional: Register your data sources by creating feature groups and features.

- Set up online store and feature view resources to connect the feature data sources with online serving clusters.

- Serve the latest feature values online from a feature view.

### Datasets
You can use a managed dataset to provide the source data used to train AutoML and custom models on Vertex AI. A managed dataset is required for AutoML and is optional for custom training.
You can create managed datasets for training AutoML models by using the Google Cloud console or the Vertex AI API. The instructions for how to do this slightly vary based on your data type and model objective. Start by preparing your training data.
<img width="1506" alt="Screenshot 2024-09-21 at 3 30 18 PM" src="https://github.com/user-attachments/assets/81894bb8-dc8f-4935-9701-216510329f00">

Data split
<img width="876" alt="Screenshot 2024-09-21 at 3 31 21 PM" src="https://github.com/user-attachments/assets/425b7151-e849-46a4-98eb-020d987d09ec">



