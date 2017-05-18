---
title: Compilerfehler C2872 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: c81fc315c4bb893b96876b7b67b42806a3246583
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="compiler-error-c2872"></a>Compilerfehler C2872
"*Symbol*': Mehrdeutiges Attribut  
  
Der Compiler ermitteln nicht, welches Symbol auf verwiesen wird. Mehr als ein Symbol mit dem angegebenen Namen befindet sich im Bereich. Finden Sie im Anschluss an die Fehlermeldung für die Dateispeicherorte und Deklarationen des Compilers hat für das Symbol nicht eindeutig. Um dieses Problem zu beheben, können Sie vollständig mehrdeutige Symbol mithilfe des Namespaces, z. B. qualifizieren `std::byte` oder `::byte`. Sie können auch eine [Namespacealias](../../cpp/namespaces-cpp.md#namespace_aliases) um einem Namespace enthalten einen bequemen kurze Namen für die Verwendung zu gewähren, wenn Symbole in Ihren Quellcode eindeutig gemacht.  
  
C2872 kann auftreten, wenn eine Headerdatei umfasst eine [using-Direktive](../../cpp/namespaces-cpp.md#using_directives), und eine nachfolgende Headerdatei enthalten ist, enthält einen Typ, der auch in den im angegebenen Namespace ist die `using` Richtlinie. Geben Sie einen `using` Richtlinie nur nach allen die Header-Dateien werden mit angegeben `#include`.  
  
 Weitere Informationen zu C2872 finden Sie im Knowledge Base-Artikeln [PRB: Compiler Fehler bei der Verwendung #import mit XML-Code in Visual C++ .NET](http://support.microsoft.com/kb/316317) und ["C2872 Fehler: 'Plattform': Mehrdeutiges Attribut" Fehlermeldung, wenn Sie den Windows::Foundation::Metadata-Namespace in Visual Studio 2013 verwenden](https://support.microsoft.com/kb/2890859).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2872, da ein mehrdeutiger Verweis auf die Variable erfolgt `i`; zwei Variablen mit demselben Namen sind im Bereich:  
  
```cpp  
// C2872.cpp  
// compile with: cl /EHsc C2872.cpp  
namespace A {  
   int i;  
}  
  
using namespace A;  
int i;  
int main() {  
   ::i++;   // ok, uses i from global namespace  
   A::i++;   // ok, uses i from namespace A  
   i++;   // C2872 ambiguous: ::i or A::i? 
   // To fix this issue, use the fully qualified name
   // for the intended variable. 
}  
```
