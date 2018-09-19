---
title: Compilerwarnung (Stufe 2) C4094 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4094
dev_langs:
- C++
helpviewer_keywords:
- C4094
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b9317cbc31ef8bddb14da11af1087a148fd3188
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078711"
---
# <a name="compiler-warning-level-2-c4094"></a>Compilerwarnung (Stufe 2) C4094

Unbenanntes 'token' deklariert keine Symbole

Der Compiler hat eine leere Deklaration einer unbenannten Struktur, Union oder Klasse. Die Deklaration wird ignoriert.

## <a name="example"></a>Beispiel

```
// C4094.cpp
// compile with: /W2
struct
{
};   // C4094

int main()
{
}
```

Diese Bedingung generiert einen Fehler ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).