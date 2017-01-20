---
title: "protected (C++)"
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
  - "protected"
  - "protected_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "protected-Schlüsselwort [C++]"
  - "protected-Schlüsselwort [C++], Memberzugriff"
ms.assetid: 863d299f-fc0d-45d5-a1a7-bd24b7778a93
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# protected (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
protected:  
   [member-list]  
protected base-class  
```  
  
## Hinweise  
 Das `protected`\-Schlüsselwort spezifiziert den Zugriff auf Klassenmember in der *Memberliste* bis zum nächsten Zugriffsspezifizierer \(**public** oder `private`\) oder bis zum Ende der Klassendefinition.  Klassenmember, die als `protected` deklariert werden, können nur mit folgenden Möglichkeiten verwendet werden:  
  
-   Memberfunktionen der Klasse, die ursprünglich diese Member deklariert hat.  
  
-   Friends der Klasse, die ursprünglich diese Member deklariert hat.  
  
-   Klassen, die mit öffentlichem oder geschütztem Zugriff von der Klasse abgeleitet werden, die ursprünglich diese Member deklariert hat.  
  
-   Direkt privat abgeleitete Klassen, die auch über privaten Zugriff auf geschützte Member verfügen.  
  
 Wenn das `protected`\-Schlüsselwort dem Namen einer Basisklasse vorangestellt ist, gibt es an, dass die öffentlichen und geschützten Member der Basisklasse geschützte Member der abgeleiteten Klassen sind.  
  
 Geschützte Member sind nicht so privat wie `private`\-Member, die nur für Member der Klasse zugänglich sind, in der sie deklariert werden. Sie sind jedoch nicht so öffentlich wie **public**\-Member, die in jeder Funktion zugänglich sind.  
  
 Geschützte Member, die auch als **static** deklariert werden, sind für alle Friend\- oder Memberfunktionen einer abgeleiteten Klasse zugänglich.  Geschützte Member, die nicht als **static** deklariert werden, sind für Friends\- und Memberfunktionen in einer abgeleiteten Klasse nur über einen Zeiger\/Verweis auf die abgeleitete Klasse bzw. über ein Objekt derselben zugänglich.  
  
 Weitere Informationen finden Sie unter [friend](../cpp/friend-cpp.md), [public](../cpp/public-cpp.md) und [private](../cpp/private-cpp.md) sowie in der Memberzugriffstabelle unter [Steuern des Zugriffs auf Klassenmember](../misc/controlling-access-to-class-members.md).  
  
## "\/clr"\-spezifisch  
 In CLR\-Typen können die C\+\+\-Schlüsselwörter für Zugriffsspezifizierer \(**public**, `private` und `protected`\) die Sichtbarkeit von Typen und Methoden hinsichtlich der Assemblys beeinträchtigen.  Weitere Informationen finden Sie unter [Typ\- und Membersichtbarkeit](../misc/type-and-member-visibility.md).  
  
> [!NOTE]
>  Dateien, die mit [\/LN](../build/reference/ln-create-msil-module.md) kompiliert werden, werden durch dieses Verhalten nicht beeinflusst.  In diesem Fall werden alle verwalteten Klassen \(entweder "public" oder "private"\) angezeigt.  
  
## "\/clr"\-spezifisch – Ende  
  
## Beispiel  
  
```  
// keyword_protected.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class X {  
public:  
   void setProtMemb( int i ) { m_protMemb = i; }  
   void Display() { cout << m_protMemb << endl; }  
protected:  
   int  m_protMemb;  
   void Protfunc() { cout << "\nAccess allowed\n"; }  
} x;  
  
class Y : public X {  
public:  
   void useProtfunc() { Protfunc(); }  
} y;  
  
int main() {  
   // x.m_protMemb;         error, m_protMemb is protected  
   x.setProtMemb( 0 );   // OK, uses public access function  
   x.Display();  
   y.setProtMemb( 5 );   // OK, uses public access function  
   y.Display();  
   // x.Protfunc();         error, Protfunc() is protected  
   y.useProtfunc();      // OK, uses public access function  
                        // in derived class  
}  
```  
  
## Siehe auch  
 [Steuern des Zugriffs auf Klassenmember](../misc/controlling-access-to-class-members.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)