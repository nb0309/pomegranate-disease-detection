# pomegranate-disease-detection
an additional layer is added to the resnet model for classification purpose, so in order to use the trained model, use the below given steps:
# Load the saved model and its weights
loaded_model = torchvision.models.resnet18(pretrained=False)
loaded_model.fc = nn.Linear(num_features, num_classes)  # Re-create the custom linear layer
loaded_model.load_state_dict(torch.load(model_path))
loaded_model.to(device)  # Move the model to the desired device (CPU or GPU)