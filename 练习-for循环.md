## For循环练习

1.操场上100多人排队，三人一组多1人，四人一组多2人，五人一组多3人，共多少人？
```js
let x;
or(x=100;x<200;x++){
    if(x%3==1 && x%4==2 && x%5==3 ){
         document.write(`总共有${x}人<br>`)
     }
 }
```
>思路：问共有多少人？设共有x人，x的取值范围为[100,200),已知条件有：x%3=1,x%4=2,x%5=3  

2.甲、乙、丙、丁四人共加工零件370个，如果把甲做的个数加10个，乙做的个数减20个，丙做的个数乘以2，丁做的个数除以2，四人做的零件数正好相等，求甲实际加工了多少个零件 
```js
for(let a=1;a<=370;a++){
    if(a+(a+10+20)+(a+10)/2+(a+10)*2==370){
        document.write("甲实际加工了"+a+"个零件<br>")
    }
}
```
>思路：问甲实际加工了多少零件，设甲加工了a个零件，a的取值范围为[1,370)，已知条件有：甲+乙+丙+丁=370，甲+10=乙-20=丙*2=丁/2   

3.从1到500所有自然数中不含数字4的自然数共有多少个？
```js
let count=0;
for(let num=1;num<=500;num++){
    if(parseInt(num/100)!=4 && parseInt((num%100)/10)!=4 && num%10!=4){
        count++
    }
}
document.write("总共有：",count,"个<br>")
```
>思路：设num，num的取值范围为[1,500],条件：num的百位数，十位数，个位数都不是4  

4.两个自然数X，Y相除，商3余10，被除数、除数、商、余数的和是163，求被除数、除数。
```js
let x,y
for(let y=1;y<=163;y++){
    x=y*3+10;
    if(x+y+3+10==163){
        document.write("被除数："+x+"<br>")
        document.write("除数："+y+"<br>")
    }
}
``` 
>思路：求被除数和除数，设被除数为x，除数为y，已知条件：x=y*3+10，x+y+3+10=163  

5.某数学竞赛中，参赛人数大约在380~450人之间。比赛结果，全体考生的总平均分为76分，男生的平均分为75分，女生的平均分为80.1分，求男女生各有多少人？(328，80)
```js
let x,y;
for(x=1;x<=450;x++){
    for(y=1;y<=450;y++){
        if(380<=x+y && x+y<=450 && (x+y)*76==x*75+y*80.1){
            document.write("男生:"+x+"人<br>")
            document.write("女生:"+y+"人<br>")
        }
    }
}
```
>思路：设男生x人，女生y人。已知：380<=(x+y)<=450，(x+y)*76=x*75+y*80.1  

6.一个四位数，恰好等于去掉它的首位数字之后所剩的三位数的3倍，这个四位数是多少？(1500)
```js
let a
for(a=1000;a<=9999;a++){
    if(a==a%1000*3){
        document.write("四位数是："+a)
    }
}
```
>思路：设四位数为a，a的取值范围为[1000,9999]，a去掉它的首位数字之后所剩的三位数为a%1000，条件：a=(a%1000)*3

7.有一个两位数，如果在它的前面添一个3，可得到一个三位数；把3添在它的后面，也可以得到一个三位数。这两个三位数相差468，求原来的两位数。（85）
```js
let a,b,c
for(a=10;a<=99;a++){
    b=300+a;
    c=a*10+3;
    if(b-c==468 || c-b==468){
        document.write("原来的两位数是："+a)
    }
}
```

8.一个六位自然数，将其末位上数字7移至首位，其余数字依次向右移动一位，得到一个新的六位数，新的六位数是原六位数的4倍，求原数。 (179487)
```js
let x,y
for(x=100007;x<=999997;x+=10){
    y=(x-7)/10+700000
    if(y==x*4){
        document.write("原六位数："+x)
    }
}
```

9.要在[ ]、[ ]7、[ ]48这三个数中的每个[ ]内各填上1~9中的一个数字，使中间的两位数是左边的一位数和右边的三位数的平均数，求这三个数。（6、77、148）
```js
let a,b,c;
for(a=1;a<10;a++){
    for(b=1;b<10;b++){
        for(c=1;c<10;c++){
            if((a+c*100+48)/2==b*10+7){
                document.write(`这三个数分别为：${a},${b*10+7},${c*100+48}`)
            }
        }
    }
}
```

10.有红、白、黑三种球若干个，其中红、白球共25个，白、黑球共31个，红、黑球共28个，求这三种球各多少个？（11、14、17）
```js
let a
for(a=1;a<25;a++){
    if(25-a==31-(28-a)){
        document.write("红球:"+a+"个<br>")
        document.write("白球:"+(25-a)+"个<br>")
        document.write("黑球:"+(28-a)+"个<br>")
    }
}
```

11.某人去购买教材和练习簿。已知教材每本10元，教参每本5元，练习簿每本0.5元，他总共购买了100本，用了100元。问他购买教材、教参和练习簿各多少本？（1、9、90）
```js
let x,y,z;
for(x=1;x<10;x++){
    for(y=1;y<20;y++){
        for(z=1;z<200;z++){
            if(x+y+z==100 && x*10+y*5+z*0.5==100){
                document.write(`教材有${x}本，教参有${y}本，练习簿有${z}本`)
            }
        }
    }
}
```

12.输出四位自然数中各位数字之和为6并且各位数字互不相同的数，并统计个数。（1023、1032、1203、1230、1302、1320、……、3201、3210，18）
```js
let a,b,c,d,count=0
for(a=1;a<=9;a++){
    for(b=0;b<=9;b++){
        if(b==a){
            continue;
        }
        for(c=0;c<=9;c++){
            if(c==b || c==a){
                continue;
            }
            for(d=0;d<=9;d++){
                if(d==c || d==b || d==a){
                    continue;
                }
                if(a+b+c+d==6){
                    document.write(`${a*1000+b*100+c*10+d},`)
                    count++
                }
            }
        }
    }
}
document.write("<br>总共"+count+"个数")
```

13.由数字1、2、3、4、5、6六个数字共可组成多少个没有重复数字的四位数，输出这些数据并统计个数。（1234、1235、1236、1243、1245、1246、1253、……、6542、6543，S=360）
```js
let a,b,c,d,count=0;
for(a=1;a<=6;a++){
    for(b=1;b<=6;b++){
        if(b!=a){
            for(c=1;c<=6;c++){
                if(c!=b && c!=a){
                    for(d=1;d<=6;d++){
                        if(d!=c && d!=b && d!=a){
                            document.write((a*1000+b*100+c*10+d)+",")
                            count++
                        }
                    }
                }
            }
        }
    }
}
document.write("<br>总共"+count+"个数")
```

14.将100元纸币兑换成10元、5元和1元纸币共20张，输出各种兑换法，并统计个数。（4、11，5；8、2、10；S=2）
```js
let a,b,c,count=0;
for(a=1;a<10;a++){
    for(b=1;b<20;b++){
        c=20-a-b
        if(a*10+b*5+c*1==100){
            document.write(`10元纸币有${a}张，5元纸币有${b}张，1元纸币有${c}张<br>`)  
            count++
        }
    }
}
document.write("兑换方法共有"+count+"种")
```

15.打印“＊”字三角形：从键盘输入一个自然数Ｎ（１《Ｎ《 ９）。根据Ｎ的值，打印输出对应的“＊”字三角形。如Ｎ＝４，输出
```js
let num =prompt("请输入一个正整数","5") 
for(let i=1;i<=num;i++){
    for(let j=num-i;j>0;j--){
        document.write("&nbsp;")
    }
    for(let k=0;k<(2*i-1);k++){
        document.write("*")
    }
    document.write("<br>")
}
```

16.打印“＊”字三角形：从键盘输入一个自然数Ｎ（１《Ｎ《 ９）。根据Ｎ的值，打印输出对应的“＊”字三角形。如Ｎ＝４，输出
```js
let num = prompt("请输入一个正整数","5") 
for(let i=1;i<=2*num-1;i++){
    if(i<=num){
        for(let j=num-i;j>0;j--){
            document.write("&nbsp;")
        }
        for(let k=0;k<(2*i-1);k++){
            document.write("*")
        }
        document.write("<br>")
    }
    else{
        for(let j=i-num;j>0;j--){
            document.write("&nbsp;")
        }
        for(let k=0;k<(num-(i-num))*2-1;k++){
            document.write("*")
        }
        document.write("<br>")
    }
}
```

17.把16题中的菱形变为空心的
```js
let num = prompt("请输入一个正整数","5") 
for(let i=1;i<=2*num-1;i++){
    if(i<=num){
        for(let j=num-i;j>0;j--){
            document.write("&nbsp;")
        }
        for(let k=0;k<2*i-1;k++){
            if(k==0 || k==2*i-2){
                document.write("*")
            }
            document.write("&nbsp;")
        }
        document.write("<br>")
    }
    else{
        for(let j=i-num;j>0;j--){
            document.write("&nbsp;")
        }
        for(let k=0;k<(num-(i-num))*2-1;k++){
            if(k==0 || k==(num-(i-num)-1)*2-1){
                document.write("*")
            }
            document.write("&nbsp;")
        }
        document.write("<br>")
    }
}
```

九九乘法表
```js
for(let i=1;i<=9;i++){
    for(let j=1;j<=i;j++){
        document.write(`${j}*${i}=${j*i}&nbsp;&nbsp;`)
    }
    document.write("<br>")
}
```

猜数字游戏
```js
let num = parseInt(Math.random()*55+10)
while(true){
    let num2 =parseInt(prompt("请输入一个10-65之间的整数"))
    if(num2==num){
        alert("恭喜你，猜对了")
        break
    }else if(num2<num){
        alert("数字过小")
    }else{
        alert("数字过大")
    }
}
```

