# clion快捷键使用

## clion中选中整个单词

### 移动到单词最前部分和末尾

<kbd>⌥</kbd>+<kbd>→</kbd>可以移动到整个单词的末尾,比如移动到一个变量或者函数名的最前面和末尾,可以选择增加shift来是否选中整个单词

<kbd>⌥</kbd>+<kbd>→</kbd>这种快捷键组合也可以根据驼峰命名法来移动,比如,勾选setting->编辑器->常规->Smart keys中的`使用 ‘驼峰’词`,每次option+右键移动的就是一个驼峰的距离.

### 直接选中整个单词

<kbd>⌥</kbd>+<kbd>↑</kbd> 快捷键,可以直接选择整个单词,在快捷键设置里面的拓展选择

<kbd>⌥</kbd>+<kbd>↓</kbd> 快捷键,可以取消选择整个单词,在快捷键设置里面的缩小选择

## 删除行

<kbd>⌘</kbd>+<kbd>⌫</kbd> 删除行

同时不选中任何部分, <kbd>⌘</kbd>+<kbd>x</kbd> 也有剪切整行的作用

## 快速复制

<kbd>⌘</kbd>+<kbd>d</kbd>可以直接复制,在不选中的情况下,将默认复制当前一整行,并粘贴到下一行.

<kbd>⌘</kbd>+<kbd>d</kbd>选中情况下,将复制选中部分到光标当前位置后面.

# 汉化包

可以从这个[github仓库](https://github.com/pingfangx/jetbrains-in-chinese)中找





# 配置问题

pycharm2018.3安装3.8的python解释器会出问题,关键看最后一句.这个问题已经被修复,修改方案可以看[这里](https://github.com/JetBrains/intellij-community/commit/07ef928f3b1fbc24401380110691342a558de242)

```shell
C:\anaconda3\envs\pytorch\python.exe "C:\software\Jetbrain\PyCharm 2018.3.7\helpers\pydev\pydevconsole.py" --mode=client --port=53845
C:\anaconda3\envs\pytorch\lib\site-packages\numpy\__init__.py:148: UserWarning: mkl-service package failed to import, therefore Intel(R) MKL initialization ensuring its correct out-of-the box operation under condition when Gnu OpenMP had already been loaded by Python process is not assured. Please install mkl-service package, see http://github.com/IntelPython/mkl-service
  from . import _distributor_init
Traceback (most recent call last):
  File "C:\software\Jetbrain\PyCharm 2018.3.7\helpers\pydev\pydevconsole.py", line 33, in <module>
    from _pydev_bundle.pydev_console_utils import BaseInterpreterInterface
  File "C:\software\Jetbrain\PyCharm 2018.3.7\helpers\pydev\_pydev_bundle\pydev_console_utils.py", line 11, in <module>
    from _pydevd_bundle import pydevd_thrift
  File "C:\software\Jetbrain\PyCharm 2018.3.7\helpers\pydev\_pydevd_bundle\pydevd_thrift.py", line 17, in <module>
    from pydev_console.protocol import DebugValue, GetArrayResponse, ArrayData, ArrayHeaders, ColHeader, RowHeader, \
  File "C:\software\Jetbrain\PyCharm 2018.3.7\helpers\pydev\pydev_console\protocol.py", line 6, in <module>
    _console_thrift = _shaded_thriftpy.load(os.path.join(os.path.dirname(os.path.realpath(__file__)), "console.thrift"),
  File "C:\software\Jetbrain\PyCharm 2018.3.7\helpers\third_party\thriftpy\_shaded_thriftpy\parser\__init__.py", line 29, in load
    thrift = parse(path, module_name, include_dirs=include_dirs,
  File "C:\software\Jetbrain\PyCharm 2018.3.7\helpers\third_party\thriftpy\_shaded_thriftpy\parser\parser.py", line 502, in parse
    parser.parse(data)
  File "C:\software\Jetbrain\PyCharm 2018.3.7\helpers\third_party\thriftpy\_shaded_ply\yacc.py", line 331, in parse
    return self.parseopt_notrack(input, lexer, debug, tracking, tokenfunc)
  File "C:\software\Jetbrain\PyCharm 2018.3.7\helpers\third_party\thriftpy\_shaded_ply\yacc.py", line 1106, in parseopt_notrack
    p.callable(pslice)
  File "C:\software\Jetbrain\PyCharm 2018.3.7\helpers\third_party\thriftpy\_shaded_thriftpy\parser\parser.py", line 212, in p_struct
    val = _fill_in_struct(p[1], p[3])
  File "C:\software\Jetbrain\PyCharm 2018.3.7\helpers\third_party\thriftpy\_shaded_thriftpy\parser\parser.py", line 765, in _fill_in_struct
    gen_init(cls, thrift_spec, default_spec)
  File "C:\software\Jetbrain\PyCharm 2018.3.7\helpers\third_party\thriftpy\_shaded_thriftpy\thrift.py", line 103, in gen_init
    cls.__init__ = init_func_generator(default_spec)
  File "C:\software\Jetbrain\PyCharm 2018.3.7\helpers\third_party\thriftpy\_shaded_thriftpy\_compat.py", line 102, in init_func_generator
    new_code = types.CodeType(len(varnames),
TypeError: an integer is required (got type bytes)

```

修改方案就是替换最后报错的`C:\software\Jetbrain\PyCharm 2018.3.7\helpers\third_party\thriftpy\_shaded_thriftpy\_compat.py`这个文件的这部分

```python
    # 原始PY3部分
    if PY3:
        new_code = types.CodeType(len(varnames),
                                  0,
                                  len(varnames),
                                  code.co_stacksize,
                                  code.co_flags,
                                  code.co_code,
                                  code.co_consts,
                                  code.co_names,
                                  varnames,
                                  code.co_filename,
                                  "__init__",
                                  code.co_firstlineno,
                                  code.co_lnotab,
                                  code.co_freevars,
                                  code.co_cellvars)
    # 替换为
        if PY3:
        args = [
            len(varnames),
            0,
            len(varnames),
            code.co_stacksize,
            code.co_flags,
            code.co_code,
            code.co_consts,
            code.co_names,
            varnames,
            code.co_filename,
            "__init__",
            code.co_firstlineno,
            code.co_lnotab,
            code.co_freevars,
            code.co_cellvars
        ]
        if sys.version_info >= (3, 8, 0):
            # Python 3.8 and above supports positional-only parameters. The number of such
            # parameters is passed to the constructor as the second argument.
            args.insert(2, 0)
        new_code = types.CodeType(*args)
```

