# MLflow-Research
## Introduction 

MLFlow is a platform to manage machine learning model lifecycle, including experimentation, training, and deployment. It is highly customizable 
to developers and engineers who are proficient in defining the metrics needed for observibility. MLFlow is a platform where models are registered,
experiment or model trainings are tracked and versioned. MLflow also offers simple user interface to visualize the metrics. 

MLFlow has a MLFlow tracking server. The purpose of this server is to curate and safeguard the backend of MLFlow. Every time an application
executes the MLflow library, whether it's training or inference, metrics defined in the application will be logged to the server. If there are artifacts
such as model files, these artifacts are also logged and stored at the server.

## MLflow client set up
In the application code, one may configure MLflow to point to the tracking server and then log metrics to it:

```python
mlflow.set_tracking_uri("http://your-server-ip:5000")  # Replace with your server IP
mlflow.set_experiment("openai_text_generation_monitoring")

```

## View metrics in the MLFlow UI
Once the server is up and running, open the MLflow UI at http://your-server-ip:5000. In the UI, you can:

1. Select the Experiment: Choose your experiment, like "openai_text_generation_monitoring."
2. View Runs and Metrics: Each API call will log a new run, where you can view and compare BLEU, ROUGE, and perplexity metrics over time.
3. Create Line Graphs: MLflow allows you to visualize these metrics as line graphs. You can:
    * Select metrics defined and calculated in the application code.
    * View trends over runs to understand how performance varies over time.
    * Adjust the x-axis to run index, time, or another metric.


Overall, as long as the metrics may be quantified programmitically, these metrics may be tracked and displayed by the MLFlow UI. 