---
title: Friend (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Friend
- friend_cpp
dev_langs:
- C++
helpviewer_keywords:
- member access, from friend functions
- friend classes
- friend keyword [C++]
ms.assetid: 8fe9ee55-d56f-40cd-9075-d9fb1375aff4
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 2d8dd1c80e9b006b3689b6d17ad9d7635670cc98
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="friend-c"></a>Friend (C++)
In einigen Fällen ist es einfacher auf Memberebene Zugriff auf Funktionen, die nicht Member einer Klasse sind, oder auf alle Elemente in einer separaten Klasse gewähren. Nur der Klassenimplementierer kann seine „Friends“ deklarieren. Eine Funkion oder Klasse kann sich nicht selbst als „Friend“ einer Klasse deklarieren. Verwenden Sie in einer Klassendefinition das `friend` -Schlüsselwort und den Namen der eine Memberfunktion oder einer anderen Klasse Zugriff auf die privaten und geschützten Member einer Klasse gewähren.         In der Vorlagendefinition eines kann ein Typparameter als einen "Friend" deklariert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class friend F  
friend F;  
```  
  
## <a name="friend-declarations"></a>Friend-Deklarationen  
 Wenn Sie eine Friend-Funktion deklarieren, die zuvor nicht deklariert wurde, wird diese Funktion in den einschließenden Nichtklassenbereich exportiert.  
  
 Die Funktionen, die in einer Friend-Deklaration deklariert sind, werden so behandelt, als ob sie mithilfe des `extern`-Schlüsselworts deklariert worden wären. (Weitere Informationen zu `extern`, finden Sie unter [statische Speicherklassenspezifizierer](http://msdn.microsoft.com/en-us/3ba9289a-a412-4a17-b319-ceb2c087df48).)  
  
 Obwohl Funktionen mit globalem Gültigkeitsbereich als Friends vor ihrem Prototypen deklariert werden können, können Memberfunktionen nicht als Friends vor der Darstellung ihrer vollständigen Klassendeklaration deklariert werden. Der folgende Code zeigt, warum hierbei ein Fehler auftritt:  
  
```cpp  
class ForwardDeclared;   // Class name is known.  
class HasFriends  
{  
    friend int ForwardDeclared::IsAFriend();   // C2039 error expected  
};  
```  
  
 Im vorhergehenden Beispiel wird der Klassenname `ForwardDeclared` in den Bereich eingegeben. Die vollständige Deklaration (besonders der Teil, in der die Funktion als `IsAFriend` deklariert wird) ist jedoch nicht bekannt. Daher wird von der `friend`-Deklaration in der Klasse `HasFriends` ein Fehler generiert.  
  
 Ab C ++ 11 können Sie zwei Formen von Friend-Deklarationen für eine Klasse stehen:  
  
```cpp  
friend class F;  
friend F;  
```  
  
 Die erste Form führt eine neue Klasse F auf, wenn keine vorhandenen Klasse mit diesem Namen in der innersten Namespace gefunden wurde.  **C ++ 11**: die zweite Form führt eine neue Klasse; es kann verwendet werden, wenn die Klasse bereits deklariert wurde und verwendet werden, muss Wenn Sie ein Vorlagentyp-Parameter oder eine Typdefinition als Friend zu deklarieren.  
  
 Verwendung `class friend F` Wenn referenzierten Typs nicht noch deklariert wurde:  
  
```cpp  
namespace NS  
{  
    class M  
    {  
        class friend F;  // Introduces F but doesn't define it  
    };  
}  
```  
  
```cpp  
namespace NS  
{  
    class M  
    {  
        friend F; // error C2433: 'NS::F': 'friend' not permitted on data declarations  
    };  
}  
```  
  
 Im folgenden Beispiel `friend F` bezieht sich auf die `F` -Klasse, die außerhalb des Bereichs der NS deklariert wird.  
  
```cpp  
class F {};  
namespace NS  
{  
    class M  
    {  
        friend F;  // OK   
    };  
}  
```  
  
 Verwendung `friend F` einen Vorlagenparameter als Friend zu deklarieren:  
  
```cpp  
template <typename T>  
class my_class  
{  
    friend T;  
    //...  
};  
```  
  
 Verwendung `friend F` Typedef als Friend zu deklarieren:  
  
```cpp  
class Foo {};  
typedef Foo F;  
  
class G  
{  
    friend F; // OK  
    friend class F // Error C2371 -- redefinition  
};  
```  
  
 Um zwei befreundete Klassen zu deklarieren, muss die gesamte zweite Klasse als Friend der ersten Klasse angegeben werden. Diese Einschränkung besteht, weil der Compiler über genügend Informationen verfügt, um einzelne Friend-Funktionen nur an der Stelle zu deklarieren, in der die zweite Klasse deklariert wird.  
  
> [!NOTE]
>  Obwohl die gesamte zweite Klasse Friend der ersten Klasse sein muss, können Sie auswählen, welche Funktionen in der ersten Klasse Friends der zweiten Klasse sind.  
  
## <a name="friend-functions"></a>friend-Funktionen  
 Eine `friend`-Funktion ist eine Funktion, die kein Member einer Klasse ist, jedoch Zugriff auf private und geschützte Member der Klasse hat. Friend-Funktionen gelten nicht als Klassenmember. Es sind normale externe Funktionen, denen spezielle Zugriffsrechte gewährt werden. Friends befinden sich nicht im Gültigkeitsbereich der Klasse, und sie werden nicht aufgerufen, mithilfe der memberauswahloperatoren (**.** "und" -**>**), wenn sie Mitglieder einer anderen Klasse sind. Eine `friend`-Funktion wird von der Klasse deklariert, die Zugriff gewährt. Die Deklaration `friend` kann überall in der Klassendeklaration platziert werden. Sie wird nicht durch die Schlüsselwörter der Zugriffssteuerung beeinflusst.  
  
 Das folgende Beispiel zeigt eine `Point`-Klasse und die Friend-Funktion `ChangePrivate`. Die Funktion `friend` hat Zugriff auf den privaten Datenmember des Objekts `Point`, welches es als Parameter erhält.  
  
```cpp  
// friend_functions.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class Point  
{  
    friend void ChangePrivate( Point & );  
public:  
    Point( void ) : m_i(0) {}  
    void PrintPrivate( void ){cout << m_i << endl; }  
  
private:  
    int m_i;  
};  
  
void ChangePrivate ( Point &i ) { i.m_i++; }  
  
int main()  
{  
   Point sPoint;  
   sPoint.PrintPrivate();  
   ChangePrivate(sPoint);  
   sPoint.PrintPrivate();  
// Output: 0  
           1  
}  
```  
  
## <a name="class-members-as-friends"></a>Klassenmember als „Friends“  
 Klassenmemberfunktionen können in anderen Klassen als "Friends" deklariert werden. Betrachten Sie das folgende Beispiel:  
  
```cpp  
// classes_as_friends1.cpp  
// compile with: /c  
class B;  
  
class A {  
public:  
   int Func1( B& b );  
  
private:  
   int Func2( B& b );  
};  
  
class B {  
private:  
   int _b;  
  
   // A::Func1 is a friend function to class B  
   // so A::Func1 has access to all members of B  
   friend int A::Func1( B& );  
};  
  
int A::Func1( B& b ) { return b._b; }   // OK  
int A::Func2( B& b ) { return b._b; }   // C2248  
```  
  
 Im vorherigen Beispiel wird nur der Funktion `A::Func1( B& )` Friend-Zugriff auf die `B`-Klasse gewährt. Daher kann der Zugriff auf den privaten Member `_b` richtig ist `Func1` Klasse `A` jedoch nicht in `Func2`.  
  
 Bei der `friend`-Klasse handelt es sich um eine Klasse, deren sämtliche Memberfunktionen Friend-Funktionen einer Klasse sind, d. h. deren Memberfunktionen Zugriff auf die privaten und geschützten Member der anderen Klasse haben. Angenommen, die `friend`-Deklaration in der `B`-Klasse lautete:  
  
```cpp  
friend class A;  
```  
  
 In diesem Fall wären allen Memberfunktionen in der `A`-Klasse Friend-Zugriff auf die `B`-Klasse gewährt worden. Der folgende Code ist ein Beispiel für eine Friend-Klasse:  
  
```cpp  
// classes_as_friends2.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class YourClass {  
friend class YourOtherClass;  // Declare a friend class  
public:  
   YourClass() : topSecret(0){}  
   void printMember() { cout << topSecret << endl; }  
private:  
   int topSecret;  
};  
  
class YourOtherClass {  
public:  
   void change( YourClass& yc, int x ){yc.topSecret = x;}  
};  
  
int main() {  
   YourClass yc1;  
   YourOtherClass yoc1;  
   yc1.printMember();  
   yoc1.change( yc1, 5 );  
   yc1.printMember();  
}  
```  
  
 Die Friendship-Klasse wurde nicht gegenseitig festgelegt, es sei denn, sie wurde explizit als solche angegeben. Im obigen Beispiel können Memberfunktionen von `YourClass` nicht auf die privaten Member von `YourOtherClass` zugreifen.  
  
 Ein verwalteter Typ darf keine Friend-Funktionen, Friend-Klassen oder Friend-Schnittstellen haben.  
  
 Die Friendship-Klasse wird nicht vererbt. Dies bedeutet, dass die von `YourOtherClass` abgeleiteten Klassen nicht auf die privaten Member von `YourClass` zugreifen können. Die Friendship-Klasse ist nicht transitiv. Daher können Klassen, die Friends von `YourOtherClass` sind, nicht auf die privaten Member von `YourClass` zugreifen.  
  
 Die folgende Abbildung zeigt vier Klassendeklarationen: `Base`, `Derived`, `aFriend` und `anotherFriend`. Nur die `aFriend`-Klasse hat direkten Zugriff auf die privaten Member der `Base`-Klassendeklaration (und auf alle Member, die `Base` möglicherweise geerbt hat).  
  
 ![Auswirkungen von Friend-Beziehungen](../cpp/media/vc38v41.gif "vc38V41")  
Auswirkungen von Friend-Beziehungen  
  
## <a name="inline-friend-definitions"></a>Inline-Friend-Definitionen  
 Friend-Funktionen können in Klassendeklarationen definiert werden. Diese Funktionen sind Inlinefunktionen und wie Memberinlinefunktionen verhalten sie sich, als wären sie sofort definiert worden, nachdem alle Klassenmember angezeigt wurden, jedoch bevor der Klassengültigkeitsbereich geschlossen wurde (Ende der Klassendeklaration).  
  
 Friend-Funktionen, die innerhalb von Klassendeklarationen definiert werden, gelten nicht als im Gültigkeitsbereich der einschließenden Klasse. Sie befinden sich im Dateigültigkeitsbereich.  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselwörter](../cpp/keywords-cpp.md)
