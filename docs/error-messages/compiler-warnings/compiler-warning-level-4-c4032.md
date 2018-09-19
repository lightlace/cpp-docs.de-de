---
title: Compilerwarnung (Stufe 4) C4032 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4032
dev_langs:
- C++
helpviewer_keywords:
- C4032
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 608c99c81fac0088a4d1d8bb8a6d3b0b61c7af50
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086035"
---
# <a name="compiler-warning-level-4-c4032"></a>Compilerwarnung (Stufe 4) C4032

formaler Parameter 'Nummer' hat einen anderen Typ, wenn die höher gestuft

Der Parametertyp ist nicht kompatibel ist, über Standard-Erweiterungen, mit dem Typ in einer früheren Deklaration.

Dies ist ein Fehler in ANSI C ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) und eine Warnung der Microsoft-Erweiterungen (/ Ze).

## <a name="example"></a>Beispiel

```
// C4032.c
// compile with: /W4
void func();
void func(char);   // C4032, char promotes to int

int main()
{
}
```