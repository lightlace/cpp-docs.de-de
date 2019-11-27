---
title: Portabilität an Abi-Grenzen
description: Vereinfachen Sie C++ Schnittstellen zu C-Aufruf Konventionen an binären Schnittstellen Grenzen.
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: abbd405e-3038-427c-8c24-e00598f0936a
ms.openlocfilehash: b3b2b217739ff5900c8ef0329ff3e8909a3fe036
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303322"
---
# <a name="portability-at-abi-boundaries"></a>Portabilität an Abi-Grenzen

Verwenden Sie bei binären Schnittstellen Begrenzungen ausreichend Portable Typen und Konventionen. Ein "portabler Typ" ist ein integrierter c-Typ oder eine Struktur, die nur integrierte c-Typen enthält. Klassentypen können nur verwendet werden, wenn der Aufrufer und der aufgerufene das Layout, die Aufruf Konvention usw. akzeptieren. Dies ist nur möglich, wenn beide mit den gleichen Compilereinstellungen und Compilereinstellungen kompiliert werden.

## <a name="how-to-flatten-a-class-for-c-portability"></a>Vereinfachen einer Klasse für die C-Portabilität

Wenn Aufrufer mit einem anderen Compiler bzw. einer anderen Sprache kompiliert werden können, dann "vereinfachen" Sie eine **externe "C"** -API mit einer bestimmten Aufruf Konvention:

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

[Willkommen zurück beiC++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)
