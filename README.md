# 命名规范
> 大驼峰（Upper Camel Case）：
> 第一个单词的首字母大写，单词间使用大写字母作为词的分割，其他的字母均使用小写。

>小驼峰（Lower Camel Case）：
>第一个单词的首字母小写，单词间使用大写字母作为词的分割，其他的字母均使用小写。

> 下划线命名法（snake-case）：
复合词或短语中的各个单词之间用下划线（_）分隔并且没有空格。复合词中的每一个单词的首字母通常都是小写的，并且复合词的第一个字母既可以是大写的又可以是小写的，例如：“foo_bar”和“Hello_world”。

>匈牙利命名法：基本原则是：变量名=属性+类型+对象描述，其中每一对象的名称都要求有明确含义，可以取对象名字全称或名字的一部分。[前缀类型] `a b by c cb cr cx,cy dw fn h i l lp m_ n np p s sz w`
```
（一一对应关系） 
- 数组 `(Array) `
- 布尔值` (Boolean) `
- 字节 `(Byte)`
- 有符号字符 `(Char)` 
- 无符号字符 `(Char Byte，没有多少人用)` 
- 颜色参考值 `(ColorRef)` 
- 坐标差`（长度 ShortInt）` 
- `Double Word` 函数 
- `Handle`（句柄） 
- 整型 长整型 `(Long Int)` 
- `Long Pointer` 类的成员 
- 短整型 `(Short Int)` 
- `Near Pointer Pointer `
- 字符串型 以 null 做结尾的字符串型 `(String with Zero End) Word`
```
## 文件夹命名
- 文件夹统一使用**小写字母**，如果文件夹名由多个单词组成可以使用 `-` 或 `_` 来分割【 `laravel` 项目中除 `app` 文件夹下面的文件夹除外。比如:`Models`, `Controllers`, `Requests`, `Repositories`, `Classes` 等例外 】例子，例如: `app`, `jakub-onderka`, `import_user`。
## 文件的命名
- 如果是类文件的话，那么文件的命名应该同类名称保持一致，统一使用**大驼峰**。如 `User.php` , `UnitController.php`。如果是控制器, repo, 请求记得他们是有后缀 `Controller`, `Repository`, `Request`
- 如果是普通的文件名，统一使用**小驼峰**，如 `helper.php`。
## 常量命名
- 常量、全局常量，使用大写字母命名，单词之间用 `_` 来分割，如 `USERNAME`, `DB_HOST`, `define('DEFAULT_NUM_AVE',90)`。
## 普通变量命名
- **匈牙利命名法** ， **下划线命名法**，**小驼峰**都会用，比较纠结
- 临时变量通常被取名为i，j，k，m和n，它们一般用于整型；c，d，e，s 它们一般用于字符型。
- 临时变量还可以加 `temp` 为前缀
- 实例变量前面需要一个下划线， 首单次小写，其余单词首字母大写。
## 全局变量
- 全局变量应该带有前缀 `g`(代表global)。如：`global $gTest`。
## 静态变量
- 静态变量应该带有前缀 `s`(代表static)。如：`static $sStatus = 1`     
## 引用变量
- 引用变量要带有`r`(代表reference) 前缀。如：
```
class Example{
    $mExam = "";
    funciton setExam(&$rExam){
        ...
    }
    function getExam(){
        ...
    }
}
```
## 方法中的参数命名
- 统一使用**小驼峰**
## 类命名
- 使用**大驼峰**
  - 模型类【model】
- 使用**大驼峰**，例如： `Area`, `ItemType`
  - 控制器类【controller】
使用**大驼峰 + `Controller` 后缀 **, 例如： `IndexController`, `InvoiceTypeController`
  - 请求类【request】
- 新建和修改的请求分别使用 **`Create` 前缀 + 大驼峰 + `Request` 后缀** 和  **`Update` 前缀 + 大驼峰 + `Request` 后缀**。例如：`UpdateCodeTypeRequest.php`, `CreateAreaRequest.php` 
  - 仓库类【repository】
使用**大驼峰 + `Repository` 后缀 **, 例如： `AreaRepository.php`, `InvoiceHeaderTypeRepository.php`
  - ##提供者类【Providers】
使用**大驼峰 + `ServiceProvider` 后缀 **, 例如： `AppServiceProvider.php`, `PassportDingoProvider.php`
## 类方法的命名
名称一般使用 **动词 + 名词** 构成。所以名称应该说明方法是做什么的。一般名称的前缀都是有第一规律的，如 `is`（判断）、`get`（得到），`set`（设置）， `can`（能否）。
方法的命名使用**小驼峰**，首字母小写或者使用下划线 ”_”，例如 `getLessonOne()` ， `_getResource()`，通常下划线开头的方法属于私有方法。
## 类属性的命名
属性的命名使用**小驼峰**，首字母小写或者使用下划线”_”，如 `$username` ， `$_instance`，通常下划线开头的属性属于私有属性;
## 函数的命名
函数的命名使用**下划线命名法**。例如: `get_client_ip`;
***
# 约定
- 会根据环境变化的参数变成配置项
***
# 代码尽量干净
- 合并代码时, 把注释掉的代码删除掉, 自己可以保留注释的代码(很少的注释可以接受, 多的就不可以)
***
# 注意点
- 反斜杠'/'用全局变量`DIRECTORY_SEPARATOR`代替
- 在Linux环境下执行php命令要在php前面拼接完整路径,可以在配置项定义好php路径.例如: 
```
    'command' => [
        'php_command' => '/usr/local/php/bin/php'
    ]
```
