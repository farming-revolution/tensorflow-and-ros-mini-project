![image](https://user-images.githubusercontent.com/72017322/231417840-be6e2fe7-35df-4ca1-b570-d634436ddadb.png)

# farming revolution tensorflow-and-ros-mini-project
Mini-project to evaluate capabilities in tensorflow and ROS for applicants at farming revolution GmbH


## Objective
The objective of this mini-project is to evaluate an applicant's  
* capacity to use `linux`
* basic understanding of `ROS` and `tensorflow`  
* basic programming skills in `python`
* capability to use `git`  
* ability to write proper documentation

## Preliminary tasks
* Install `ROS` and `tensorflow`.  
* Recommended: *Beginner Level* tutorials 1-7 and 12 of ROS: [link to ROS tutorials](http://wiki.ros.org/ROS/Tutorials).  
* Recommended: *Customization basics: tensors and operations* tutorial for tensorflow: [link to tutorial](https://www.tensorflow.org/tutorials/customization/basics). Depending on your background, starting with an additional [beginners tutorial](https://www.tensorflow.org/tutorials) might help as well.

## Play the bag file
The provided bag file contains images of plants published on the `/img_bgri` topic (4-channel image, blue, green, red, near-infrared).

```
rosbag play mini-project.bag -l
rosrun image_view image_view image:=/img_bgri  # Visualize the image
```
![image](https://user-images.githubusercontent.com/72017322/231418378-163ab21d-d1fe-429d-88e1-3ca5ffd94d19.png)



## Task

Write a python `ROS` node, that uses `tensorflow` to extract a basic plant mask.

Your node has to  
* subscribe to `/img_bgri`  
* publish to `/plant_mask` a mask (single-channel) showing the plant pixels

Do **not** write something too complex: the goal is prove that you can write a simple ROS node with minimal functionality.
An easy way to detect the plant pixels is to subtract the red from the near-infrared value and apply a threshold. 

You **have** to use tensorflow to do that (even if it would be easier with an OpenCV or numpy function).

Morphological operations can be used if you want but it is not required.


## Upload on github.com

Use a repository management service supporting `git` (preferrably [github.com](https://www.github.com)) to:  
* Create a **private** repository  
* Push your code   
* Add a `README.md` file describing how to install the required dependencies, what your node does an how to use it 
* Send us a link to the repository and give us permissions to read your code.
