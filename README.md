# SIR(Script Inter-language) 

一种服务于脚本执行的可二进制化指令语言

## 支持的虚拟机

SEVM：Script Execution Virtual Machine <https://github.com/inmount/SEVM>

## 指令说明

为了最大化的兼容现有从业者的使用习惯，我将使用类似汇编语言的指令方式定义。

### 一、段指令

#### 1.1 数据定义define及end define

用来申请内存及定义名称。

支持的类型包括：any, number, string, list, native_object, native_function

例如：

···
define
    number a, 1
    number b, 2
    number c, 0
    string $0, "a+b的和是"
    any str,
    list $1 
end define
···

#### 1.2 代码段定义code及end code

用来定义代码区域

例如：

···
code main
    mov #0, a
    add #0, b
    mov c, #0
    mov #0, [$1]
    mov #1, 0
    push [$0]
    push [c]
    join str, $1
end code
···
