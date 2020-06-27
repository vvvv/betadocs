# Conventions CodingStyle
For better readability and standardization of VVVV related code we should all conform to the coding styles below:  

## Casing
### Definitions

```
**Pascal Casing**  
 RedHotChilliPeppers
**Camel Casing**  
 redHotChilliPeppers
```

### Classes
* Pascal Casing  
```  
//good  
class RedHot  

//bad  
class TRedHot  
class redhot  

```  

### Interfaces
* start with an I (for Interface) and then Pascal Casing  
```  
//good  
interface IRedHot  

//bad  
interface RedHotInterface  
interface Iredhot  

```  

### Class Variables
* start with an F (for Field) and then Pascal Casing  
```  
//good  
int FChilliPepper  

//bad  
int ChilliPepper   
int FchilliPepper  

```  

### Local Variables, Function Arguments
* Camel Casing  
```  
//good  
int redPepper;  
void Foo(int barCode);  

//bad  
int Redpepper;  
int RedPepper;  
void Foo(int BarCode);  

```  

### Global Variables
* start with a G and then Pascal Casing  
```  
//good  
int GChilliPepper;  

//bad  
int ChilliPepperGlobal;  
int GchilliPepper;  

```

### Functions

* Pascal Casing  
```
//good  
PlayMusic();  

//bad  
playMusic();  

```

### Events

* start with On.. and then Pascal Casing  
```  
//good  
OnExplode  

//bad  
Explode  
Onexplode  

```  

### Events Callbacks
* are named like their corresponding Events  
* end with ..CB   
```  
//good  
ExplodeCB()  

//bad  
ExplosionCB()  
explodeCB()  

```  

## Braces
* braces are always in a new line  
```  
//good  
if true then  
{   
 ...
};  

//bad  
if true then { ... };  
if true then {  
   ...
 };

```  

## Indenting
* always use 4 spaces  

## Spacing
* there is always a single space after a comma or a semicolon, never before  
```  
//good  
MyFunction(a, b);  

//bad  
MyFunction( a , b );  

```  

* single spaces surround operators (except unary operators like increment or logical not)  
```  
//good  
a = b;                         
for (int i = 0; i < 10; ++i)   

//bad  
a=b;                               
for (int i=0; i<10; ++i)  

```  

## Other Coding Guidlines
Note that certain incompatibilities to the similar guides listed below (which differ among themselves aswell) are deliberate.  

<a href="http://www.mono-project.com/Coding_Guidelines" class="extURL" target="_blank">Mono Coding Guidlines</a>  

<a href="http://msdn.microsoft.com/en-us/library/ms229042.aspx" class="extURL" target="_blank">.Net Design Guidlines</a>  

<a href="http://www.icsharpcode.net/TechNotes/SharpDevelopCodingStyle03.pdf" class="extURL" target="_blank">Sharp Develop Coding Guidlines</a>  