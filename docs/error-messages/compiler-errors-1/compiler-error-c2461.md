---
title: Compilerfehler C2461 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2461
dev_langs:
- C++
helpviewer_keywords:
- C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39d58b315fdd7e3c4e1899041cebf8400813ed40
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029298"
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