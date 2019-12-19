# csv2src
game config convert to source code



### Usage

1. install Python 2.x (we test in Python 2.7)
2. run cmd `python csv2lua.py` or `python csv2py.py`



### Feature

- support csv, xls, xlsx

- support convert to lua, python

- custom ignore files and fields

- more headers

  | 变量名 | rank      | _comment                        | rank_tw    | bkCsv          |
  | ------ | --------- | ------------------------------- | ---------- | -------------- |
  | 默认值 | <>        |                                 | <1;2>      |                |
  | ID     | 列名含义  | 变量名前缀_为注释列，不参与生成 | 多语言支持 | 文件引用       |
  | 1      | <1;100>   |                                 |            | stage/xszd.csv |
  |        | <101;200> | 没有ID，不参与生成              |            |                |

- extend csv

  - Bool
    - true, false, True, False, TRUE, FALSE
  - String
    - "123"
    - '   abc  '
  - Array
    - <item1;item2;item3;item4>
  - Map:
    - {key=value;key=value}
    - key must are int or string
  - Nested Array or Map
    - <1;<2;3>;{a=1;b=2};4>

- support gen cache 

  - LastModifyList.txt will record the last gen file modified time

- special for lua

  - slim redundancy lua table when the values same
  - deal with 65536 constants limit
  - use metatable for default value

- special for python

  - namedtuple for row fields

- simple value type check

- simple value  implicit convert

  - bool, number -> string