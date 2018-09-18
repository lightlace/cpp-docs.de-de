---
title: Compilerfehler C2197 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2197
dev_langs:
- C++
helpviewer_keywords:
- C2197
ms.assetid: 6dd5a6ec-bc80-41b9-a4ac-46f80eaca42d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb8e13e21cbba3b6cbf6a4bd84a835270d7fee2c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036813"
---
# <a name="compiler-error-c2197"></a>Compilerfehler C2197

"Funktion": Zu viele Argumente für Aufruf

Der Compiler hat zu viele Parameter für einen Aufruf der Funktion oder eine falsche Funktionsdeklaration gefunden.

Im folgenden Beispiel wird C2197 generiert:

```
// C2197.c
// compile with: /Za /c
void func( int );
int main() {
   func( 1, 2 );   // C2197 two actual parameters
   func( 2 );   // OK
}
```