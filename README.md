# c_study

const 和指针
const再前面 值不能变  const在后面 地址不能变

    //常量指针
    int a=5;
    const int *p=&a;
    //    *p=20; 错误的 不能通过指针修改指向的变量的值

    int b = 10;
    p=&b;


    //指向常量的指针 指针常量
    // 指针常量的值不能被修改 不能存一个新的地址
    //不能指向别的变量 但是可以通过指针修改他所指向的变量的值
    int c =5;
    int *const k=&a;
    *k=20;
    
    
    
    const 和函数
    如果给以“指针传递”方式的函数返回值加const修饰，那么函数返回值（即指针）的内容不能被修改，该返回值只能被赋给加const修饰的同类型指针。例如函数
const char * GetString(void);
如下语句将出现编译错误：
char *str = GetString();
正确的用法是
const char  *str =GetString();
如果函数返回值采用“值传递方式”，由于函数会把返回值复制到外部临时的存储单元中，加const修饰没有任何价值。
例如不要把函数int GetInt(void) 写成constint GetInt(void)。
同理不要把函数AGetA(void) 写成constA GetA(void)，其中A为用户自定义的数据类型。
如果返回值不是内部数据类型，将函数AGetA(void) 改写为constA &GetA(void)的确能提高效率。但此时千万千万要小心，一定要搞清楚函数究竟是想返回一个对象的“拷贝”还是仅返回“别名”就可以了，否则程序会出错。
函数返回值采用“引用传递”的场合并不多，这种方式一般只出现在类的赋值函数中，目的是为了实现链式表达

    函数后面加const
    表示函数不能修改该class 的成员变量
    比如class 里面有成员value   成员函数不能修改value
    
    
    const 和对象
    在 C++ 中，const 也可以用来修饰对象，称为常对象。一旦将对象定义为常对象之后，就只能调用类的 const 成员（包括 const 成员变量和 const 成员函数）了。
    
    
    
    
    
    -----------------------------------------------------------------------------
    static 
    static 修饰全局变量
    static int b= 10; //不能再其他文件中使用
    int a=10;  //可以再其他文件中使用 extern int a ;
    
    
    static修饰局部变量  只初始化一次 就相当于变成全局变量
    
    static修饰函数 和修饰全局变量差不多    如果没有static    其他文件extern int fun()；
    
