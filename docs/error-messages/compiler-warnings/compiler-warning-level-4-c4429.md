---
title: Compilerwarnung (Stufe 4) C4429
ms.date: 11/04/2016
f1_keywords:
- C4429
helpviewer_keywords:
- C4429
ms.assetid: a3e4cf1f-a869-4e47-834a-850c21eb5297
ms.openlocfilehash: e814867278701be11b0158789f6373453aea75b8
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2019
ms.locfileid: "74683236"
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