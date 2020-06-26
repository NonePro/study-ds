# 结合go语言理解数组数据结构

## 静态数组
### 定义数组

#### 显式声明并赋初始值

```shell script
var arr [10]int
fmt.Printf("%v", arr)
fmt.Println(reflect.TypeOf(arr))

// [0 0 0 0 0 0 0 0 0 0]
// [10]int
```

#### 隐含式声明并赋值

##### 明确指定数量

```shell script
arr1 := [8]int{0, 1, 2, 3, 4, 5, 6, 7}
fmt.Println(arr1)
fmt.Println(reflect.TypeOf(arr1))

// [0 1 2 3 4 5 6 7]
// [8]int
```

##### 不指定数量

```shell script
arr1 := [8]int{0, 1, 2, 3, 4, 5, 6, 7}
fmt.Println(arr1)
fmt.Println(reflect.TypeOf(arr1))

// [2 4 6 8 10]
// [5]int

```

#### 多维数组定义

```shell script
var arr3 [4][5]bool
fmt.Println(arr3)
fmt.Println(reflect.TypeOf(arr3))
```

通过以上的例子有以下几点是非常明确的：
* 元素的数据类型需要明确
* 数组的长度是固定的

这两个原则的组合能够让我们申请到逻辑上连续的内存地址，并且空间大小可以根据数据类型进行确定。能够实现基于索引的随机访问，这是数组的的核心。

与数据结构中对数组的定义是一致的。

## 动态数组

静态数组的很大束缚在于需要在使用初期就确定数组的大小，这在很多场景下都是困难的.数据结构基于静态数组引入reseize机制实现动态数组来让用户感知不到这一限制。而其底层依然是静态的。

803
