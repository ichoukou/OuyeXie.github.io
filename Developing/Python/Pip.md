pip 官網的說法，pip 改善了不少 easy_install 的缺點，如此說來 pip 應該是略勝一籌，不過它還不能夠完全取代對方，因為目前有很多套件還是得用 easy_install 安裝

 - http://my.oschina.net/swrite/blog/298051
 - http://blog.csdn.net/xifeijian/article/details/12576455
 
Using pip and requirements.txt to install from the HEAD of a Github branch
 - http://pip.readthedocs.org/en/1.1/requirements.html
 - http://codeinthehole.com/writing/using-pip-and-requirementstxt-to-install-from-the-head-of-a-github-branch/)
 - http://stackoverflow.com/questions/32354249/pip-requirements-txt-github-repo-django-app
 
Unable to Uninstall Program : Own by OS
 - http://askubuntu.com/questions/647919/unable-to-uninstall-program-own-by-os
    - sudo rm -rf /usr/lib/python2.7/dist-packages/six-1.5.2.egg-info

Pip install

<pre>
$ pip install SomePackage            # latest version
$ pip install SomePackage==1.0.4     # specific version
$ pip install 'SomePackage>=1.0.4'     # minimum version
$ pip2 install SomePackage           # install into python2.*/dist-package
$ pip3 install SomePackage           # install into python3.*/dist-package
</pre>


 
# Command
 - http://www.aikaiyuan.com/6918.html
 - https://pip.pypa.io/en/stable/user_guide/#installing-packages