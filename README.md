# MLflow-Research
Focus of discussion

MLFlow is a platform to manage machine learning model lifecycle, including experimentation, training, and deployment. It is highly customizable 
to developers and engineers who are proficient in defining the metrics needed for observibility. MLFlow is a platform where models are registered,
experiment or model trainings are tracked and versioned. MLflow also offers simple user interface to visualize the metrics. 

MLFlow also offers a MLFlow tracking server. The purpose of this server is to curate and safeguard the backend of MLFlow. Every time an application
executes the MLflow library, whether it's training or inference, metrics defined in the application will be logged to the server. If there are artifacts
such as model files, these artifacts are also logged and stored at the server.

In the application code, one may configure MLflow to point to the tracking server and then log metrics to it:

```python
mlflow.set_tracking_uri("http://your-server-ip:5000")  # Replace with your server IP
mlflow.set_experiment("openai_text_generation_monitoring")

```