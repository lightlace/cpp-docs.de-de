---
title: Compilerfehler C3904 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3904
dev_langs:
- C++
helpviewer_keywords:
- C3904
ms.assetid: 08297605-e4f2-4c6c-b637-011f1fd40631
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4453d39b93000116b3547ff5047e6837c8d34e6a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46135974"
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