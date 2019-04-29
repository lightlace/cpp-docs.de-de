---
title: Compilerfehler C3804
ms.date: 11/04/2016
f1_keywords:
- C3804
helpviewer_keywords:
- C3804
ms.assetid: 7c4cda28-ec96-4d04-937b-36dbd9944722
ms.openlocfilehash: c3c00d1d07306a9e8dc67d3f75a5cb25d8f03aee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400083"
---
# <a name="compiler-error-c3804"></a>Compilerfehler C3804

'Property_accessor': die Zugriffsmethoden eine Eigenschaft müssen entweder werden alle statisch oder alle nicht statischen

Wenn Sie eine nicht triviale Eigenschaft zu definieren, werden die Accessorfunktionen können entweder statisch oder -Instanz, aber nicht beides.

Weitere Informationen finden Sie unter [property](../../extensions/property-cpp-component-extensions.md) .

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3804 generiert.

```
// C3804.cpp
// compile with: /c /clr
ref struct A {

   property int i {
      static int get() {}
      void set(int i) {}
   }   // C3804 error

   // OK
   property int j {
      int get() { return 0; }
      void set(int i) {}
   }

   property int k {
      static int get() { return 0; }
      static void set(int i) {}
   }
};
```