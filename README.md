# Laptop price Prediction

### Table of Content ###

⦿ [Overview](https://github.com/PassionateDataScientist/Laptop_price_capstone2#overview)

⦿ [Data](https://github.com/PassionateDataScientist/Laptop_price_capstone2#data)

⦿ [Aim](https://github.com/PassionateDataScientist/Laptop_price_capstone2#aim)

⦿ [Technologies Used](https://github.com/PassionateDataScientist/Laptop_price_capstone2#technologies-used)

⦿ [Data Wrangling](https://github.com/PassionateDataScientist/Laptop_price_capstone2#data-wrangling)

⦿ [Exploratory Data Analysis](https://github.com/PassionateDataScientist/Laptop_price_capstone2#exploratory-data-analysis)

⦿ [Algorithms and Machine Learning](https://github.com/PassionateDataScientist/Laptop_price_capstone2#algorithms-and-machine-learning)

⦿ [Prediction](https://github.com/PassionateDataScientist/Laptop_price_capstone2#prediction)

⦿ [Future Scope](https://github.com/PassionateDataScientist/Laptop_price_capstone2#future-scope)

⦿ [Motivation](https://github.com/PassionateDataScientist/Laptop_price_capstone2#motivation)

⦿ [Bug/Feature Request](https://github.com/PassionateDataScientist/Laptop_price_capstone2#bug-feature-request)

⦿ [Acknowledgement](https://github.com/PassionateDataScientist/Laptop_price_capstone2#acknowledgement)

⦿ [Glossary](https://github.com/PassionateDataScientist/Laptop_price_capstone2#glossary)

### Overview ###
In 2021, approximately 340 million PCs were shipped around the world. The PC market saw its highest growth in 10 years. A Laptop’s lifespan is three to five years. Buying a laptop is an exercise in confusion. Even if you know what everything means, and know exactly what you want, finding it can be difficult, just navigating the manufacturers' websites to try buying the model you want is totally frustrating. This project will help you to find out major components you should consider when you browse for your next PC.

Before beginning to look at laptops, one must figure out various aspects like which operating system (OS), CPU, GPU, RAM, SSD, etc… works best. Once you have decided on your specification, you would like to know what the price of your desired laptops will be. This project helps you to consider your specifications and predict the price!

### Data ###
[Kaggle Dataset](https://www.kaggle.com/datasets/ionaskel/laptop-prices?select=laptops.csv)

The Dataset contains the data for 1300+ laptops and 12 features.

_ Features _
Company Name
Product Name
Laptop Type
Screen Inches
Screen Resolution
CPU Model
RAM Characteristics
Memory
GPU Characteristics
Operating System
Laptop's Weight
Laptop's Price

### Aim ###
This project aims to predict the price of a laptop by taking various factors like Name of the Company, Type of the Product, RAM, Memory, CPU, GPU, etc.

### Technologies Used ###
‣ Numpy

‣ Pandas

‣ Matplotlib

‣ Seaborn

‣ Scikit-learn

### Data Wrangling ###
Data Wrangling Notebook [Click Here](https://github.com/PassionateDataScientist/Laptop_price_capstone2/blob/main/Data_Wrangling.ipynb)

➠ **Feature Name: Memory**

**Problem:** ‘Memory’ contains Storage Type and Total Storage Capacity. Some Laptops have Mixture of storage type. And Storage Capacity is in different units GB and TB(1000 GB = 1TB).

**Solution:** First, I replaced GB with empty string and TB with ‘000’ to make same unit. I split the combination of the storage data and saved them making two columns ‘para1’ and ‘para2’.‘para1’ and ‘para2’ contains storage capacity and storage type. Still each columns have 2 piece of information. Firstly, I fetched the Storage type by using Lambda and saved them creating eight new columns. Then, Removed Storage Type in ‘para1’ and ‘para2’, and multiply them to those eight columns to get storage capacity. Now, we have Storage Type as a feature name and storage capacity as their respective value.

----pic---

➠ **Feature Name: ScreenResolution**

**Problem:** Feature Name ‘ScreenResolution’ contains useful information like whether the laptop is touchscreen or not, whether it has IPS or not, and resolution of the screen. Our Machine cannot interpret that complex information.

**Solution:** By using individual lambda functions for each piece of information, we fetch the information and save it in different columns. Further, by using the split function, we split x resolution and y resolution and find out PPI (Pixel Per Inches).

➠ **Feature Name: ScreenResolution**

Problem: ‘Cpu’, ‘Gpu’ and ‘OpSys’ also contain more than 1 piece of information.

**Solution:** Again, using Lambda function we fetch information from 'Cpu' and save ‘Cpu_ processor’ and ‘Processor_speed_GHz’. For 'Gpu', the best graphics cards are MSI, AMD, and Nvidia. Defining a function, I considered these cards as good and others as average. Again, creating a function, I fetched operating systems.

➠ **Feature Name:** RAM and Weight

Problem: ‘RAM' and 'Weight' contain unit (string) with numbers For Example, RAM datatype is object because values are 8GB/4GB, and Weight is in 'kg' unit.

**Solution:** Replaced the unit with empty string, and then convert object datatype to int/float.

➠ **Feature Name: Weight** and **Price**

**Problem:** ‘Weight' and 'Price' is in 'kg' and 'euro' unit.

**Solution:** Converted weight into lb. by multiplying 2.205 (1 kg ≈ 2.205) and converted euro price into Dollar by multiplying 1.14 (1 Euro ≈ 1.14 United States Dollar).

### Exploratory Data Analysis ###
Exploratory Data Analysis [Click Here](https://github.com/PassionateDataScientist/Laptop_price_capstone2/blob/main/Exploratory_Data_Analysis.ipynb)

Our target variable is ‘Price’ and the ‘Price’ data is skewed to right. That’s self-explanatory; many laptops in the market have lower prices and few have high prices. Real life distributions are usually skewed. In skewed data, the tail region may act as an outlier for the statistical model, and outliers adversely affect the model ’s performance, especially regression-based models. So there is a necessity to transform the skewed data to close enough to a Gaussian distribution or Normal distribution. A log transformation can help to fit a skewed distribution into a Gaussian one.

--- pic---

### Algorithms and Machine Learning ###
PreProcessing and Modeling [Click Here](https://github.com/PassionateDataScientist/Laptop_price_capstone2/blob/main/PreProcessing_and_Training_Data_Development.ipynb)

### Prediction ###
Some factors that have the largest effect (Correlation) on price of laptops. By taking various features like Storage size, Storage Capacity, processor speed (GHz), Company Name, etc.; you can predict price of your desired laptop!

### Future Scope ###
• Use different Techniques of Encoding Data

• Hyper-parameter tunning can improve the performance.

### Motivation ###
Laptop Price Prediction is an important problem. With a successful model for Laptop Price Prediction, we can choose better option! The motivated idea is that, if we know all information about today's laptop’s features, the price is predictable. In 2021, 340 million laptops are forecast to be shipped; this project is for all those 340 million lives!

### Bug/ Feature Request ###
If you find a bug (undesired results), kindly open an issue by including your search query and the expected result Click Here

### Acknowledgement ###
I would like to Thank You Travis Oliphant for maintaining NumPy library. Wes McKinney for maintaining Pandas library. John D. Hunter for inventing Matplotlib and Michael Droettboom for maintaining Matplotlib. Michael Waskom for creating Seaborn. David Cournapeau for inventing Scikit-learn. Daniel Wu for guiding me in this project.

### Glossary ###
**Screen Size:** Size of the screen, measured diagonally from corner to corner.

**Screen Resolution:** Screens come in a range of resolutions (measured in pixels, horizontal x vertical). The higher the resolution, the greater the picture quality.

**Touch Screen:** Touch-screen devices make navigating more intuitive. Using a touch-screen display, you can do things such as tap to select, hold and drag to move items, swipe to scroll, and pinch to zoom.

**Processor Model:** Your computer's processor is like its brain. Working in combination with system memory, the power of the processor determines the complexity of software you can run, how many programs you can have open at the same time, and how fast those programs will run. Most computers feature an Intel or AMD processor.

**Processor Speed (up to):** Actual central processing unit (CPU) speed may vary by device configuration and design. Also referred to as clock speed, this is how quickly the central processing unit (CPU) can receive and interpret instructions. The higher the number, the more operations per second that can be completed. Working in combination with system memory, the power of the processor determines the complexity of software you can run.

**Solid State Drive Capacity:** The amount of data that can be stored on the device's solid state drive (SSD). SSD is a flash-based storage with faster speeds than a hard disk drive (HDD).

**System Memory (RAM):** Random-access memory (RAM) is a computing device's short-term data storage, which allows active information to be accessed quickly. The size and type of RAM determines how efficiently the device can handle large amounts of information at one time. For example, gaming or video editing requires more RAM for optimal performance.

**System Memory RAM Speed:** How fast the information-storing hardware operates. The faster the RAM, the faster memory can be transferred to other system components. Ultimately, faster RAM improves operational efficiency.

**Graphics Type:** Discrete graphics uses a separate graphics card for processing video images. Because it does not use memory from the system's RAM, there is no extra burden on the CPU and graphics are processed more efficiently. Integrated graphics shares system RAM to process video images.

**Graphics:** Often referred to as a "graphics processing unit" (GPU), this device is responsible for displaying image content and decoding/encoding video content in programs and games.

**Operating System:** The operating system manages all software and hardware, including files, memory and connected devices. Most importantly, it lets you interact with your device and your programs in a visual way; otherwise, you'd be typing computer code to get anything done.

**2-in-1:** A laptop and a tablet combined in one lightweight, portable device. Sometimes referred to as "convertible" or "hybrid" laptops, these devices deliver the processing power and keyboard of a laptop. When you're ready to play, either detach the screen or fold your 2-in-1 into tablet mode to comfortably watch movies, play games, read an e-book and more.

