# Info

## DeepLabV3 Method - Chris Morris
Within the /dl/cm/ folder is my deep learning method for wheat segmentation using DeepLabV3 in PyTorch. The goal of this part was to train a semantic segmentation model that can predict a binary mask for each image, separating wheat pixels from background pixels.

My work started from the CIFAR-10 demo shown in the Week 7 lecture, which was used as a coding starting point for the training workflow. From there, the code was modified from an image classification setup into a binary semantic segmentation pipeline using DeepLabV3 with a ResNet-50 backbone. The method was then extended through fine-tuning, longer training, data augmentation, and checkpointing.

### Files
The /dl/cm/ folder contains the full progression of the DeepLabV3 method, from the initial baseline through to the final checkpointed version, and backup experiment results file.

| File / Folder                                    | Description                                                                                                                      |
| ------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| `method_pytorch_deeplabv3.ipynb`                 | Initial baseline DeepLabV3 notebook used as the starting version of the method.                                                  |
| `FINETUNING_method_pytorch_deeplabv3.ipynb`      | Fine-tuning version where pretrained DeepLabV3 was adapted to the wheat dataset.                                                 |
| `AUGMENTATION_method_pytorch_deeplabv3.ipynb`    | Version that adds data augmentation, including flips and rotations changes.                                |
| `BEST_CHECKPOINT_method_pytorch_deeplabv3.ipynb` | Final DeepLabV3 version with checkpointing, used to produce the best result.                                                     |
| `data/`                                          | Dataset folder containing the images and masks used by the notebooks. This should remain in the same directory as the notebooks and contatin the folders (with test data): test/ train/ validation/ |
| `training_results_history.xlsx`                  | Backup of the Excel file used to store the results from different experiment runs.                                                             |

* NOTE: The dataset will need to be added on your local machine in order to run this method

### Main libraries used
The following external libraries were used in this part of the project:
- PyTorch — main deep learning framework used for model training and testing
- Torchvision — used for the DeepLabV3 model, pretrained weights, transforms, and image utilities
- NumPy — used for array handling and numerical operations
- Pillow (PIL) — used for image loading and preprocessing
- Matplotlib — used for graphs and result visualisation
- pandas — used for saving and reviewing experiment results in Excel format
- openpyxl — used for writing Excel result files

### External code / resources used
The following code or ideas were adapted from external sources:
- Week 7 CIFAR-10 lecture demo — used as the starting point for the training code structure, then modified for binary segmentation
- Torchvision DeepLabV3 implementation — used as the base model architecture
- PyTorch / Torchvision documentation — used for guidance on transfer learning, transforms, saving/loading models, and model setup

The submitted code mainly contains my own implementation and modifications built around these tools and references.

### Running the Code
To run this code, place the dataset folder (renamed as data/) in the same directory as the notebook and make sure the Excel results file is stored in the home project directory (as this is expected by the code). After that, open the notebook and run it from top to bottom so that the dataset paths, model setup, training settings, and result-saving steps are all loaded in the correct order. This will allow the code to train or fine-tune the model, evaluate it, and then save the updated results back to the Excel file correctly.

## U-Net Method - Ganes Ngim
This side of the project attempts to conduct image segmentation on wheat using the U-Net CNN architecture. The model uses ResNet50 encoder pretrained on ImageNet, allowing it to benefit from learned low-level and mid-level visual features such as edges, textures, and shapes. There has been extensive testing and experimentation with various parameters to find the best outcome, and some of these changes and results can be seen in the excel file within the corresponding U-Net directory. The notebooks also checks and exits the training loop if there hasn't been a reduction in validation loss over a certain number of period. This ensures that the model is not over-fitted and produces the best results during testing.

The associated files for this implementation is in the /dl/gn directory.

### Files
| File / Folder                                    | Description                                                                                                                      |
| ------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| `unet_data_augmentation.ipynb`                   | Final notebook containing best parameter changes and data augmentation.                                                          |
| `unet_implementation.ipynb`                      | Base implemenation of U-Net, used as a reference point for future tuning and augmentation.                                       |
| `unet_parameter_tuning.ipynb`                    | The first parameter tuning after the base implementation. Only fine tuned basic parameters like the lr, number of epochs and image size. |
| `unet_parameter_tuning2.ipynb`                   | The second notebook containing notable parameter changes like different encoders and weights, loss function and optimizers.      |
| `training_results_history.xlsx`                  | Contains training result logs of parameter changes and data augmentation implemenation for comparison.                           |

### Main libraries used


### External code / resources used


### Running the Code
This implementation was done on Google colab while using their existing libraries. For the best training and result experience is it recommended that you run the notebook on the Google Colab workspace.

To run this notebook on Google Colab, upload your desired file to Google Drive, then right click on the uploaded file to open with Google Colab. This will open Google Colab's workspace environment where you can then run the notebook. It is recommonded that you use one of Google's available GPU's for a faster run time.

