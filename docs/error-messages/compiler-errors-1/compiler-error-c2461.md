---
title: Compilerfehler C2461
ms.date: 11/04/2016
f1_keywords:
- C2461
helpviewer_keywords:
- C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
ms.openlocfilehash: e8f82ed4ce8ad77a22961a42c8e9a256e6f647db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368031"
---
# <a name="compiler-error-c2461"></a>Compilerfehler C2461

> "*Klasse*": Formale Parameterliste für Konstruktor fehlt

Der Konstruktor für die Klasse gibt keine formalen Parameter. Die Deklaration eines Konstruktors muss es sich um eine Liste formaler Parameter angeben. Die Liste kann leer sein.

Um dieses Problem zu beheben, fügen Sie ein Klammernpaar nach der Deklaration von *Klasse*:: **Klasse*.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie C2461 generiert Fehler beheben:

```cpp
// C2461.cpp
// compile with: /c
class C {
   C::C;     // C2461
   C::C();   // OK
};
```