---
title: "Operatoren für den Memberzugriff:. \"und\" -&gt; | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- .
- ->
dev_langs:
- C++
helpviewer_keywords:
- member access, expressions
- operators [C++], member access
- dot operator (.)
- -> operator
- member access, operators
- postfix operators [C++]
- . operator
- member access
ms.assetid: f8fc3df9-d728-40c5-b384-276927f5f1b3
caps.latest.revision: 11
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
ms.openlocfilehash: 7c4e69727c474cb89f931832da2dbde6e20c16b9
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="member-access-operators--and--gt"></a>Operatoren für den Memberzugriff:. "und" -&gt;
## <a name="syntax"></a>Syntax  
  
```  
postfix-expression . name  
postfix-expression -> name  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Operatoren für den Memberzugriff **.** und ** -> ** werden verwendet, um auf Member von Strukturen, Unions und Klassen verweisen. Memberzugriffsausdrücke haben den Wert und Typ des ausgewählten Members.  
  
 Es gibt zwei Arten von Memberzugriffsausdrücken:  
  
1.  In der ersten Form stellt *postfixausdruck* stellt einen Wert von der Struktur, Klasse oder union-Typ und *Namen* Namen eines Members der angegebenen Struktur, Union oder Klasse. Der Wert des Vorgangs ist der *Namen* und ist ein l-Wert, wenn *postfixausdruck* ist ein l-Wert.  
  
2.  In der zweiten Form *postfixausdruck* stellt einen Zeiger auf eine Struktur, Union oder Klasse, und *Namen* Namen eines Members der angegebenen Struktur, Union oder Klasse. Der Wert ist der *Namen* und ist ein l-Wert. Die ** -> ** Operator dereferenziert den Zeiger. Daher sind die Begriffe *e* ** -> ** `member` und **(\****e***)**.`member` (, in denen *e* stellt einen Zeiger) identische Ergebnisse ergeben (Ausnahme: Wenn die Operatoren ** -> ** oder ** \* ** überladen werden).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden beide Formen des Memberzugriffsoperators dargestellt.  
  
```  
// expre_Selection_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
struct Date {  
   Date(int i, int j, int k) : day(i), month(j), year(k){}  
   int month;  
   int day;  
   int year;  
};  
  
int main() {  
   Date mydate(1,1,1900);  
   mydate.month = 2;     
   cout  << mydate.month << "/" << mydate.day  
         << "/" << mydate.year << endl;  
  
   Date *mydate2 = new Date(1,1,2000);  
   mydate2->month = 2;  
   cout  << mydate2->month << "/" << mydate2->day  
         << "/" << mydate2->year << endl;  
   delete mydate2;  
}  
```  
  
```Output  
2/1/1900  
2/1/2000  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Postfixausdrücke](../cpp/postfix-expressions.md)   
 [Integrierte C++-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Klassen und Strukturen](../cpp/classes-and-structs-cpp.md)   
 [Struktur- und Unionmember](../c-language/structure-and-union-members.md)
