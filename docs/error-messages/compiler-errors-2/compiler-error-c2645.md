---
title: Compilerfehler C2645 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2645
dev_langs:
- C++
helpviewer_keywords:
- C2645
ms.assetid: 6609c2fa-c3b2-4a6b-8e8d-58fb52f67175
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ada345b79c061c71bc716bf7baf96116444bcc7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076826"
---
# <a name="compiler-error-c2645"></a>Compilerfehler C2645

kein vollständiger Name für Elementzeiger (gefunden ":: *")

Die Deklaration eines Zeigers auf einen Member gibt keine Klasse an.

Im folgende Beispiel wird die C2645 generiert:

```
// C2645.cpp
class A {};
int main() {
   int B::* bp;   // C2645 B not defined
   int A::* ap;   // OK
}
```