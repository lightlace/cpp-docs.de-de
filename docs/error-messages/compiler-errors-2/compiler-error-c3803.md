---
title: Compilerfehler C3803
ms.date: 11/04/2016
f1_keywords:
- C3803
helpviewer_keywords:
- C3803
ms.assetid: bad5fb9a-ed9a-4c15-96e7-cf06e200a50d
ms.openlocfilehash: f6c255ec18d6dcf94f3ec022f09b173c2c66a1dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400096"
---
# <a name="compiler-error-c3803"></a>Compilerfehler C3803

"Property": Eigenschaft hat einen Typ, der mit einem seiner Accessoren 'Accessor' inkompatibel ist

Der Typ einer Eigenschaft, die mit definierten [Eigenschaft](../../cpp/property-cpp.md) entspricht nicht den Rückgabetyp für eine der Accessorfunktionen.

Im folgende Beispiel wird die C3803 generiert:

```
// C3803.cpp
struct A
{
   __declspec(property(get=GetIt)) int i;
   char GetIt()
   {
      return 0;
   }

   /*
   // try the following definition instead
   int GetIt()
   {
      return 0;
   }
   */
}; // C3803

int main()
{
}
```