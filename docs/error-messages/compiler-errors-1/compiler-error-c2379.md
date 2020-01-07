---
title: Compilerfehler C2379
ms.date: 11/04/2016
f1_keywords:
- C2379
helpviewer_keywords:
- C2379
ms.assetid: 37dc3015-a4af-4341-bbf3-da6150df7e51
ms.openlocfilehash: f096791a6120023e079b93452a4b35c669db2139
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302106"
---
# <a name="compiler-error-c2379"></a>Compilerfehler C2379

der formale Parameter Number hat beim herauf Stufen einen anderen Typ.

Der Typ des angegebenen Parameters ist aufgrund von Standard Erweiterungen mit dem Typ in einer vorherigen Deklaration nicht kompatibel. Dies ist ein Fehler in ANSI C ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) und eine Warnung mit Microsoft-Erweiterungen ( **/Ze**).

Im folgenden Beispiel wird C2379 generiert:

```c
// C2379.c
// compile with: /Za
void func();
void func(char);   // C2379, char promotes to int
```
