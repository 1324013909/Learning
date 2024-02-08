# Unity手游开发中所有特殊的文件夹

## 1.Editor

### Editor文件夹无确定位置，也无数量要求。

##### Editor下面放的所有资源文件或者脚本文件都不会被打进发布包中， 并且脚本也只能在编辑时使用。

#####  一般呢会把一些工具类的脚本放在这里，或者是 一些编辑时用的DLL。

## 2.Editor Default Resources

### Editor Default Resources必须放在Project视图的根目录下

##### 不会被打到最终发布包里，仅仅用于开发时使用

##### 可以把编辑器用到的一些资源放在这里，比如图片、文本文件等等。

## 3.Gizmos

##### 可以在Scene视图里给某个坐标绘制一个icon

```
void OnDrawGizmos() {
        Gizmos.DrawIcon(transform.position, "0.png", true);
}
```

## 4.Plugins

##### 用于存放插件 ：如Andoird 或者 ios 要接一些sdk，可以把sdk依赖的库文件 放在这里，比如 .so .jar .a 文件。放至于此文件夹后打包会自动将这些文件打在你的包中。

## 5.Resources

### Resources文件夹无确定位置，也无数量要求。

#### Resources文件夹下的资源都会被打包,会压缩文件

```
Resource.Load();  编辑时和运行时都可以通过Resource.Load来直接读取。
```

```
Resources.LoadAssetAtPath();  它可以读取Assets目录下的任意文件夹下的资源，它可以在编辑时或者编辑器运行时用，但是它不能在真机上用，它的路径是”Assets/xx/xx.xxx” 必须是这种路径，并且要带文件的后缀名。
```

```
AssetDatabase.LoadAssetAtPath();  它可以读取Assets目录下的任意文件夹下的资源，它只能在编辑时用。它的路径是”Assets/xx/xx.xxx” 必须是这种路径，并且要带文件的后缀名。。
```

## 5.StreamingAssets

#### StreamingAssets文件夹下的资源都会被打包；不会压缩文件（比较占内存）；【**只读**】

#### 在各个平台下的路径是不同的，可以用Application.streamingAssetsPath 选择对应的路径。