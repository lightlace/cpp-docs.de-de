---
title: Compilerfehler C3904
ms.date: 11/04/2016
f1_keywords:
- C3904
helpviewer_keywords:
- C3904
ms.assetid: 08297605-e4f2-4c6c-b637-011f1fd40631
ms.openlocfilehash: 8c7f4a2861825a35d676328b5e283a5e4087d85b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519781"
---
# <a name="compiler-error-c3904"></a>Compilerfehler C3904

'Property_accessor': muss Number-Parameter angeben

Überprüfen Sie die Anzahl von Parametern in Ihrer `get` und `set` Methoden mit den Eigenschaftendimensionen.

- Die Anzahl von Parametern für die `get` Methode muss gleich der Anzahl der Dimensionen der Eigenschaft oder 0 (null) bei nicht indizierten Eigenschaften.

- Die Anzahl der Parameter, der die `set` Methode muss eine mehr als die Anzahl der Dimensionen der Eigenschaft.

Weitere Informationen finden Sie unter [property](../../windows/property-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3904 generiert.

```
// C3904.cpp
// compile with: /clr /c
ref class X {
   property int P {
      // set
      void set();   // C3904
      // try the following line instead
      // void set(int);

      // get
      int get(int, int);   // C3904
      // try the following line instead
      // int get();
   };
};
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3904 generiert.

```
// C3904b.cpp
// compile with: /clr /c
ref struct X {
   property int Q[double, double, float, float, void*, int] {
      // set
      void set(double, void*);   // C3904
      // try the following line instead
      // void set(double, double, float, float, void*, int, int);

      // get
      int get();   // C3904
      // try the following line instead
      // int get(double, double, float, float, void*, int);
   }
};
```