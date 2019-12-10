---
title: Linkertoolwarnung LNK4254
ms.date: 11/04/2016
f1_keywords:
- LNK4254
helpviewer_keywords:
- LNK4254
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
ms.openlocfilehash: 8431bd2d89fd5df5cf076ad006ab04006f552c4c
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988060"
---
# <a name="linker-tools-warning-lnk4254"></a>Linkertoolwarnung LNK4254

der Abschnitt "Section1" (Offset) wurde in "Section2" (Offset) mit unterschiedlichen Attributen zusammengeführt.

Der Inhalt eines Abschnitts wurde mit einem anderen Abschnitt zusammengeführt, aber die Attribute der beiden Abschnitte unterscheiden sich. Ihr Programm kann unerwartete Ergebnisse liefern. Beispielsweise können Daten, die Sie lesen möchten, sich jetzt in einem beschreibbaren Abschnitt befinden.

Um Linkertoolwarnung LNK4254 aufzulösen, ändern Sie die Merge-Anforderung, oder entfernen Sie Sie.

Wenn Sie auf x86-Computer und Windows CE Ziele (Arm, mips, SH4 und Thumb) mit C++Visual abzielen, ist das. Der CRT-Abschnitt ist schreibgeschützt. , Wenn der Code vom vorherigen Verhalten abhängig ist (. CRT-Abschnitte mit Lese-/Schreibzugriff sind möglicherweise ein unerwartetes Verhalten.

Weitere Informationen finden Sie unter

- [/MERGE (Abschnitte kombinieren)](../../build/reference/merge-combine-sections.md)

- [comment (C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird Linkertoolwarnung LNK4254 generiert.

```cpp
// LNK4254.cpp
// compile with: /W1 /link /WX
// LNK4254 expected
#pragma comment(linker, "/merge:.data=.text")
int main() {}
```
