---
title: Compilerwarnung (Stufe 1) C4010
ms.date: 11/04/2016
f1_keywords:
- C4010
helpviewer_keywords:
- C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
ms.openlocfilehash: 40c6724daf17c1c0b546bb7bc64bb704f732e8d6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386550"
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