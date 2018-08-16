### 数组
* 值传递
* 长度固定
* len(array)
 
 ```
 1. [6]int {1, 2, 3, 4, 5, 6 }
 2. [6]int {1, 2}
 3. [...]int {1, 2, 3, 4, 5, 6}
 4. [5] int {2: 1, 3: 2, 4: 3} 等价于 [5] int {0, 0, 1, 2, 3}
 5. [...] int {2: 1, 4: 3} 等价于 [5] int {0, 0, 1, 0, 3}
 
 ```

### 切片
* 引用类型
* len(array) 长度, cap(array) 容量
* append 可以改变长度
* []来定义切片类型

```
1. s := [] int {1, 2, 3} cap = len = 3
2. s := arr[:] 初始化切片s，是arr的一个引用
3. s := arr[startIndex:endIndex] 将arr中从下标startIndex到endIndex-1 下的元素创建为一个新的切片
4. s := arr[startIndex:] startIndex 到最后一个元素
5. s :=make([]int,len,cap) make初始化标示为int的切片
6. s := append(s, 1, 2, 3, 4)
7. s := append(s, s1...) 
```

### Map
* 引用类型

```
func offset(tz string) int {
	if seconds, ok := timeZone[tz], ok {
		return seconds
	}
	log.Println("unknow time zone:", tz)
	return 0
}
```

### 方法
* 两种具体方法，值和指针
* 值，改方法需要返回更新后的切片，比较麻烦，其实是指值为接收者

```
type ByteSlice []byte

func (slice ByteSlice) Append(data []byte) []byte {
	// append data to slice
}
```

* 指针

```
func (p *ByteSlice) Write(data []byte) {
	slice := *p
	// append data to slice
	*p = slice
}
```

```
更优雅的方式

func (p *ByteSlice) Write(data []byte) (n int, err error) {
	slice := *p
	// append data to slice
	*p = slice
	return len(data), nil
}
```


* 值方法可以通过指针和值调用，指针方法只能通过指针来调用

