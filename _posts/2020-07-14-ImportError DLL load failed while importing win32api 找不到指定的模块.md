---
title: ImportError：DLL load failed while importing win32api：找不到指定的模块
date: 2020-07-14 00:10:10
categories:
 - Python
tags: errors
---
## ImportError: DLL load failed while importing win32api: 找不到指定的模块

前几天在尝试打开jupyter lab是报以下错误：

```
Error Starting Kernel
Invalid response: 500 Internal Server Error
Unhandled error
详细信息
Traceback (most recent call last):
  File "c:\users\administrator\anaconda3\envs\communitydetection\lib\site-packages\tornado\web.py", line 1703, in _execute
    result = await result
  File "c:\users\administrator\anaconda3\envs\communitydetection\lib\site-packages\tornado\gen.py", line 742, in run
    yielded = self.gen.throw(*exc_info)  # type: ignore
  File "c:\users\administrator\anaconda3\envs\communitydetection\lib\site-packages\notebook\services\sessions\handlers.py", line 69, in post
    model = yield maybe_future(
  File "c:\users\administrator\anaconda3\envs\communitydetection\lib\site-packages\tornado\gen.py", line 735, in run
    value = future.result()
  File "c:\users\administrator\anaconda3\envs\communitydetection\lib\site-packages\tornado\gen.py", line 742, in run
    yielded = self.gen.throw(*exc_info)  # type: ignore
  File "c:\users\administrator\anaconda3\envs\communitydetection\lib\site-packages\notebook\services\sessions\sessionmanager.py", line 88, in create_session
    kernel_id = yield self.start_kernel_for_session(session_id, path, name, type, kernel_name)
  File "c:\users\administrator\anaconda3\envs\communitydetection\lib\site-packages\tornado\gen.py", line 735, in run
    value = future.result()
  File "c:\users\administrator\anaconda3\envs\communitydetection\lib\site-packages\tornado\gen.py", line 742, in run
    yielded = self.gen.throw(*exc_info)  # type: ignore
  File "c:\users\administrator\anaconda3\envs\communitydetection\lib\site-packages\notebook\services\sessions\sessionmanager.py", line 100, in start_kernel_for_session
    kernel_id = yield maybe_future(
  File "c:\users\administrator\anaconda3\envs\communitydetection\lib\site-packages\tornado\gen.py", line 735, in run
    value = future.result()
  File "c:\users\administrator\anaconda3\envs\communitydetection\lib\site-packages\tornado\gen.py", line 209, in wrapper
    yielded = next(result)
  File "c:\users\administrator\anaconda3\envs\communitydetection\lib\site-packages\notebook\services\kernels\kernelmanager.py", line 168, in start_kernel
    super(MappingKernelManager, self).start_kernel(**kwargs)
  File "c:\users\administrator\anaconda3\envs\communitydetection\lib\site-packages\jupyter_client\multikernelmanager.py", line 186, in start_kernel
    km.start_kernel(**kwargs)
  File "c:\users\administrator\anaconda3\envs\communitydetection\lib\site-packages\jupyter_client\manager.py", line 304, in start_kernel
    kernel_cmd, kw = self.pre_start_kernel(**kw)
  File "c:\users\administrator\anaconda3\envs\communitydetection\lib\site-packages\jupyter_client\manager.py", line 251, in pre_start_kernel
    self.write_connection_file()
  File "c:\users\administrator\anaconda3\envs\communitydetection\lib\site-packages\jupyter_client\connect.py", line 468, in write_connection_file
    self.connection_file, cfg = write_connection_file(self.connection_file,
  File "c:\users\administrator\anaconda3\envs\communitydetection\lib\site-packages\jupyter_client\connect.py", line 138, in write_connection_file
    with secure_write(fname) as f:
  File "c:\users\administrator\anaconda3\envs\communitydetection\lib\contextlib.py", line 113, in __enter__
    return next(self.gen)
  File "c:\users\administrator\anaconda3\envs\communitydetection\lib\site-packages\jupyter_core\paths.py", line 435, in secure_write
    win32_restrict_file_to_user(fname)
  File "c:\users\administrator\anaconda3\envs\communitydetection\lib\site-packages\jupyter_core\paths.py", line 361, in win32_restrict_file_to_user
    import win32api
ImportError: DLL load failed while importing win32api: 找不到指定的模块。
```

在网上找了一大堆解决办法，没有解决，先挂起不提。。。

今天又要用到jupyter lab，于是乎又Google解决办法，终于找到一个对于自身可行的办法 ：）

解决办法：

1. 先卸载pywin32（原来装的版本是228）
2. 安装pywin32\==225：pip install pywin32\==225



### 参考：

1.  https://stackoverflow.com/questions/58612306/how-to-fix-importerror-dll-load-failed-while-importing-win32api 