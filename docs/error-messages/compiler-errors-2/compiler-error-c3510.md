---
title: Compilerfehler C3510
ms.date: 11/04/2016
f1_keywords:
- C3510
helpviewer_keywords:
- C3510
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
ms.openlocfilehash: dbb65628aa6e0da94a91a59724ca8e1cd5b56491
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187351"
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