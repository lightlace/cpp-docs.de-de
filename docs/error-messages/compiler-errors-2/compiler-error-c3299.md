---
title: Compilerfehler C3299
ms.date: 11/04/2016
f1_keywords:
- C3299
helpviewer_keywords:
- C3299
ms.assetid: 7cabdf01-bceb-404f-9401-cdd9c7fc1641
ms.openlocfilehash: 4ad48ea0bc09e098a41cb9aa969a08e9ead48f73
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484828"
---
# <a name="compiler-error-c3299"></a>Compilerfehler C3299

"Member_Funktion": Einschränkungen können nicht angegeben werden, sie werden von der Basismethode geerbt.

Wenn Sie eine generische Memberfunktion überschreiben, können Sie keine Einschränkungsklauseln angeben (das Wiederholen von Einschränkungen impliziert, dass die Einschränkungen nicht geerbt werden).

Die Einschränkungsklauseln für die generische Funktion, die Sie überschreiben, werden geerbt.

Weitere Informationen finden Sie unter [Einschränkungen für generische Typparameter (C++ / CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3299 generiert:

```
// C3299.cpp
// compile with: /clr /c
public ref struct R {
   generic<class T>
   where T : R
   virtual void f();
};

public ref struct S : R {
   generic<class T>
   where T : R   // C3299
   virtual void f() override;
};
```