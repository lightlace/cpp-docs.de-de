---
title: Linkertoolwarnung LNK4078 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4078
dev_langs:
- C++
helpviewer_keywords:
- LNK4078
ms.assetid: 5a16796d-6caf-42d9-8f65-b042843eafb8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eecd4dc17724b5c02a8ce8398f5630b691dab320
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109813"
---
# <a name="linker-tools-warning-lnk4078"></a>Linkertoolwarnung LNK4078

mehrere 'Abschnittsname'-Abschnitte mit unterschiedlichen Attributen gefunden

LINK finden Sie zwei oder mehr Abschnitte mit dem gleichen Namen, jedoch unterschiedliche Attribute auf.

Diese Warnung kann durch eine Import- oder Exportdatei-Datei verursacht werden, die von einer früheren Version von LINK oder LIB erstellt wurde.

Erstellen Sie die Datei, und anschließend neu.

## <a name="example"></a>Beispiel

LNK4078 kann auch von einer wichtigen Änderung verursacht werden: im Abschnitt mit dem Namen von [Init_seg](../../preprocessor/init-seg.md) X86 war Lese-/Schreibzugriff, sie sind jetzt schreibgeschützt.

Im folgende Beispiel wird die LNK4078 generiert.

```
// LNK4078.cpp
// compile with: /W1
// LNK4078 expected
#include <stdio.h>
#pragma warning(disable : 4075)
typedef void (__cdecl *PF)(void);
int cxpf = 0;   // number of destructors to call
PF pfx[200];   // pointers to destructors.

struct A { A() {} };

int myexit (PF pf) { return 0; }

#pragma section(".mine$a", read, write)
// try the following line instead
// #pragma section(".mine$a", read)
__declspec(allocate(".mine$a")) int ii = 1;

#pragma section(".mine$z", read, write)
// try the following line instead
// #pragma section(".mine$z", read)
__declspec(allocate(".mine$z")) int i = 1;

#pragma data_seg()
#pragma init_seg(".mine$m", myexit)
A bbbb;
A cccc;
int main() {}
```