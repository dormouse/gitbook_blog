Linux Note
==========

date
:   2016-05-27

modified
:   2017-05-09

slug
:   linux-note

tags
:   linux, note

category
:   software

author
:   Dormouse Young

summary
:   Note of how to use linux

Install chrome
--------------

date: 2016-05-27

    wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
    sudo gdebi google-chrome-stable_current_amd64.deb

Install new font
----------------

date: 2015-04-29

### How-to

For system wide installation, copy the fonts to /usr/share/fonts and run
`sudo fc-cache` to rebuild the font cache, or for user local
installation, make sure `~/.fonts` exists, copy them into there, then
rebuild the font cache.

### Example

Install
[adobe-fonts/source-code-pro](https://github.com/adobe-fonts/source-code-pro)
in Ubuntu 14.04:

    [ -d /usr/share/fonts/opentype ] || sudo mkdir /usr/share/fonts/opentype
    sudo git clone https://github.com/adobe-fonts/source-code-pro.git /usr/share/fonts/opentype/scp
    sudo fc-cache -f -v

Install Anaconda
----------------

官方网站：https://www.continuum.io/
清华大学开源软件镜像站：https://mirrors.tuna.tsinghua.edu.cn/help/anaconda/

conda 官方文档：https://docs.continuum.io/docs\_oss/conda/using/

查看版本：
:   conda -V conda --version

查看信息：
:   conda info

查看当前所在的虚拟环境：
:   conda info --e

创建虚拟环境：
:   conda /home/somebody/anaconda3/bin/conda create -p
    /home/somebody/anaconda3/envs/env\_name -y python=3.6

切换虚拟环境：
:   source activate env\_name

查看当前环境的包列表：
:   conda list

搜索包：
:   conda search beautifulsoup4


