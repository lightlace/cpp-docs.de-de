---
title: Linkertoolwarnung LNK4253
ms.date: 11/04/2016
f1_keywords:
- LNK4253
helpviewer_keywords:
- LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
ms.openlocfilehash: c3f45880571e5c06f76d5f063ff993e2f6b2be9b
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988085"
---
# <a name="linker-tools-warning-lnk4253"></a>Linkertoolwarnung LNK4253

der Abschnitt "Section1" wurde nicht in "Section2" zusammengeführt. bereits in "Section3" zusammengeführt

Der Linker hat mehrere zusammen widersprüchliche Zusammenschluss Anforderungen erkannt. Der Linker ignoriert eine der Anforderungen.

Eine **/Merge** -Option oder-Direktive wurde gefunden, und der `from` Abschnitt wurde aufgrund einer früheren **/Merge** -Option oder-Direktive (oder aufgrund einer impliziten Zusammenführung vom Linker) bereits in einem anderen Abschnitt zusammengeführt.

Entfernen Sie zum Auflösen von Linkertoolwarnung LNK4253 eine der Zusammenschluss Anforderungen.

Wenn Sie auf x86-Computer und Windows CE Ziele (Arm, mips, SH4 und Thumb) mit C++Visual abzielen, ist das. Der CRT-Abschnitt ist jetzt schreibgeschützt. , Wenn der Code vom vorherigen Verhalten abhängig ist (. CRT-Abschnitte mit Lese-/Schreibzugriff sind möglicherweise ein unerwartetes Verhalten.

Weitere Informationen finden Sie unter

- [/MERGE (Abschnitte kombinieren)](../../build/reference/merge-combine-sections.md)

- [comment (C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird der Linker angewiesen, den `.rdata` Abschnitt zweimal zusammenzuführen, aber in verschiedene Abschnitte. Im folgenden Beispiel wird Linkertoolwarnung LNK4253 generiert.

```cpp
// LNK4253.cpp
// compile with: /W1 /link /merge:.rdata=text2
// LNK4253 expected
#pragma comment(linker, "/merge:.rdata=.text")
int main() {}
```
