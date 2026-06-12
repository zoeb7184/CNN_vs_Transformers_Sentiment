Sentiment Analysis on SST-2 with Classical and Transformer Models
By: Zoeb Ali Khan, 4439666

=========================================================
1. PROJECT DIRECTORY STRUCTURE
=========================================================

Project/
│
├─ README.txt
├─ requirements.txt
│
├─ Report.pdf
│
└─ Code/
   ├─ 1_CNN_Baseline.ipynb
   ├─ 2_BERT_Off_The_Shelf.ipynb
   └─ 3_BERT_Fine_Tuned.ipynb


=========================================================
2. ENVIRONMENT SETUP
=========================================================

To ensure the code runs correctly, please follow these steps to set up the Python environment.
(Python version >= 3.9 is recommended).

- Create a new virtual environment in a folder of your choice:
  "python -m venv your_env_name"

- Navigate to your environment's "Scripts" folder and activate it. On Windows, use the command:
  "activate"

- Once your environment is active, install all the required libraries from the requirements file using the command:
  "pip install -r requirements.txt"

- After the installation is complete, you can run the Jupyter notebooks. To start JupyterLab, type the following command in your active terminal:
  "jupyter-lab"

- You can now navigate to and run the .ipynb files from the "Code" folder.

=========================================================
3. CODE EXECUTION
=========================================================

IMPORTANT NOTE: To avoid slow performance or potential errors, please ensure a GPU is enabled in your runtime environment. In Google Colab, you can do this by navigating to "Runtime" > "Change runtime type" and selecting "GPU" as the hardware accelerator.

NOTE: All code has been written to ensure reproducibility where possible. A seed of SEED = 42 has been used in all notebooks. Please run the code blocks in sequence without skipping cells.

NOTE: All saved model checkpoints and outputs have been deleted to keep the project file size small. Re-running the scripts will generate them.

1. Classic Model (CNN Baseline)

- For model training, open and run the file "1_CNN_Baseline.ipynb".
- The training is relatively fast but may take a few minutes.
- After training is complete, the final validation accuracy will be printed.
- The script will save the trained Keras model in the same directory.

2. Off-the-Shelf Transformer (BERT)

- For the model evaluation, open and run the file "2_BERT_Off_The_Shelf.ipynb".
- This notebook does NOT involve training and will only evaluate the pre-trained model.
- Once the evaluation is completed, the accuracy and F1 scores will be printed.

3. Fine-Tuned Transformer (BERT)

- For model training, open and run the file "3_BERT_Fine_Tuned.ipynb".
- The training should take approximately 1 hour, depending on the GPU.
- After training is complete, the final validation scores will be printed.
- The best model checkpoint will be saved to the "bert-sst2-fine-tuned" directory.

IMPORTANT NOTES ON FINE-TUNING (ADDRESSING MEMORY CONSTRAINTS):

  - The fine-tuning script is configured to work on a modern GPU (approx. 6-8GB VRAM) by using mixed-precision training (FP16).
  - Please ensure your GPU is compatible with FP16. Most GPUs from the last 5-6 years are compatible.
  - If your GPU is older or not compatible, you may encounter an error. To fix this, make the following change in the "Training arguments" cell:
    'fp16 = False,'  # Change from True to False
  - Disabling FP16 will increase memory usage significantly. If you run out of memory, you can try reducing the `per_device_train_batch_size` in the `TrainingArguments` from 4 to 2 or 1.
  - Please be aware that changing these settings (disabling FP16 or reducing the batch size) may slightly alter the final accuracy and training time. However, the results should remain within a small margin of error.

=========================================================
4. EXPECTED RESULTS
=========================================================

- The results from running the notebooks should closely match the results stated in the "Report.pdf".
- Utmost care has been taken to ensure the reproducibility of the results by setting a fixed seed.
- Any minor deviations, especially for the CNN model, may be due to the non-deterministic nature of neural network weight initialization.
- If you run into any errors not mentioned here or are unsure about any procedure, please feel free to reach out via the email mentioned in the report.

Thank you!
```