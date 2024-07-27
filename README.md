Here I will install Ros2 humble in ubuntu 22.04 on Mac m1

## first install Virtual machines for Mac (UTM)
here the link:

```
https://mac.getutm.app
```

### Second install Ubuntu 22.04 in the same link

1- Click on GALLERY
<img width="1440" alt="‏لقطة الشاشة ١٤٤٦-٠١-٢١ في ١ ٤٦ ٢٥ م" src="https://github.com/user-attachments/assets/ecd26802-fcf9-467b-bf07-ceb01aa3e5dd">

2- Scroll down and find Ubuntu 22.04
<img width="1440" alt="‏لقطة الشاشة ١٤٤٦-٠١-٢١ في ١ ٥٠ ٠٠ م" src="https://github.com/user-attachments/assets/c3a271bb-f3f9-4e08-9cd9-5b91a88724b2">

3-then Click on Open in UTM
<img width="1440" alt="‏لقطة الشاشة ١٤٤٦-٠١-٢١ في ١ ٥٥ ١٦ م" src="https://github.com/user-attachments/assets/275a0798-64cd-4f75-8abe-6e8a9c72fa6a">

#### Install ROS2 humble
1-here the link:
```
https://docs.ros.org/en/humble/Installation.html
```
2-Install Binary packages
<img width="1440" alt="‏لقطة الشاشة ١٤٤٦-٠١-٢١ في ٢ ٠٣ ٤٨ م" src="https://github.com/user-attachments/assets/75396051-3c40-4653-8daf-cbc71d8afaf0">

##### Open Terminal
1- Use this command to Make sure you have a locale which supports UTF-8:

```
locale
```
<img width="1440" alt="‏لقطة الشاشة ١٤٤٦-٠١-٢١ في ٢ ١٥ ٢٣ م" src="https://github.com/user-attachments/assets/cc805fab-4336-4071-9e6e-e84880ca7c0f">


if you dont see UTF-8 just use this command
```
sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8

locale  # verify settings
```
2-to add the ROS 2 apt repository to your system First ensure that the Ubuntu Universe repository is enabled.

```
apt-cache policy | grep universe
```

The should output like this:
<img width="1440" alt="‏لقطة الشاشة ١٤٤٦-٠١-٢١ في ٢ ٢٢ ١١ م" src="https://github.com/user-attachments/assets/2601cb2f-1365-435c-bc55-987b21bf52a4">

3- Now add the ROS 2 GPG key with apt:
```
sudo apt update && sudo apt install curl -y
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
```
4-Then add the repository to your sources list:
```
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
```
