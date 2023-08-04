# Proyecto Final MLII
#### Description:
This software combines Pywinauto and Pytesseract:
  - Pywinauto automates the Microsoft Windows GUI. allows to send mouse and keyboard actions to windows dialogs and controls
  - Pytesseract to give the feedback, allows to recognize and read the text embedded in images.

Having action and assertion, wrote in python tool, become in a simple automation tool.

#### Prerequisites
python --version        # Python 3.11.4

python -m venv envmlii      # Crear environment
Set-ExecutionPolicy Unrestricted -Scope Process
.\envmlii\Scripts\activate    # Activar (envmlii)


- pip install pandas
- pip install opencv-python
- pip install matplotlib  
- pip install nbformat
- pip install scikit-image
- pip install seaborn
- pip install tensorflow
- pip install -U scikit-learn
- pip install plotly
- pip install ipython
- pip install keras_preprocessing    
- pip install ipykernel

pip install -r .\requirements.txt # Ejecuta todos los package
pip install -U scikit-learn   # Successfully installed joblib-1.3.1 scikit-learn-1.3.0 threadpoolctl-3.2.0
deactivate
.\envmlii\Scripts\activate
ipython kernel install --user --name=envmlii # Kernel del proyecto: Installed kernelspec envmlii in C:\Users\nicom\AppData\Roaming\jupyter\kernels\envmlii 