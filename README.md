# CPTN-demo
使用框架：https://github.com/dlunion/CCDL
参考作者：https://github.com/tianzhi0549/CTPN
为了使用python layer ,需要在layer_factory.cpp中加入
#define BOOST_PYTHON_STATIC_LIB
#define WITH_PYTHON_LAYER = 1
然后重新编译libcaffe 和python（python使用Anaconda2）

.pyx转换pyd:在“..python安装路径...\Lib\distutils目录下有个msvc9compiler.py找到243行 toolskey = "VS%0.f0COMNTOOLS" % version   直接改为 toolskey = "VS你的版本COMNTOOLS".for example:toolskey = "VS120COMNTOOLS" 
 添加完后，命令行切换到utils/目录下执行Python setup.py install，会出现fatal error C1083: 无法打开包括文件: “numpy/npy_math.h”: No such file or directory。这里将这些包含头文件改为绝对路径即可。
 生成后，执行demo-cmd 即可展示结果。
 常见错误及编译参考：http://blog.csdn.net/chenzhi1992/article/details/52618386


