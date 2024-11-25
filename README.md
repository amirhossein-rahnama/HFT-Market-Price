# HFT-Market-Price






# StockPredictionRNN  

[![GitHub license](https://img.shields.io/github/license/mashape/apistatus.svg)](https://raw.githubusercontent.com/dzitkowskik/StockPredictionRNN/master/LICENSE)  

High-Frequency Trading Price Prediction Using LSTM Recurrent Neural Networks  

---

### **Overview**  

This project focuses on utilizing **Recurrent Neural Networks (RNNs)** with **Long Short-Term Memory (LSTM)** units to predict stock prices in high-frequency trading scenarios. By leveraging historical NYSE OpenBook data, the program reconstructs limit order books at specific points in time to train and test predictive models. 

This project was created as part of the **Computational Intelligence in Business Applications** course at the Warsaw University of Technology, Department of Mathematics and Computer Science.

---

### **Data Requirements**  

The program requires the dataset `openbookultraAA_N20130403_1_of_1` from the NYSE OpenBook history. This dataset can be downloaded using FTP from the following link:  
**[Download Data from NYSE](ftp://ftp.nyxdata.com/Historical%20Data%20Samples/TAQ%20NYSE%20OpenBook/)**  (ftp://ftp.nyxdata.com/Historical%20Data%20Samples/TAQ%20NYSE%20OpenBook/)

#### **Steps for Data Preparation**  
1. Download the dataset.  
2. Unzip the file.  
3. Move the unzipped file to the `src/nyse-rnn` directory of the project.

---

### **Installation and Usage**  

This project is implemented in Python 2.7 and utilizes the **Keras** library for building and training the neural network models. Follow the steps below for installation and execution.

#### **Dependencies**  

The program requires the following software and libraries:  
- **Theano**: Backend for Keras.  
- **Keras**: Neural network library.  
- **NumPy, SciPy, Matplotlib**: Libraries for numerical computations and data visualization.  
- **PyMongo**: For MongoDB database integration.  
- **Optional**: OpenBLAS and cuDNN for optimized performance.

#### **Installation Commands**  

1. Install Theano and Keras:  
   ```bash
   sudo pip install git+git://github.com/Theano/Theano.git
   sudo pip install keras
   ```

2. Install additional libraries:  
   ```bash
   sudo pip install numpy scipy matplotlib pymongo
   ```

---

#### **Running the Program**  

1. Navigate to the project directory:  
   ```bash
   cd StockPredictionRNN
   cd src/nyse-rnn
   ```

2. Create a directory for storing symbols:  
   ```bash
   mkdir symbols
   ```

3. Execute the following scripts in order:  
   ```bash
   python nyse.py
   python main.py
   ```

---

### **Saving Data with MongoDB**  

If you wish to save processed data to MongoDB, ensure it is installed on your system. Refer to the [MongoDB installation guide](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/) for detailed instructions.

---

### **Optimizing Performance**  

For better performance, especially on GPUs, create a file `~/.theanorc` with the following content:  

```ini
[global]
floatX = float32
device = gpu1

[blas]
ldflags = -L/usr/local/lib -lopenblas

[nvcc]
fastmath = True
```

---

### **Customization Options**  

Review the source code for additional features and functionalities. Certain options may require uncommenting specific lines in the code to enable them. Customizations allow tailoring the program to specific requirements.

---

### **Key Features**  

- Leverages LSTM-based RNNs to model sequential data for stock price prediction.  
- Reconstructs limit order books using NYSE OpenBook historical data.  
- Offers integration with MongoDB for efficient data management.  
- Supports GPU acceleration through CUDA and OpenBLAS for faster computations.  

This project provides a foundational framework for applying deep learning techniques to high-frequency trading. It serves as a starting point for further research and development in predictive modeling for financial markets.  
