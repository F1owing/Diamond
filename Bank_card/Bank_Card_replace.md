# 银行卡某些数字替换为“*”

## 功能：输入一个字符串，如果符以下条件：

#### 		>/这个字符串中含有“621226"的连续字符串段

#### 		>/"621226"后接13位数字

## 	则会将“621226”后面的四个数字将会被替换为“*”

### 样例输入1：

sadkfheiuws6312260502005983197

### 样例输出1：

sadkfheiuws6312260502005983197

### 样例输入2：

adszfvad6212260502005983197

### 样例输出2：

adszfvad621226\****005983197

## Java代码：

/*

- This is a ez program to match bankcard number and replace some bit by "*“. 
- Remarks: This program just match one of ICBC's cards. */
  package com.bank_card_match;

import java.util.Scanner;

public class B_C_Match
{

```
private String str;
```

```
B_C_Match(String num)
{
	this.str = num;
}

String replace()
{
	if(str.matches(".*621226\\d{13}.*"))
		str = str.replaceAll("621226\\d{4}", "621226****");
	return str; 
}
public static void main(String args[])
{
	String num;
	Scanner sc = new Scanner(System.in);
	num = sc.nextLine();
	sc.close();
	B_C_Match b = new B_C_Match(num);
	System.out.println(b.replace());
}
```

}