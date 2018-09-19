---
title: Compilerfehler C2467 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2467
dev_langs:
- C++
helpviewer_keywords:
- C2467
ms.assetid: f9ead270-5d0b-41cc-bdcd-586a647c67a7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8bab320bfdba9fcbd408771b7859a22fc85fa06e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048772"
---
# <a name="compiler-error-c2467"></a>Compilerfehler C2467

Ungültige Deklaration des anonymen '– benutzerdefinierte-Typ'

Ein geschachtelter Typ mit den benutzerdefinierten deklariert wurde. Dies ist ein Fehler beim Kompilieren von C-Quellcode mit ANSI-Kompatibilitätsoption ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) aktiviert.

Im folgende Beispiel wird die C2467 generiert:

```
//C2467.c
// compile with: /Za
int main() {
   struct X {
      union { int i; };   // C2467, nested declaration
   };
}
```