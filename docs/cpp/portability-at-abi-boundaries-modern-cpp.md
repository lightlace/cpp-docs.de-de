---
title: Portabilität an ABI-Grenzen (Modern C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: abbd405e-3038-427c-8c24-e00598f0936a
ms.openlocfilehash: 3f72bc32e436c2f7a2f76ed6bbb9553b5e5be6b8
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220308"
---
# <a name="portability-at-abi-boundaries-modern-c"></a>Portabilität an ABI-Grenzen (Modern C++)

Verwenden Sie ausreichend portable Datentypen und Konventionen, an den Begrenzungen der Anwendungsbinärdatei-Schnittstelle. Eine "portable-Type" ist ein integrierter C-Typ oder eine Struktur, die nur die integrierte C#-Typen enthält. Klassentypen können nur verwendet werden, wenn der Aufrufer und aufgerufenen auf Layout mit Ausrichtung von einigen Aufrufen Konvention usw. Dies ist nur möglich, wenn beide mit dem gleichen Compiler und der compilereinstellungen kompiliert werden.

## <a name="how-to-flatten-a-class-for-c-portability"></a>Wie Sie eine Klasse für den C-Portabilität zu vereinfachen

Wenn Aufrufer mit einer anderen Compiler/Sprache kompiliert werden kann, dann "vereinfachen", um eine **Extern "C"** -API mit einer bestimmten Aufrufkonvention:

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

[Willkommen zurück bei C++ (Modern C++)](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)
