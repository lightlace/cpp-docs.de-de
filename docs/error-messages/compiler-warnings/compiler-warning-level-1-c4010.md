---
title: Compilerwarnung (Stufe 1) C4010 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4010
dev_langs:
- C++
helpviewer_keywords:
- C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52449689d329cee45cc69b63c315ce9335befbe0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073097"
---
# <a name="compiler-warning-level-1-c4010"></a>Compilerwarnung (Stufe 1) C4010

einzeiliger Kommentar enthält Zeilenfortsetzungszeichen

Ein einzeiliger Kommentar an, die von eingeführt wird / / "," enthält einen umgekehrten Schrägstrich (\\), die als ein Zeilenfortsetzungszeichen dient. Der Compiler die nächste Zeile als Fortsetzung betrachtet und als Kommentar behandelt.

Einige gesteuerte Syntax-, dass die Editoren nicht auf die Zeile das Fortsetzungszeichen als Kommentar nach Hinweisen. Syntaxfarben für alle Zeilen, die dazu führen, diese Warnung dass zu ignorieren.

Im folgende Beispiel wird die C4010 generiert:

```
// C4010.cpp
// compile with: /WX
int main() {
   // the next line is also a comment because of the backslash \
   int a = 3; // C4010
   a++;
}
```