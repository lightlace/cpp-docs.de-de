---
title: Compilerwarnung (Stufe 4) C4429
ms.date: 11/04/2016
f1_keywords:
- C4429
helpviewer_keywords:
- C4429
ms.assetid: a3e4cf1f-a869-4e47-834a-850c21eb5297
ms.openlocfilehash: d4eb7e7075c7adf418254e748f104a6d57c72741
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391529"
---
# <a name="compiler-warning-level-4-c4429"></a>Compilerwarnung (Stufe 4) C4429

Mögliche unvollständig oder falsch formatiert. Universelle Zeichennamen

Der Compiler hat eine Folge von Zeichen, die ein ungültiger universeller Zeichenname sein können. Ein universeller Zeichenname ist `\u` gefolgt von vier hexadezimale Ziffern oder `\U` gefolgt von acht hexadezimalen Ziffern.

Im folgende Beispiel wird die C4429 generiert:

```
// C4429.cpp
// compile with: /W4 /WX
int \ug0e4 = 0;   // C4429
// Try the following line instead:
// int \u00e4 = 0;   // OK, a well-formed universal character name.
```