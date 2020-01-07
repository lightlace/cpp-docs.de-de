---
title: Compilerfehler C2198
ms.date: 11/04/2016
f1_keywords:
- C2198
helpviewer_keywords:
- C2198
ms.assetid: 638a845c-9d7f-4115-a9aa-d72455605668
ms.openlocfilehash: cbe4f95037aabf3b4febc1a8fff5a324773a33b4
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301833"
---
# <a name="compiler-error-c2198"></a>Compilerfehler C2198

"Funktion": Nicht genügend Argumente für Aufruf.

Der Compiler hat nicht genügend Parameter für einen Aufruf der Funktion oder eine falsche Funktionsdeklaration gefunden.

Im folgenden Beispiel wird C2198 generiert:

```c
// C2198.c
// compile with: /c
void func( int, int );
int main() {
   func( 1 );   // C2198 only one actual parameter
   func( 1, 1 );   // OK
}
```
