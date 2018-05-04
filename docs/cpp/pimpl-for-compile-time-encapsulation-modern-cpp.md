---
title: Pimpl für Compilierungszeitkapselung (Modern C++) | Microsoft Docs
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
ms.openlocfilehash: f611a898018cee5edc031be1db2fd35af8857e16
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>Pimpl für Kompilierzeitkapselung (Modern C++)
Die *"pimpl" Idiom* eine moderne C++-Technik, um die Kopplung verringert, und trennen Sie die Schnittstellen-Implementierung ausgeblendet wird. "Pimpl" ist die Kurzform für "Zeiger auf Implementierung." Sie können bereits mit dem Konzept vertraut sein, aber wissen, dass sie von anderen Namen an, wie sich zu mir Cat oder Compiler Firewall Idiom.  
  
## <a name="why-use-pimpl"></a>Gründe für die Verwendung von "pimpl"  
 So sieht wie das Idiom "pimpl" der Softwareentwicklung verbessert werden kann:  
  
-   Minimierung der Kompilierung Abhängigkeiten.  
  
-   Die Trennung der Schnittstelle sowie die Implementierung.  
  
-   Portabilität.  
  
## <a name="pimpl-header"></a>Header "pimpl"  
  
```cpp  
// my_class.h  
class my_class {  
   //  ... all public and protected stuff goes here ...  
private:  
   class impl; unique_ptr<impl> pimpl; // opaque type here  
};  
  
```  
  
 Die Ausdrucksweise "pimpl" vermeidet Rebuild überlappend und Objektlayouts jedoch fehleranfällig. Es ist für die (transitiv) beliebten Typen geeignet.  
  
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
 Erwägen Sie, ob die Unterstützung für nicht auslösend Swap Spezialisierung hinzuzufügen.  
  
## <a name="see-also"></a>Siehe auch  
 [Willkommen zurück bei C++](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)