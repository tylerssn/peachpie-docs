## Structure of generated assembly

The compiler outputs portable class libraries or executables compatible with .NET 4.5, Mono and .NET Core.

* ![](/img/icon_ns.png) *namespace* -
    * ![](/img/icon_class.png) *class* &lt;Script&gt;
        * ![](/img/icon_method.png) Main(string[] *args*) : int
* ![](/img/icon_ns.png) *namespace* **NS1**
    * ![](/img/icon_class.png) *class* **Class1**
* ![](/img/icon_ns.png) *namespace* &lt;Root&gt;
    * ![](/img/icon_class.png) `[Script("file1.php")]` static *class* **file1_php**
        * ![](/img/icon_method.png) &lt;Main&gt;(Context *&lt;ctx&gt;*, PhpArray *&lt;locals&gt;*, object *this*, RuntimeTypeHandle *self*) : T
        * ![](/img/icon_method.png) **function1**(Context *&lt;ctx&gt;*, ...) : T

> Declarations are compiled into the assembly as depicted above.

> - Script files (**file1.php**) are represented by the respective class in namespace &lt;Root&gt;. The script body is represented by the static method &lt;Main&gt;.

> - Global functions (**function1**) are compiled as static methods in their script file class. Conditionally declared functions contain a suffix.

> - Classes and interfaces (**class1**) are compiled into the same structure as defined.
