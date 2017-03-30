---
---
# <a name="compiler-warning-level-1-c4055"></a>Compilerwarnung (Stufe 1) C4055  
  
'Konvertierung': Von Datenzeiger 'Typ1' zu Funktionszeiger 'Typ2'.  
  
**Veraltet:** diese Warnung wird von Visual Studio 2017 und neueren Versionen nicht generiert.

 Ein Datenzeiger wird (möglicherweise falsch) in einen Funktionszeiger umgewandelt. Dies ist unter „/Za“ eine Warnung der Stufe 1 und unter „/Ze“ eine Warnung der Stufe 4.  
  
 Im folgenden Beispiel wird C4055 generiert:  
  
```C  
// C4055.c  
// compile with: /Za /W1 /c  
typedef int (*PFUNC)();  
int *pi;  
PFUNC f() {  
   return (PFUNC)pi;   // C4055  
}  
```  
  
 Unter „/Ze“ ist dies eine Warnung der Stufe 4.  
  
```C  
// C4055b.c  
// compile with: /W4 /c  
typedef int (*PFUNC)();  
int *pi;  
PFUNC f() {  
return (PFUNC)pi;   // C4055  
}  
```