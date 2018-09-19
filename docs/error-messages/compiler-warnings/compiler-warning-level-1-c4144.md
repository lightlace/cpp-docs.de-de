---
title: Compilerwarnung (Stufe 1) C4144 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4144
dev_langs:
- C++
helpviewer_keywords:
- C4144
ms.assetid: a37b445d-dbc6-43b4-8d95-ffd0e4225464
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ba9c1210247ad537f8fa1224c30b1c88d9c6b721
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109664"
---
# <a name="compiler-warning-level-1-c4144"></a>Compilerwarnung (Stufe 1) C4144

"Ausdruck": Relationaler Ausdruck als Schalterausdruck

Die angegebenen relationalen Ausdrucks wurde als steuernder Ausdruck verwendet eine [wechseln](../../cpp/switch-statement-cpp.md) Anweisung. Die zugeordnete Case-Anweisungen werden boolesche Werte angeboten. Im folgende Beispiel wird die C4144 generiert:

```
// C4144.cpp
// compile with: /W1
int main()
{
   int i = 0;
   switch(!i) {   // C4144, remove the ! to resolve
      case 1:
         break;
      default:
         break;
   }
}
```