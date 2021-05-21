# BrilliantClassifier

In root directory 

# Settings
IMAGE_SIZE=224
ARCHITECTURE="mobilenet_0.50_${IMAGE_SIZE}"

# Train 

python -m scripts.retrain \
--bottleneck_dir=Model_Files/bottlenecks \
--how_many_training_steps=500 \
--model_dir=models/ \
--summaries_dir=Model_Files/training_summaries/"${ARCHITECTURE}" \
--output_graph=Model_Files/retrained_graph.pb \
--output_labels=Model_Files/retrained_labels.txt \
--architecture="${ARCHITECTURE}" \
--image_dir=Dog_murphy/

# Prediction 

python -m scripts.label_classification \
--graph=retrained_graph.pb  \
--image=aki_2dg7OC16199004948500_dog_0.jpg
