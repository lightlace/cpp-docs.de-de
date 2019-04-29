---
title: Compilerfehler C3675
ms.date: 11/04/2016
f1_keywords:
- C3675
helpviewer_keywords:
- C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
ms.openlocfilehash: e29e536bf89aef887dc043327e4b4596703d0538
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363894"
---
# <a name="compiler-error-c3675"></a>Compilerfehler C3675

'Funktion': ist reserviert, weil "Eigenschaft" definiert ist

Wenn Sie eine einfache Eigenschaft deklarieren, generiert der Compiler die Get- und Set-Accessormethode und die Namen in den Bereich des Programms vorhanden sind.  Die vom Compiler generierten Namen werden durch voranstellen Get_- und Set_ an den Eigenschaftennamen gebildet.  Aus diesem Grund können Sie Funktionen mit dem gleichen Namen wie die vom Compiler generierten Accessoren nicht deklarieren.

Weitere Informationen finden Sie unter [property](../../extensions/property-cpp-component-extensions.md) .

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3675 generiert.

```
// C3675.cpp
// compile with: /clr /c
ref struct C {
public:
   property int Size;
   int get_Size() { return 0; }   // C3675
};
```