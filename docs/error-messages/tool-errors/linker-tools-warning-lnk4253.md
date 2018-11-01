---
title: Linkertoolwarnung LNK4253
ms.date: 11/04/2016
f1_keywords:
- LNK4253
helpviewer_keywords:
- LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
ms.openlocfilehash: d2fd7238a3f57b11b91813bd40b66cb3e9f47202
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628825"
---
# <a name="linker-tools-warning-lnk4253"></a>Linkertoolwarnung LNK4253

Abschnitt 'Abschnitt1' in "" section2";" nicht zusammengeführt bereits zusammengeführt in 'Abschnitt3'.

Der Linker erkannt mehrere Anforderungen in Konflikt stehende zusammenführen. Der Linker ignoriert eine der Anforderungen.

Ein **/MERGE** Option oder Direktive festgestellt wird und die `from` Abschnitt wurde bereits mit einem anderen Abschnitt aufgrund einer vorherigen zusammengeführt **/MERGE** Option oder Direktive (oder aufgrund einer impliziten Zusammenführung der Linker-Tool).

Entfernen Sie eines der Merge-Anforderungen an, um LNK4253 generiert zu beheben.

Wenn X86 auf Computern und Windows CE-Plattformen (ARM, MIPS, SH4 und Ziehpunkt) mit Visual C++, die. CRT-Abschnitt ist jetzt schreibgeschützt. Wenn Ihr Code auf das vorherige Verhalten (. CRT-Abschnitte sind Lese-/Schreibzugriff), kann unerwartetes Verhalten angezeigt.

Weitere Informationen finden Sie unter

- [/MERGE (Abschnitte kombinieren)](../../build/reference/merge-combine-sections.md)

- [comment (C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird der Linker angewiesen wird, zum Zusammenführen der `.rdata` Abschnitt zweimal, aber in verschiedene Abschnitte. Im folgende Beispiel wird die LNK4253 generiert.

```
// LNK4253.cpp
// compile with: /W1 /link /merge:.rdata=text2
// LNK4253 expected
#pragma comment(linker, "/merge:.rdata=.text")
int main() {}
```