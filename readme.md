# My copy space
```
curl --upload-file ./td3_ros_reacher_doc13_oct23_models.zip https://transfer.sh/td3_ros_reacher_doc13_oct23_models.zip

zip -r td3_ros_reacher_doc13_oct23.zip td3
curl --upload-file ./td3_ros_reacher_doc13_oct23.zip https://transfer.sh/td3_ros_reacher_doc13_oct23.zip
zip -r td3_ros_reacher_doc13_oct23_models.zip td3
curl --upload-file ./td3_ros_reacher_doc13_oct23_models.zip https://transfer.sh/td3_ros_reacher_doc13_oct23_models.zip
```

```
cd ~/rl_ws/src/multiros
git pull

cd ~/rl_ws/src/reactorx200
git clone https://github.com/ncbdrck/reactorx200_ros_reacher

cd ~/rl_ws/src/
git clone https://github.com/ncbdrck/ros_rl.git
git clone https://github.com/ncbdrck/sb3_ros_support.git
git clone https://github.com/ncbdrck/hrl-kdl.git

cd ~/rl_ws/src/hrl-kdl/pykdl_utils
python3 setup.py build
sudo python3 setup.py install

cd ~/rl_ws/src/hrl-kdl/hrl_geom/
python3 setup.py build
sudo python3 setup.py install

sudo apt-get install ros-noetic-urdf-parser-plugin
sudo apt-get install ros-noetic-urdfdom-py

cd ~/rl_ws/
rm -rf devil/ build/
rosdep install --from-paths src --ignore-src -r -y
catkin_make
source devel/setup.bash
rospack profile
```
