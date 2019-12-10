---
title: Compilerwarnung (Stufe 4) C4429
ms.date: 11/04/2016
f1_keywords:
- C4429
helpviewer_keywords:
- C4429
ms.assetid: a3e4cf1f-a869-4e47-834a-850c21eb5297
ms.openlocfilehash: 6702db4af5c31d21610e02b1a4ec75af27ad10f2
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990826"
---
# <a name="compiler-warning-level-4-c4429"></a>Compilerwarnung (Stufe 4) C4429

möglicherweise unvollständiger oder nicht ordnungsgemäß geformter universeller Zeichen Name.

Der Compiler hat eine Zeichen Sequenz erkannt, die möglicherweise ein ungültiger universeller Zeichen Name ist. Ein universeller Zeichen Name wird `\u` gefolgt von vier hexadezimalen Ziffern oder `\U` gefolgt von acht hexadezimalen Ziffern.

Im folgenden Beispiel wird C4429 generiert:

```cpp
// C4429.cpp
// compile with: /W4 /WX
int \ug0e4 = 0;   // C4429
// Try the following line instead:
// int \u00e4 = 0;   // OK, a well-formed universal character name.
```
