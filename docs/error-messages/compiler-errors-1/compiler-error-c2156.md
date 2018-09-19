---
title: Compilerfehler C2156 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2156
dev_langs:
- C++
helpviewer_keywords:
- C2156
ms.assetid: 136f9c67-2c27-4f61-b7e6-ccd202eca697
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 37e0810fa31e66b62553825892b53374b22e4263
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038635"
---
# <a name="compiler-error-c2156"></a>Compilerfehler C2156

Pragma muss außerhalb der Funktion liegen

Ein Pragma, das auf globaler Ebene (außerhalb eines Funktionsrumpfs) angegeben werden muss, befindet sich innerhalb einer Funktion.

Im folgenden Beispiel wird C2156 generiert:

```
// C2156.cpp
#pragma optimize( "l", on )   // OK
int main() {
   #pragma optimize( "l", on )   // C2156
}
```