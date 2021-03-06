# [C_string]C风格String的用法

## 1.字符数组与字符串的差别

字符串的最后一个元素为空字符('\0')。

```C++
char str1[] = {'H','e','l','l','o'}; //是字符数组
char str2[] = {'H','i','\0'}; //是字符串
```

## 2.字符串的初始化方法

```C++
char str2[] = {'H','i','\0'}; //是字符串
char str3[] = "Hello";  //这里是双引号
char str4[8] = "Hi";  //str4 = ['H','i','\0','\0','\0','\0','\0','\0'] 
```

## 3.sizeof()与strlen()

sizeof()的返回值是整个结构的大小，而strlen()返回显式的字符长度，且不包含空字符。

```C++
char str[4] = "Hi";
cout << strlen(str) << endl;
cout << sizeof(str) << endl;
```

输出值分别为4和2，即使空字符后面依然有字符，该字符也不显式存在的，也不会计入strlen()里。

## 4.字符串数组的拼接和复制

使用strcpy()和strcat()函数，但要提前处理好数组边界。

```C++
char str5[10] = {"Hello"};
char str6[3] = "Hi";
strcpy(str5,str6);  //合法
strcat(str5,str6);  //合法
strcpy(str6,str5);  //非法
strcat(str6,str5);  //非法
```

## 5.字符串比较

```C++
char str7[10] = "hello";
if(str7 == "hello"){  //该处会比较两字符串地址
    cout << "They are the same." << endl;
}
