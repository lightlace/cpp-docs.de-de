---
title: Portabilität an ABI-Grenzen (Modern C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: abbd405e-3038-427c-8c24-e00598f0936a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c214ed18e5afec51f52514abdd73e0e5b658635a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32419660"
---
# <a name="portability-at-abi-boundaries-modern-c"></a>Portabilität an ABI-Grenzen (Modern C++)
Verwenden Sie ausreichend portable Typen und Konventionen anwendungsbinärschnittstelle Grenzen an. "portable Type" ist ein integrierter C-Typ oder eine Struktur, die nur die integrierte C-Typen enthält. Klassentypen können nur verwendet werden, wenn der Aufrufer und aufgerufenen Layout Einigkeit Konvention usw. aufrufen. Dies ist nur möglich, wenn beide mit dem gleichen Compiler und die compilereinstellungen kompiliert werden.  
  
## <a name="how-to-flatten-a-class-for-c-portability"></a>Gewusst wie: eine Klasse für C#-Portabilität vereinfachen  
 Wenn Aufrufer mit einer anderen Compiler/Sprache kompiliert werden kann, dann "reduzieren", um eine **"extern"C""** -API mit einem bestimmten Aufrufkonvention:  
  
```cpp  
// class widget {  
//   widget();  
//   ~widget();  
//   double method( int, gadget& );  
// };  
extern "C" {        // functions using explicit "this"  
   struct widget;   // opaque type (forward declaration only)  
   widget* STDCALL widget_create();      // constructor creates new "this"  
   void STDCALL widget_destroy(widget*); // destructor consumes "this"  
   double STDCALL widget_method(widget*, int, gadget*); // method uses "this"  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Willkommen zurück bei C++](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)