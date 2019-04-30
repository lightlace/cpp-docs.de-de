---
title: Compilerfehler C2379
ms.date: 11/04/2016
f1_keywords:
- C2379
helpviewer_keywords:
- C2379
ms.assetid: 37dc3015-a4af-4341-bbf3-da6150df7e51
ms.openlocfilehash: 1b3256efb6c0ff8236ba80a9ac681780f34fa8dd
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345652"
---
# <a name="compiler-error-c2379"></a>Compilerfehler C2379

Anzahl der formalen Parameter hat einen anderen Typ, wenn heraufgestuft

Der Typ des angegebenen Parameters ist nicht kompatibel ist, über Standard-Erweiterungen, mit dem Typ in einer früheren Deklaration. Dies ist ein Fehler in ANSI C ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) und eine Warnung mit Microsoft-Erweiterungen (**/Ze**).

Im folgende Beispiel wird die C2379 generiert:

```
// C2379.c
// compile with: /Za
void func();
void func(char);   // C2379, char promotes to int
```