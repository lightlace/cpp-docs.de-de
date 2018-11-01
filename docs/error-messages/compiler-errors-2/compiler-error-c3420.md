---
title: Compilerfehler C3420
ms.date: 11/04/2016
f1_keywords:
- C3420
helpviewer_keywords:
- C3420
ms.assetid: 99b53c77-f36b-4574-9199-b53111becccb
ms.openlocfilehash: 3db109598ce0741ca34a230d8925994543bcb5ea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50645938"
---
# <a name="compiler-error-c3420"></a>Compilerfehler C3420

"Finalizer": Ein Finalizer kann nicht virtuell sein.

Ein Finalizer kann von seinem einschließenden Typ nur nicht virtuell aufgerufen werden. Aus diesem Grund wird die Deklaration eines Finalizers als Fehler angesehen.

Weitere Informationen finden Sie unter [Destruktoren und Finalizer in der Vorgehensweise: definieren und Verarbeiten von Klassen und Strukturen (C++ / CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3420 generiert.

```
// C3420.cpp
// compile with: /clr /c
ref class R {
   virtual !R() {}   // C3420
};
```