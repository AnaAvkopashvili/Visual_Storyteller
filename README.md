This project is a deep learning-based **Image Caption Generator** that automatically produces natural language descriptions for visual content. Built with TensorFlow and Keras, the model utilizes an encoder-decoder architecture, leveraging the **Xception** network to extract rich image features and a custom text-generation model to predict captions word-by-word. 

Whether you want to train a custom model on your own dataset or run inference on local files and web URLs, this repository provides a complete, easy-to-use pipeline from data preprocessing to final caption generation. 

**Note on Current Performance:** The model currently performs best on well-lit outdoor scenes, people, and dogs. Due to the limitations of the current training dataset, it may struggle with complex indoor environments, aerial shots, or food imagery. You can easily improve performance in these areas by expanding the training data and tweaking the provided hyperparameters.
