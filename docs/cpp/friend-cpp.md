---
title: "Friend (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "Friend"
  - "friend_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "friend-Klassen"
  - "friend-Schlüsselwort [C++]"
  - "Memberzugriff, Von friend-Funktionen"
ms.assetid: 8fe9ee55-d56f-40cd-9075-d9fb1375aff4
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Friend (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unter bestimmten Umständen ist es einfacher, Zugriff auf Funktionen, die nicht Member einer Klasse sind, oder auf alle Funktionen in einer separaten Klasse auf Memberebene zu gewähren.  Nur der Klassenimplementierer kann seine „Friends“ deklarieren.  Eine Funkion oder Klasse kann sich nicht selbst als „Friend“ einer Klasse deklarieren.  Mit dem `friend`\-Schlüsselwort können Sie einer Funktion oder einer Klasse Zugriff auf die privaten und geschützten Member einer Klasse gewähren.  
  
## Syntax  
  
```  
  
        friend class-name;  
friend function-declarator;  
```  
  
## Friend\-Deklarationen  
 Wenn Sie eine Friend\-Funktion deklarieren, die zuvor nicht deklariert wurde, wird diese Funktion in den einschließenden Nichtklassenbereich exportiert.  
  
 Die Funktionen, die in einer Friend\-Deklaration deklariert sind, werden so behandelt, als ob sie mithilfe des `extern`\-Schlüsselworts deklariert worden wären.  \(Weitere Informationen zu `extern` finden Sie im Artikel über [statische Speicherklassenspezifizierer](assetId:///3ba9289a-a412-4a17-b319-ceb2c087df48)\).  
  
 Obwohl Funktionen mit globalem Gültigkeitsbereich als Friends vor ihrem Prototypen deklariert werden können, können Memberfunktionen nicht als Friends vor der Darstellung ihrer vollständigen Klassendeklaration deklariert werden.  Der folgende Code zeigt, warum hierbei ein Fehler auftritt:  
  
```  
class ForwardDeclared;   // Class name is known.  
class HasFriends  
{  
    friend int ForwardDeclared::IsAFriend();   // C2039 error expected  
};  
```  
  
 Im vorhergehenden Beispiel wird der Klassenname `ForwardDeclared` in den Bereich eingegeben. Die vollständige Deklaration \(besonders der Teil, in der die Funktion als `IsAFriend` deklariert wird\) ist jedoch nicht bekannt.  Daher wird von der `friend`\-Deklaration in der Klasse `HasFriends` ein Fehler generiert.  
  
 Um zwei befreundete Klassen zu deklarieren, muss die gesamte zweite Klasse als Friend der ersten Klasse angegeben werden.  Diese Einschränkung besteht, weil der Compiler über genügend Informationen verfügt, um einzelne Friend\-Funktionen nur an der Stelle zu deklarieren, in der die zweite Klasse deklariert wird.  
  
> [!NOTE]
>  Obwohl die gesamte zweite Klasse Friend der ersten Klasse sein muss, können Sie auswählen, welche Funktionen in der ersten Klasse Friends der zweiten Klasse sind.  
  
## friend\-Funktionen  
 Eine `friend`\-Funktion ist eine Funktion, die kein Member einer Klasse ist, jedoch Zugriff auf private und geschützte Member der Klasse hat.  Friend\-Funktionen gelten nicht als Klassenmember. Es sind normale externe Funktionen, denen spezielle Zugriffsrechte gewährt werden.  Friends befinden sich nicht im gültigen Bereich der Klasse und werden nicht mit Memberauswahloperatoren aufgerufen \(**.** und –**\>**\), außer sie sind Member einer anderen Klasse.  Eine `friend`\-Funktion wird von der Klasse deklariert, die Zugriff gewährt.  Die Deklaration `friend` kann überall in der Klassendeklaration platziert werden.  Sie wird nicht durch die Schlüsselwörter der Zugriffssteuerung beeinflusst.  
  
 Das folgende Beispiel zeigt eine `Point`\-Klasse und die Friend\-Funktion `ChangePrivate`.  Die Funktion `friend` hat Zugriff auf den privaten Datenmember des Objekts `Point`, welches es als Parameter erhält.  
  
```  
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
  
## Klassenmember als „Friends“  
 Klassenmemberfunktionen können in anderen Klassen als "Friends" deklariert werden.  Betrachten Sie das folgende Beispiel:  
  
```  
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
  
 Im vorherigen Beispiel wird nur der Funktion `A::Func1( B& )` Friend\-Zugriff auf die `B`\-Klasse gewährt.  Daher ist der Zugriff auf den privaten Member `_b` in `Func1` der Klasse `A` richtig, jedoch nicht in `Func2`.  
  
 Bei der `friend`\-Klasse handelt es sich um eine Klasse, deren sämtliche Memberfunktionen Friend\-Funktionen einer Klasse sind, d. h. deren Memberfunktionen Zugriff auf die privaten und geschützten Member der anderen Klasse haben.  Angenommen, die `friend`\-Deklaration in der `B`\-Klasse lautete:  
  
```  
friend class A;  
```  
  
 In diesem Fall wären allen Memberfunktionen in der `A`\-Klasse Friend\-Zugriff auf die `B`\-Klasse gewährt worden.  Der folgende Code ist ein Beispiel für eine Friend\-Klasse:  
  
```  
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
  
 Die Friendship\-Klasse wurde nicht gegenseitig festgelegt, es sei denn, sie wurde explizit als solche angegeben.  Im obigen Beispiel können Memberfunktionen von `YourClass` nicht auf die privaten Member von `YourOtherClass` zugreifen.  
  
 Ein verwalteter Typ darf keine Friend\-Funktionen, Friend\-Klassen oder Friend\-Schnittstellen haben.  
  
 Die Friendship\-Klasse wird nicht vererbt. Dies bedeutet, dass die von `YourOtherClass` abgeleiteten Klassen nicht auf die privaten Member von `YourClass` zugreifen können.  Die Friendship\-Klasse ist nicht transitiv. Daher können Klassen, die Friends von `YourOtherClass` sind, nicht auf die privaten Member von `YourClass` zugreifen.  
  
 Die folgende Abbildung zeigt vier Klassendeklarationen: `Base`, `Derived`, `aFriend` und `anotherFriend`.  Nur die `aFriend`\-Klasse hat direkten Zugriff auf die privaten Member der `Base`\-Klassendeklaration \(und auf alle Member, die `Base` möglicherweise geerbt hat\).  
  
 ![Auswirkungen von Friend&#45;Beziehungen](../cpp/media/vc38v41.png "vc38V41")  
Auswirkungen von Friend\-Beziehungen  
  
## Inline\-Friend\-Definitionen  
 Friend\-Funktionen können in Klassendeklarationen definiert werden.  Diese Funktionen sind Inlinefunktionen und wie Memberinlinefunktionen verhalten sie sich, als wären sie sofort definiert worden, nachdem alle Klassenmember angezeigt wurden, jedoch bevor der Klassengültigkeitsbereich geschlossen wurde \(Ende der Klassendeklaration\).  
  
 Friend\-Funktionen, die innerhalb von Klassendeklarationen definiert werden, gelten nicht als im Gültigkeitsbereich der einschließenden Klasse. Sie befinden sich im Dateigültigkeitsbereich.  
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)