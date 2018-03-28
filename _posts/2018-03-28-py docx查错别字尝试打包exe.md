


使用py2exe
ide：pycharm
file /settings / project/project interpreter 选择3.4及以下版本（py2exe不支持3.5以上）
添加package： 
+ py2exe
+ python-docx


同一目录下新建build.py:


    from distutils.core import setup
    import py2exe, sys, os

    sys.argv.append('py2exe')

    setup(
        options = {'py2exe': {'bundle_files': 1, 'compressed': True}},
        windows = [{'script': "contract.py"}],
        zipfile = None,
    )

build成功：

    running py2exe

      3 missing Modules                  
      ------------------                 
    ? readline                            imported from cmd, code, pdb
    ? win32api                            imported from platform
    ? win32con                            imported from platform
    Building 'dist\contract.exe'.

    Process finished with exit code 0

可执行文件.exe存放在dist目录下 
