# 解决Linux低分屏下字体模糊发虚的问题
## 0.打开点阵[https://askubuntu.com/questions/1244175/how-can-i-activate-bitmap-fonts-on-20-04]
```
$ rm /etc/fonts/conf.d/70-no-bitmaps.conf
$ ln -s ../conf.avail/70-force-bitmaps.conf /etc/fonts/conf.d/
$ dpkg-reconfigure fontconfig-config
$ dpkg-reconfigure fontconfig
$ cp *.otb /usr/local/share/fonts
$ dpkg-reconfigure fontconfig-config
$ dpkg-reconfigure fontconfig
$ fc-list | grep otb
```
## 1.下载文泉驿正黑（黑体矢量+宋体点阵）
```
git clone https://github.com/czcq/linux-fonts-config.git
```
## 2.配置文泉驿正黑 /etc/fonts/conf.d/66-wqy-zenhei-sharp.conf
```
cd linux-fonts-config
sudo cp 66-wqy-zenhei-sharp.conf /etc/fonts/conf.d/
fc-cache -fv
```
## 3.xfce中配置字体
![image](https://user-images.githubusercontent.com/16433413/118372669-66b1d200-b5e5-11eb-9eaa-767d88f3c4f1.png)

## 4.firefox配置简体中文、拉丁字母
![image](https://user-images.githubusercontent.com/16433413/118372372-e6d73800-b5e3-11eb-83c0-4dc61099e51b.png)
![image](https://user-images.githubusercontent.com/16433413/118372396-fa829e80-b5e3-11eb-8843-180ab4d5fef9.png)
## 5.local.conf可选配置


## 6.使用gohufont(12pt,14pt)[https://font.gohu.org/] 点阵作为monospace
```
cp *.otb /usr/share/fonts/
fc-cache -fv
dpkg-reconfigure fontconfig
fc-list | grep otb
```

## 7.效果
![image](https://user-images.githubusercontent.com/16433413/118372844-1dae4d80-b5e6-11eb-80c7-b6a8177f1595.png)
![image](https://user-images.githubusercontent.com/16433413/118372901-6403ac80-b5e6-11eb-96b7-6593fe5fa3d7.png)

