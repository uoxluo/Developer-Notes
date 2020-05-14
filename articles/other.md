# Other Notes

* 
```python
mat = np.loadtxt(filename, dtype=float, delimiter=',')
np.savetxt("data.csv", A, delimiter=',')
```

* 
```
g++ -ggdb test-opencv.cpp `pkg-config --cflags --libs opencv`
```

* 
```C++
cv_mat.at<cv::Vec<float, 3>>(row, col);

cv::Rect ROI(col, row, width, height);
cv::Mat ROI_img = image(ROI);
```

* disk devices info
```bash
sudo fdisk -l
```

* Installation and use of LabelMe
```bash
sudo apt install python3-pyqt5
pip3 install labelme
labelme image.jpg --nodata
```

* 
> stdbuf -o 0 [command] | tee log.txt

> stdbuf -o 0 [command] >  >(tee -a log.txt) 2>  >(tee -a log.txt >& 2)

* 
```C++
std::string::size_type idx;
idx = s.find("substring");
if (idx == std::string::npos) { ... }
```

* GTest
```bash
sudo apt install libgtest-dev
cd /usr/src/googletest/googletest
sudo mkdir build
cd build
sudo cmake ..
sudo make
sudo cp libgtest* /usr/lib/
```
> ./UnitTests --gtest_filter=ImageUtilTest.*

* Install shared library
> ldconfig [path]

* ffmpeg -framerate 5 -pattern_type glob -i "obstacle*.png" -vcodec mpeg4 output.mp4

* Python pkgs
> sudo apt install python3-all-dev

> sudo apt install python3-pip

> pip3 install numpy

> pip3 install scipy

> pip3 install matplotlib

> pip3 install scikit-learn

> pip3 install scikit-image

> pip3 install virtualenv virtualenvwrapper

> pip3 install jupyter

> pip3 install testresources

> To fix pip: sudo python3 -m pip uninstall pip

* Install TensorFlow
> python3 -m pip install -U pip

> python3 -m pip install -U tensorflow

* OpenCV mat to and from csv files
```C++
std::ofstream outfile("a.csv")
outfile << cv::format(mat, cv::Formatter::FMT_CSV);
outfile.close();
```
```C++
cv::Ptr<cv::ml::TrainData> raw_data = cv::ml::TrainData::loadFromCSV("a.csv", 0, -2, 0);
cv::Mat mat = raw_data->getSamples();
```

* C++ random number
```C++
#include <random>
std::default_random_engine RandomEngine;
std::uniform_int_distribution<int> UniformIntDistribution(0,10);
int random_number = UniformIntDistribution(RandomEngine);
```

[Back to Contents](../README.md)