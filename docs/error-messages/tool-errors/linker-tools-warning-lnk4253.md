---
title: Linkertoolwarnung LNK4253 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4253
dev_langs:
- C++
helpviewer_keywords:
- LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d26d688825f504cbce8224adc9a5766a555d2fc8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016818"
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