---
title: __if_exists-Anweisung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __if_exists_cpp
dev_langs:
- C++
helpviewer_keywords:
- identifiers, testing for existence
- symbols, testing for existence
- __if_exists keyword [C++]
ms.assetid: d3eb34b6-f3a9-4063-a286-b62a28c0c7fa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ac866487c25ee4ce75abbebe9b9f9c2a5e97828
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405943"
---
# <a name="ifexists-statement"></a>__if_exists-Anweisung
Die **__if_exists** -Anweisung testet, ob der angegebene Bezeichner vorhanden ist. Wenn der Bezeichner vorhanden ist, wird der angegebene Anweisungsblock ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```  
__if_exists ( identifier ) {   
statements  
};  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|*identifier*|Der Bezeichner, dessen Vorhandensein Sie überprüfen möchten.|  
|*Anweisungen*|Eine oder mehrere Anweisungen ausgeführt wird, wenn *Bezeichner* vorhanden ist.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!CAUTION]
>  Um die zuverlässigsten Ergebnisse zu erzielen, verwenden die **__if_exists** Anweisung unter den folgenden Einschränkungen.  
  
-   Anwenden der **__if_exists** -Anweisung nur einfache Typen, die nicht durch Vorlagen.  
  
-   Anwenden der **__if_exists** -Anweisung auf Bezeichner innerhalb oder außerhalb einer Klasse. Wenden Sie keine der **__if_exists** Anweisung, um lokale Variablen.  
  
-   Verwenden der **__if_exists** Anweisung nur im Text einer Funktion. Außerhalb des Texts einer Funktion die **__if_exists** -Anweisung kann nur vollständig definierte Typen testen.  
  
-   Wenn Sie auf überladene Funktionen testen, können Sie nicht auf eine bestimmte Form der Überladung testen.  
  
 Die Ergänzung der **__if_exists** -Anweisung ist die [__if_not_exists](../cpp/if-not-exists-statement.md) Anweisung.  
  
## <a name="example"></a>Beispiel  
 Beachten Sie, dass in diesem Beispiel Vorlagen verwendet werden, was nicht empfohlen wird.  
  
```cpp 
// the__if_exists_statement.cpp  
// compile with: /EHsc  
#include <iostream>  
  
template<typename T>  
class X : public T {  
public:  
   void Dump() {  
      std::cout << "In X<T>::Dump()" << std::endl;  
  
      __if_exists(T::Dump) {  
         T::Dump();  
      }  
  
      __if_not_exists(T::Dump) {  
         std::cout << "T::Dump does not exist" << std::endl;  
      }  
   }     
};  
  
class A {  
public:  
   void Dump() {  
      std::cout << "In A::Dump()" << std::endl;  
   }  
};  
  
class B {};  
  
bool g_bFlag = true;  
  
class C {  
public:  
   void f(int);  
   void f(double);  
};  
  
int main() {   
   X<A> x1;  
   X<B> x2;  
  
   x1.Dump();  
   x2.Dump();  
  
   __if_exists(::g_bFlag) {  
      std::cout << "g_bFlag = " << g_bFlag << std::endl;  
   }  
  
   __if_exists(C::f) {  
      std::cout << "C::f exists" << std::endl;  
   }  
  
   return 0;  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```Output  
In X<T>::Dump()  
In A::Dump()  
In X<T>::Dump()  
T::Dump does not exist  
g_bFlag = 1  
C::f exists  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Auswahlanweisungen](../cpp/selection-statements-cpp.md)   
 [Stichwörter](../cpp/keywords-cpp.md)   
 [__if_not_exists-Anweisung](../cpp/if-not-exists-statement.md)