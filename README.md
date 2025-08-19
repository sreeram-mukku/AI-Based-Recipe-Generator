# AI-Based Recipe Generator from Food Images

This project uses a deep learning model to identify a food dish from an image and generate a corresponding recipe, complete with ingredients and instructions.

![GIF of the project in action] ---

## Features
- **Image Classification**: Utilizes a ResNet50 model, fine-tuned on the Food-11 dataset, to achieve high accuracy.
- **Recipe Generation**: Connects to the Spoonacular API to fetch detailed recipes for the predicted dish.
- **Multi-language Support**: Can translate the generated recipe into various languages upon user request.

---

## How It Works
The project follows a two-stage transfer learning process:
1.  **Feature Extraction**: The top layers of a pre-trained ResNet50 model are trained on the Food-11 dataset.
2.  **Fine-Tuning**: The final 20 layers of the ResNet50 base are "unfrozen" and trained with a very low learning rate to adapt the model for higher specificity on food images.

The final trained model is then used to predict the class of a user-uploaded image. This class name is used to query the Spoonacular API for a relevant recipe.

---

## Technology Stack
- **Backend**: Python
- **Deep Learning**: TensorFlow, Keras
- **Libraries**: NumPy, Matplotlib, Pillow
- **APIs**: Spoonacular (for recipes), Google Translate
- **Environment**: Google Colab with T4 GPU

---

## Setup and Usage
1.  Clone this repository.
2.  Upload the `.ipynb` notebook and the `.h5` model file to your environment (e.g., Google Colab and Google Drive).
3.  Install the required dependencies:
    ```
    pip install -r requirements.txt
    ```
4.  Update the Spoonacular API key in the final code cell.
5.  Run the final cell and upload an image to get a recipe!