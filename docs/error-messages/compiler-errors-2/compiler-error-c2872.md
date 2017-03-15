---
title: Compilerfehler C2872 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2872
dev_langs:
- C++
helpviewer_keywords:
- C2872
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
caps.latest.revision: 11
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: d53dbd9429ba3c1a525b85a3ef9f2e70152ddfa2
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2872"></a>Compilerfehler C2872
'Symbol': Mehrdeutiges Attribut  
  
Der Compiler ermitteln nicht, welches Symbol auf verwiesen wird.  
  
C2872 kann auftreten, wenn eine Headerdatei enthält eine [using-Direktive](../../cpp/namespaces-cpp.md#using_directives), und eine nachfolgende Headerdatei enthalten ist, und es enthält einen Typ, der auch in den im angegebenen Namespace ist die `using` Richtlinie. Geben Sie einen `using` alle Headerdateien mit angegeben werden erst nach Richtlinie `#include`.  
  
 Weitere Informationen zu C2872 finden Sie im Knowledge Base-Artikeln [PRB: Compiler Fehler bei der Verwendung #import mit XML in Visual C++ .NET](http://support.microsoft.com/kb/316317) und ["C2872 Fehler: 'Plattform': Mehrdeutiges Attribut" Fehlermeldung, wenn Sie den Windows::Foundation::Metadata-Namespace in Visual Studio 2013 verwenden](https://support.microsoft.com/kb/2890859).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2872 generiert:  
  
```cpp  
// C2872.cpp  
namespace A {  
   int i;  
}  
  
using namespace A;  
int i;  
int main() {  
   ::i++;   // ok  
   A::i++;   // ok  
   i++;   // C2872 ::i or A::i?  
}  
```
