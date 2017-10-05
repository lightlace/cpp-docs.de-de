---
title: Protected (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- protected
- protected_cpp
dev_langs:
- C++
helpviewer_keywords:
- protected keyword [C++], member access
- protected keyword [C++]
ms.assetid: 863d299f-fc0d-45d5-a1a7-bd24b7778a93
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
ms.openlocfilehash: b65c73c7ecc3419f4a2a40e4bf693049226bd8b7
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="protected-c"></a>protected (C++)
## <a name="syntax"></a>Syntax  
  
```  
protected:  
   [member-list]  
protected base-class  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `protected` -Schlüsselwort spezifiziert den Zugriff auf Member der Klasse in der *Memberliste* bis zum nächsten Zugriffsspezifizierer (**öffentlichen** oder `private`) oder am Ende der Klassendefinition. Klassenmember, die als `protected` deklariert werden, können nur mit folgenden Möglichkeiten verwendet werden:  
  
-   Memberfunktionen der Klasse, die ursprünglich diese Member deklariert hat.  
  
-   Friends der Klasse, die ursprünglich diese Member deklariert hat.  
  
-   Klassen, die mit öffentlichem oder geschütztem Zugriff von der Klasse abgeleitet werden, die ursprünglich diese Member deklariert hat.  
  
-   Direkt privat abgeleitete Klassen, die auch über privaten Zugriff auf geschützte Member verfügen.  
  
 Wenn das `protected`-Schlüsselwort dem Namen einer Basisklasse vorangestellt ist, gibt es an, dass die öffentlichen und geschützten Member der Basisklasse geschützte Member der abgeleiteten Klassen sind.  
  
 Geschützte Member sind nicht so privat wie `private` Elemente, bei denen nur für Member der Klasse zugegriffen werden, in dem sie deklariert werden, aber sie sind nicht so öffentlich wie **öffentlichen** Elemente, bei denen in jeder Funktion zugänglich sind.  
  
 Geschützte Member, die auch als deklariert werden **statische** für alle Funktionen Friend- oder Memberfunktionen einer abgeleiteten Klasse zugegriffen werden. Geschützte Member, die als nicht deklariert werden **statische** sind für Friends- und Memberfunktionen in einer abgeleiteten Klasse nur über einen Zeiger / Verweis oder Objekt der abgeleiteten Klasse zugegriffen werden kann.  
  
 Weitere Informationen finden Sie unter ["Friend"](../cpp/friend-cpp.md), [öffentlichen](../cpp/public-cpp.md), [private](../cpp/private-cpp.md), und der memberzugriffstabelle in [Steuern des Zugriffs auf Klassenmember](member-access-control-cpp.md) .  
  
## <a name="clr-specific"></a>"/clr"-spezifisch  
 In CLR-Typen, die C++ Schlüsselwörter für Zugriffsspezifizierer zugreifen (**öffentlichen**, `private`, und `protected`) kann die Sichtbarkeit von Typen und Methoden hinsichtlich der Assemblys beeinträchtigen. Weitere Informationen finden Sie unter [Memberzugriffssteuerung](member-access-control-cpp.md).  
  
> [!NOTE]
>  Dateien mit kompiliert [/ln](../build/reference/ln-create-msil-module.md) nicht durch dieses Verhalten beeinträchtigt werden. In diesem Fall werden alle verwalteten Klassen (entweder "public" oder "private") angezeigt.  
  
## <a name="end-clr-specific"></a>"/clr"-spezifisch – Ende  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Steuern des Zugriffs auf Klassenmember](member-access-control-cpp.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)
