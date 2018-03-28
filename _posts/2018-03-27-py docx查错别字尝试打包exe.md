

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


