---
title: Compilerfehler C3510 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3510
dev_langs:
- C++
helpviewer_keywords:
- C3510
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5cc134823abf2657426b0c1be9cfbe6d92a74035
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111325"
---
# <a name="compiler-error-c3510"></a>Compilerfehler C3510

abhängiger Typ 'Typbib Bibliothek 'wurde' wurde nicht gefunden.

[No_registry](../../preprocessor/no-registry.md) und [Auto_search](../../preprocessor/auto-search.md) übergeben wurden `#import` , aber der Compiler konnte nicht keine referenzierte Typbibliothek gefunden.

Um diesen Fehler zu beheben, stellen Sie sicher, dass alle Bibliotheken und Typbibliotheken für den Compiler verfügbar sind.

Im folgende Beispiel wird die C3510 generiert:

Wird davon ausgegangen, dass die folgenden zwei Typbibliotheken erstellt wurden, und C3510a.tlb wurde gelöscht oder nicht auf den Pfad.

```
// C3510a.idl
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]
library C3510aLib
{
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]
   enum E_C3510
   {
      one, two, three
   };
};
```

Und klicken Sie dann auf den Quellcode für die zweite Typbibliothek:

```
// C3510b.idl
// post-build command: del /f C3510a.tlb
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]
library C3510bLib
{
   importlib ("C3510a.tlb");
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]
   struct S_C3510 {
      enum E_C3510 e;
   };
};
```

Und klicken Sie dann die Client-Code:

```
// C3510.cpp
#import "c3510b.tlb" no_registry auto_search   // C3510
int main() {
   C3510aLib::S_C4336 ccc;
}
```