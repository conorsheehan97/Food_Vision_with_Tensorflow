
# Food Vision – Image Classification (Google Colab)

This project trains a food image classifier in Google Colab using a Tesla T4 GPU 
(compute capability 7.5). Because of this GPU, mixed precision training could be used, 
which helps speed up training and use less memory.

## What this notebook does (step-by-step)

1. **Load and prepare images**  
   Images are loaded from folders and resized so the model can work with them.

2. **Create the model**  
   A pre-trained model is used so the notebook does not start learning from scratch.  
   This usually helps the model learn faster and reach better accuracy.

3. **Train the model (first pass)**  
   The model is trained with the top layers unfrozen first.  
   This lets the new layers learn basic patterns.

4. **Fine‑tune the model**  
   More layers are unfrozen so the model can learn more detailed food features.  
   A lower learning rate is used so nothing breaks.

5. **Learning-rate finder + ReduceLROnPlateau**  
   These help find a better learning rate and adjust it when progress slows.

6. **Extra generalisation steps**  
   More data augmentation and class weights were added because the model was only 
   reaching ~15% accuracy.  
   These steps help the model avoid overfitting and handle uneven class counts.

7. **Evaluation**  
   Classification report, confusion matrix and example predictions are shown.  
   This gives a good picture of how well the model works.

## Why this order?

- Starting light and then fine‑tuning avoids damaging the pre‑trained weights.  
- LR finder + LR scheduler help keep the training stable.  
- Augmentation and class weights help the model generalise better.  
- Evaluation at the end checks whether the model improved.

## How to run

This was created for **Google Colab**.  
Just upload the notebook, connect to a GPU runtime, and run the cells top‑to‑bottom.
