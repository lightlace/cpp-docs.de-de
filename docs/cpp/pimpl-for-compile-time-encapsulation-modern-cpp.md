---
title: Pimpl für Kompilierzeitkapselung (Modern C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2e80c4bd86cd4c7400e3937fcb8d164fe6b14106
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404654"
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>Pimpl für Kompilierzeitkapselung (Modern C++)
Die *"pimpl" Idiom* ist eine moderne C++-Methode zum Ausblenden der Implementierung, um die Kopplung zu minimieren und Schnittstellen zu trennen. "Pimpl" ist die Kurzform für "-Zeiger zu Implementierung" Sie können bereits mit dem Konzept vertraut sein, aber andere Namen, wie sich zu mir Cat oder eine Compiler-Firewall-Idiom erkennbar.  
  
## <a name="why-use-pimpl"></a>Gründe für die Verwendung von "pimpl"  
 Hier ist, wie das Idiom "pimpl" für den Lebenszyklus der Softwareentwicklung verbessern kann:  
  
-   Minimierung der Kompilierung Abhängigkeiten.  
  
-   Trennung von Benutzeroberfläche und Implementierung.  
  
-   Portabilität.  
  
## <a name="pimpl-header"></a>"Pimpl"-header  
  
```cpp  
// my_class.h  
class my_class {  
   //  ... all public and protected stuff goes here ...  
private:  
   class impl; unique_ptr<impl> pimpl; // opaque type here  
};  
```  
  
 Das Idiom "pimpl" werden die Neuerstellung kaskadierende und fehleranfällig Objektlayouts vermieden. Es eignet sich gut für (transitiv) beliebte Typen.  
  
## <a name="pimpl-implementation"></a>Implementierung von "pimpl"  
 Definieren der `impl` Klasse in der CPP-Datei.  
  
```cpp  
// my_class.cpp  
class my_class::impl {  // defined privately here  
  // ... all private data and functions: all of these  
  //     can now change without recompiling callers ...  
};  
my_class::my_class(): pimpl( new impl )  
{  
  // ... set impl values ...   
}  
```  
  
## <a name="best-practices"></a>Bewährte Methoden  
 Erwägen Sie, um Unterstützung für nicht auslösend Swap Spezialisierung hinzuzufügen.  
  
## <a name="see-also"></a>Siehe auch  
 [Willkommen zurück bei C++](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ Language Reference (C++-Programmiersprachenreferenz)](../cpp/cpp-language-reference.md)   
 [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)