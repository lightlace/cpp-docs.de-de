---
title: Compilerwarnung (Stufe 1) C4010
ms.date: 11/04/2016
f1_keywords:
- C4010
helpviewer_keywords:
- C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
ms.openlocfilehash: 045b3f6e615e11c24caa9a088baf6ea9f6448efb
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627316"
---
# <a name="compiler-warning-level-1-c4010"></a>Compilerwarnung (Stufe 1) C4010

einzeiligen Kommentar enthält Zeilen Fortsetzungs Zeichen

Ein einzeiligen Kommentar, der durch//eingeführt wird, enthält einen umgekehrten Schrägstrich (\\), der als Zeilen Fortsetzungs Zeichen fungiert. Der Compiler betrachtet die nächste Zeile als Fortsetzung und behandelt Sie als Kommentar.

Einige von der Syntax gesteuerte Editoren geben nicht die Zeile an, die dem Fortsetzungs Zeichen als Kommentar folgt. Ignorieren Sie Syntax Farben für alle Zeilen, die diese Warnung auslösen.

Im folgenden Beispiel wird C4010 generiert:

```cpp
// C4010.cpp
// compile with: /WX
int main() {
   // the next line is also a comment because of the backslash \
   int a = 3; // C4010
   a++;
}
```