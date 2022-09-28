# 解决Linux低分屏下字体模糊发虚的问题

# latest 

* install necessary fonts
```
sudo apt-get install fonts-wqy,ttf-wqy-zenhei ttf-wqy-microhei fonts-arphic-ukai fonts-arphic-uming
```

 

* font configuration
```bash
git clone https://github.com/czcq/linux-fonts-config
cd linux-fonts-config
dpkg -i wqy-bitmapfont-1.0.0-RC1_all.deb # install wqy bitmap song
cd linux-fonts-config/msfonts/
double click all ttf files and install # install microsoft Chinese fonts
sudo apt install ttf-mscorefonts-installer # Times New Roman && Arial
```

```bash

vim /etc/fonts/fonts.conf

<!--
  Load local system customization file
-->
        <include ignore_missing="yes">/home/yang/linux-fonts-config/conf.d/</include>
```

* result
	```bash
	fc-cache -f -v
	fc-list | grep wqy
	fc-match '宋体'
	fc-match '黑体'
	fc-match 'serif'
	fc-match 'sans-serif'
        ```
        
        
![image](https://user-images.githubusercontent.com/16433413/138245945-a05771c0-83d4-4ef5-aba5-815e4c99cfaf.png)






