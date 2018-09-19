---
title: Compilerfehler C2470 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2470
dev_langs:
- C++
helpviewer_keywords:
- C2470
ms.assetid: e17d2cb8-b84c-447c-976a-625f0c96f3fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f494f550393bf1fb1a1a17b522b73945a7581e6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089150"
---
# <a name="compiler-error-c2470"></a>Compilerfehler C2470

"Function": sieht wie eine Funktionsdefinition aus, aber es gibt keine Parameterliste; sichtbarer Funktionstext wird übersprungen

Eine Funktionsdefinition fehlt die Argumentliste.

Im folgende Beispiel wird die C2470 generiert:

```
// C2470.cpp
int MyFunc {};  // C2470
void MyFunc2() {};  //OK

int main(){
   MyFunc();
   MyFunc2();
}
```