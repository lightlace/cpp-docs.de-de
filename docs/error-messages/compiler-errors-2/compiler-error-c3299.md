---
title: Compilerfehler C3299
ms.date: 11/04/2016
f1_keywords:
- C3299
helpviewer_keywords:
- C3299
ms.assetid: 7cabdf01-bceb-404f-9401-cdd9c7fc1641
ms.openlocfilehash: 314b75a9d0ab8cde2886a7466fa0f95b5bbdd8f1
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58778051"
---
# <a name="compiler-error-c3299"></a>Compilerfehler C3299

"Member_Funktion": Einschränkungen können nicht angegeben werden, sie werden von der Basismethode geerbt.

Wenn Sie eine generische Memberfunktion überschreiben, können Sie keine Einschränkungsklauseln angeben (das Wiederholen von Einschränkungen impliziert, dass die Einschränkungen nicht geerbt werden).

Die Einschränkungsklauseln für die generische Funktion, die Sie überschreiben, werden geerbt.

Weitere Informationen finden Sie unter [Einschränkungen für generische Typparameter (C++ / CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md).

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