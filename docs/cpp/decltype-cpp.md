---
title: "\"decltype\" (C++) | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- decltype_cpp
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], decltype
- decltype operator
- operators [C++], type of an expression
- operators [C++], deduce expression type
ms.assetid: 6dcf8888-8196-4f13-af50-51e3797255d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac9fe7ebf3d3e406854308e56d38e37567acc07a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418038"
---
# <a name="decltype--c"></a>"decltype" (C++)
Der `decltype`-Typspezifizierer ergibt den Typ eines angegebenen Ausdrucks. Die `decltype` Typspezifizierer verwenden, zusammen mit den [auto-Schlüsselwort](../cpp/auto-cpp.md), eignet sich vor allem für Entwickler, die Vorlagenbibliotheken schreiben. Verwenden Sie `auto` und `decltype`, um eine Vorlagenfunktion zu deklarieren, deren Rückgabetyp von den Typen seiner Vorlagenargumente abhängt. Oder Sie verwenden `auto` und `decltype`, um eine Vorlagenfunktion zu deklarieren, die einen Aufruf einer anderen Funktion umschließt und anschließend den Rückgabetyp der umschlossenen Funktion zurückgibt.  
  
## <a name="syntax"></a>Syntax  
  
```  
decltype( expression )  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`expression`|Ein Ausdruck. Weitere Informationen finden Sie unter [Ausdrücke](../cpp/expressions-cpp.md).|  
  
## <a name="return-value"></a>Rückgabewert  
 Der Typ des `expression`-Parameters.  
  
## <a name="remarks"></a>Hinweise  
 Der Typspezifizierer `decltype` wird in Visual C++ 2010 oder höher unterstützt und kann mit systemeigenem oder verwaltetem Code verwendet werden. `decltype(auto)` (C++14) wird in Visual Studio 2015 und höher unterstützt.  
  
 Der Compiler bestimmt mithilfe der folgenden Regeln den Typ des `expression`-Parameters.  
  
-   Wenn die `expression` -Parameter ist ein Bezeichner oder ein [-Klasse Memberzugriff](../cpp/member-access-operators-dot-and.md), `decltype(expression)` ist der Typ der Entität mit dem Namen von `expression`. Wenn keine solche Entität vorhanden ist oder der `expression`-Parameter einen Satz überladener Funktionen bezeichnet, erzeugt der Compiler eine Fehlermeldung.  
  
-   Wenn die `expression` Parameter ist ein Aufruf einer Funktion oder überladenen Operatorfunktion ist, `decltype(expression)` ist der Rückgabetyp der Funktion. Klammern um einen überladenen Operator werden ignoriert.  
  
-   Wenn die `expression` Parameter ist ein [Rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md), `decltype(expression)` ist der Typ des `expression`. Wenn die `expression` Parameter ist ein [Lvalue](../cpp/lvalues-and-rvalues-visual-cpp.md), `decltype(expression)` ist ein [Lvalue-Verweis](../cpp/lvalue-reference-declarator-amp.md) in den Typ des `expression`.  
  
 Im folgenden Codebeispiel werden einige Verwendungsmöglichkeiten des `decltype`-Typspezifizierers veranschaulicht. Angenommen, Sie haben die folgenden Anweisungen codiert.  
  
```cpp  
int var;  
const int&& fx();   
struct A { double x; }  
const A* a = new A();  
```  
  
 Überprüfen Sie als Nächstes die Typen, die von den vier `decltype`-Anweisungen in der folgenden Tabelle zurückgegeben werden.  
  
|Anweisung|Typ|Hinweise|  
|---------------|----------|-----------|  
|`decltype(fx());`|`const int&&`|Ein [Rvalue-Verweis](../cpp/rvalue-reference-declarator-amp-amp.md) zu einem `const int`.|  
|`decltype(var);`|`int`|Der Typ der `var`-Variablen.|  
|`decltype(a->x);`|`double`|Der Typ des Memberzugriffs.|  
|`decltype((a->x));`|`const double&`|Die innere Klammer bewirkt, dass die Anweisung als Ausdruck anstatt als Memberzugriff ausgewertet wird. Und da `a` als `const`-Zeiger deklariert ist, ist der Typ ein Verweis auf `const double`.|  
  
## <a name="decltype-and-auto"></a>"decltype" und "auto"  
 In C ++ 14 können Sie `decltype(auto)` ohne nachstehenden Rückgabetyp um eine Vorlagenfunktion zu deklarieren, deren Rückgabetyp hängt von den Typen seiner Vorlagenargumente.  
  
 In C++11 können Sie den `decltype`-Typspezifizierer für einen nachstehenden Rückgabetyp in Kombination mit dem `auto`-Schlüsselwort verwenden, um eine Vorlagenfunktion zu deklarieren, deren Rückgabetyp von den Typen der dazugehörigen Vorlagenargumente abhängt. Betrachten Sie das folgende Codebeispiel, in dem der Rückgabetyp der Vorlagenfunktion von den Typen der Vorlagenargumente abhängt. Im Codebeispiel wird die *unbekannte* Platzhalter gibt an, dass der Rückgabetyp angegeben werden kann.  
  
```cpp  
template<typename T, typename U>  
UNKNOWN func(T&& t, U&& u){ return t + u; };   
```  
  
 Die Einführung des `decltype`-Typspezifizierers ermöglicht es den Entwicklern, den Typ des Ausdrucks zu erhalten, den die Vorlagenfunktion zurückgibt. Verwenden der *alternative funktionsdeklarationssyntax* , die später angezeigt wird, die `auto` -Schlüsselwort, und die `decltype` Typspezifizierer deklariert eine *spät angegebenen* Typ zurückgeben. Der spät angegebene Rückgabetyp wird bestimmt, wenn die Deklaration kompiliert wird, anstatt wenn sie codiert wird.  
  
 Der folgende Prototyp veranschaulicht die Syntax einer alternativen Funktionsdeklaration. Beachten Sie, dass die `const` und `volatile` Qualifizierer, und die `throw` [Ausnahmespezifikation](../cpp/exception-specifications-throw-cpp.md) sind optional. Die *Function_body* Platzhalter darstellt, eine verbundanweisung, der Wirkungsweise der Funktion angibt. Als empfohlene Vorgehensweise bei der Codierung der *Ausdruck* Platzhalter in der `decltype` Anweisung übereinstimmen, indem der angegebene Ausdruck der `return` -Anweisung, falls vorhanden, in der *Function_body*.  
  
 **automatische** *Function_name* **(** *Parameter*<sub>opt</sub> **)**  **const**<sub>opt</sub> **volatile**<sub>opt</sub> **->** **"decltype" (** *Ausdruck* **)** **auslösen**<sub>opt</sub> **{** *Function_body* **};**  
  
 Im folgenden Codebeispiel wird der spät angegebene Rückgabetyp der `myFunc`-Vorlagenfunktion von den Typen der `t`- und `u`-Vorlagenargumente bestimmt. Als empfohlene Vorgehensweise bei der Codierung, verwendet das Codebeispiel auch Rvalue-Verweise und die `forward` -Funktionsvorlage, die Unterstützung von *eine perfekte Weiterleitung*. Weitere Informationen finden Sie unter [RValue-Verweisdeklarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
```cpp  
//C++11  
 template<typename T, typename U>  
auto myFunc(T&& t, U&& u) -> decltype (forward<T>(t) + forward<U>(u))   
        { return forward<T>(t) + forward<U>(u); };  
  
//C++14  
template<typename T, typename U>  
decltype(auto) myFunc(T&& t, U&& u)   
        { return forward<T>(t) + forward<U>(u); };  
  
```  
  
## <a name="decltype-and-forwarding-functions-c11"></a>„decltyp“ und Weiterleitungsfunktionen (C++11)  
 Weiterleitungsfunktionen umschließen Aufrufe von anderen Funktionen. Denken Sie an eine Funktionsvorlage, die ihre Argumente oder die Ergebnisse eines Ausdrucks, der diese Argumente beinhaltet, an eine andere Funktion weiterleitet. Darüber hinaus gibt die Weiterleitungsfunktion das Ergebnis des Aufrufs der anderen Funktion zurück. In diesem Szenario muss der Rückgabetyp der Weiterleitungsfunktion mit dem Rückgabetyp der umschlossenen Funktion identisch sein.  
  
 Sie können in diesem Szenario keinen geeigneten Typausdruck ohne den `decltype`-Typspezifizierer schreiben. Der `decltype`-Typspezifizierer aktiviert generische Weiterleitungsfunktionen, denn er verliert keine erforderlichen Informationen darüber, ob eine Funktion einen Verweistyp zurückgibt. Ein Codebeispiel für eine Weiterleitungsfunktion finden Sie im vorherigen `myFunc`-Vorlagenfunktionsbeispiel.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird der spät angegebene Rückgabetyp der `Plus()`-Vorlagenfunktion deklariert. Die `Plus`-Funktion verarbeitet ihre beiden Operanden mit der `operator+`-Überladung. Demzufolge hängen die Interpretation des Plus-Operators (+) und der Rückgabetyp der `Plus`-Funktion von den Typen der Funktionsargumente ab.  
  
```cpp  
// decltype_1.cpp  
// compile with: cl /EHsc decltype_1.cpp  
  
#include <iostream>  
#include <string>  
#include <utility>  
#include <iomanip>  
  
using namespace std;  
  
template<typename T1, typename T2>  
auto Plus(T1&& t1, T2&& t2) ->   
   decltype(forward<T1>(t1) + forward<T2>(t2))  
{  
   return forward<T1>(t1) + forward<T2>(t2);  
}  
  
class X  
{  
   friend X operator+(const X& x1, const X& x2)  
   {  
      return X(x1.m_data + x2.m_data);  
   }  
  
public:  
   X(int data) : m_data(data) {}  
   int Dump() const { return m_data;}  
private:  
   int m_data;  
};  
  
int main()  
{  
   // Integer   
   int i = 4;  
   cout <<   
      "Plus(i, 9) = " <<   
      Plus(i, 9) << endl;  
  
   // Floating point  
   float dx = 4.0;  
   float dy = 9.5;  
   cout <<     
      setprecision(3) <<   
      "Plus(dx, dy) = " <<  
      Plus(dx, dy) << endl;  
  
   // String        
   string hello = "Hello, ";  
   string world = "world!";  
   cout << Plus(hello, world) << endl;  
  
   // Custom type  
   X x1(20);  
   X x2(22);  
   X x3 = Plus(x1, x2);  
   cout <<   
      "x3.Dump() = " <<   
      x3.Dump() << endl;  
}  
```  
  
```Output  
Plus(i, 9) = 13
Plus(dx, dy) = 13.5
Hello, world!
x3.Dump() = 42
```
  
## <a name="example"></a>Beispiel
**Visual Studio 2017 und höher:** der Compiler analysiert "decltype" Argumente auf, wenn die Vorlagen deklariert, aber nicht instanziiert. Wenn eine unabhängige Spezialisierung im decltype-Argument gefunden wird, wird sie nicht zum Zeitpunkt der Instanziierung zurückgestellt werden. Sie wird sofort verarbeitet, und alle resultierenden Fehler können zu diesem Zeitpunkt untersucht werden.

Das folgende Beispiel zeigt einen solchen Compilerfehler, der zum Zeitpunkt der Deklaration ausgelöst wird:

```cpp
#include <utility>
template <class T, class ReturnT, class... ArgsT> class IsCallable
{
public:
   struct BadType {};
   template <class U>
   static decltype(std::declval<T>()(std::declval<ArgsT>()...)) Test(int); //C2064. Should be declval<U>
   template <class U>
   static BadType Test(...);
   static constexpr bool value = std::is_convertible<decltype(Test<T>(0)), ReturnT>::value;
};

constexpr bool test1 = IsCallable<int(), int>::value;
static_assert(test1, "PASS1");
constexpr bool test2 = !IsCallable<int*, int>::value;
static_assert(test2, "PASS2");
```

## <a name="requirements"></a>Anforderungen  
 Visual C++ 2010 oder höhere Versionen  
  
 `decltype(auto)` erfordert Visual Studio 2015 oder höher.  
  
