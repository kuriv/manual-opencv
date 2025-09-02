# ROI

从原图像矩阵中截取部分内容，就是将需要截取的部分在原图像矩阵中的位置标记出来。

```cpp
#include <opencv2/opencv.hpp>
#include <iostream>

using namespace cv;
using namespace std;

int main(int argc, char const *argv[])
{
    Mat img;
    Rect rect(200, 200, 300, 200);
    Mat roi1, roi2;
    img = imread("demo.jpg");
    if (img.empty())
    {
        cout << "Could not load image." << endl;
        return -1;
    }
    imshow("IMG", img);
    roi1 = img(rect);
    imshow("ROI1", roi1);
    roi2 = img(Range(100, 500), Range(100, 500));
    imshow("ROI2", roi2);
    waitKey(0);
    destroyAllWindows();
    return 0;
}
```

