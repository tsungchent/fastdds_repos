# install java-sdk
https://www.oracle.com/java/technologies/downloads/#java8

# install bison

- download bison from http://gnuwin32.sourceforge.net/packages/bison.htm
- install bison (!!! don't install to filepath which contain space or bracket)

# install dependencies
```
python3 -m pip -U install vcstool colcon-common-extensions colcon-gradle
```
# build fastdds 
[for windows, open x64 native tools command console, and ]
```
git clone git@github.com:tsungchent/fastdds_repos.git

cd fastdds_repos

vcs import src < fastrtps.repos

colcon build --merge-install --symlink-install
```

# run fastdds_python example
- copy fastrtps-x.x.dll, fastcdr-x.x.dll HelloWorld.dll to \${CMAKE_INSTALL_PREFIX}\lib\site-packages
 or add \${CMAKE_INSTALL_PREFIX}\bin to environment PATH
- add \${CMAKE_INSTALL_PREFIX}\lib\site-packages to PYTHONPATH
- run HelloWorldExample.py
```
python HelloWorldExample.py -p ... publisher
```

# build issues

- swig 链接pcre2失败,(原因, 静态编译错误使用了__declspec(dllimport))
```
外部符号 __imp_pcre2_config_8，函数 Swig_pcre_version 中引用了该符号  
...
```

设置 pcre2 cmake 选项 "BUILD_SHARED_LIBS" ON 或者 给swig编译添加宏定义PCRE2_STATIC





