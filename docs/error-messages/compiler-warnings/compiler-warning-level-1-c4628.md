---
title: Compilerwarnung (Stufe 1) C4628
ms.date: 11/04/2016
f1_keywords:
- C4628
helpviewer_keywords:
- C4628
ms.assetid: 20fdc6f8-5f6a-40cc-aff8-c7ccf3d8ec26
ms.openlocfilehash: ebb71155774ce32d6b4fc2b9920fdd31dd466841
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221205"
---
# <a name="compiler-warning-level-1-c4628"></a>Compilerwarnung (Stufe 1) C4628

'digraphs' werden mit '-Ze' nicht unterstützt. Die Zeichensequenz 'Digraph' wird nicht als alternativer Token für 'Zeichen' interpretiert.

Digraphen werden nicht unterstützt, unter [/Ze](../../build/reference/za-ze-disable-language-extensions.md). Diese Warnung wird ein Fehler folgen.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Im folgende Beispiel wird die C4628 generiert:

```
// C4628.cpp
// compile with: /WX
#pragma warning(default : 4628)
int main()
<%   // C4628 <% digraph for {
}
```