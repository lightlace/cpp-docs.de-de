---
title: Compilerfehler C2577
ms.date: 11/04/2016
f1_keywords:
- C2577
helpviewer_keywords:
- C2577
ms.assetid: fc79ef83-8362-40a2-9257-8037c3195ce4
ms.openlocfilehash: 4406aa90b26bc517308132ae9cccd003d44a9aad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408458"
---
# <a name="compiler-error-c2577"></a>Compilerfehler C2577

"Member": Destruktor/Finalizer kann nicht keinen Rückgabetyp haben

Einen Destruktor oder Finalizer kann nicht den Wert zurück `void` oder eines anderen Typs. Entfernen Sie die `return` Anweisung aus der Destruktordefinition.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2577 generiert.

```
// C2577.cpp
// compile with: /c
class A {
public:
   A() {}
   ~A(){
      return 0;   // C2577
   }
};
```