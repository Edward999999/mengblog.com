## pip install PyInstaller
安装之后通过打包命令 `pyinstaller -F -w -i aaa.ico zzz.py `打包提示错误

    PyInstaller cannot check for assembly dependencies.
    Please install PyWin32 or pywin32-ctypes.



修改 `D:\Program Files\Python\Lib\site-packages\PyInstaller\compat.py` 201、202行

    if is_win:
    try:
        # from win32ctypes.pywin32 import pywintypes  # noqa: F401, E402
        # from win32ctypes.pywin32 import win32api  # noqa: F401, E402
        import pywintypes
        import win32api
中的from 为import

