---
title: Compilerwarnung (Stufe 1) C4162 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4162
dev_langs:
- C++
helpviewer_keywords:
- C4162
ms.assetid: 21ae3c92-501d-4689-ad7d-13753cb65eff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a36fa6a63443bf2272df7ce6125fd77afedf100f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027179"
---
# <a name="compiler-warning-level-1-c4162"></a>Compilerwarnung (Stufe 1) C4162

'Bezeichner': keine Funktion mit C-Bindung gefunden

Eine Funktion mit C-Verknüpfung deklariert ist, aber es wurde nicht gefunden.

Um diese Warnung zu beheben, kompilieren, in eine c-Datei (der C-Compiler aufgerufen wird).  Wenn Sie den C++-Compiler aufrufen müssen, setzen Sie "extern"C"vor der Funktionsdeklaration".

Das folgende Beispiel generiert C4162

```
// C4162.cpp
// compile with: /c /W1
unsigned char _bittest(long* a, long b);
#pragma intrinsic (_bittest)   // C4162

int main() {
   bool bit;
   long num = 78002;
   bit = _bittest(&num, 5);
}
```

Mögliche Lösung:

```
// C4162b.cpp
// compile with: /c
extern "C"
unsigned char _bittest(long* a, long b);
#pragma intrinsic (_bittest)

int main() {
   bool bit;
   long num = 78002;
   bit = _bittest(&num, 5);
}
```