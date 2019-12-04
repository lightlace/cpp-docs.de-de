---
title: Compilerfehler C3420
ms.date: 11/04/2016
f1_keywords:
- C3420
helpviewer_keywords:
- C3420
ms.assetid: 99b53c77-f36b-4574-9199-b53111becccb
ms.openlocfilehash: 5e165a0c181bc27adebe75111050f49130305693
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756252"
---
# <a name="compiler-error-c3420"></a>Compilerfehler C3420

"Finalizer": Ein Finalizer kann nicht virtuell sein.

Ein Finalizer kann von seinem einschließenden Typ nur nicht virtuell aufgerufen werden. Aus diesem Grund wird die Deklaration eines Finalizers als Fehler angesehen.

Weitere Informationen finden Sie unter [debugtoren und Finalizer in Gewusst wie: definieren und Verarbeiten von Klassen und StrukturenC++(/CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3420 generiert.

```cpp
// C3420.cpp
// compile with: /clr /c
ref class R {
   virtual !R() {}   // C3420
};
```
