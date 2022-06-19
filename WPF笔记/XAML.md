# XAML

## 概要
WPF和传统的winForm应用一样是通过两个部分类，分别是XAML表示其中一个部分类，后端的C#代码表示另一个类这个类派生自Window类，这两个类编译后构成了一个类。
XAML是一种声明新的语言，编写的标签最终会被实例为一个对应该该标签类的对象实例。

**示例代码**


- `xmlns:` 表示用来声明名称空间 格式`xmlns:空间名="值"` 如果是默认空间可以省略空间名称。
- 名称空间值是以http开头的这种引用的资源不知一个而是一个程序集，里面包含有很多资源
- `xmlns:local` 是用来声明本地名称空间. 

```xaml
<Window x:Class="WpfApp1.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:WpfApp1"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Grid>
       
    </Grid>
</Window>
```


