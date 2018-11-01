---
title: Compilerwarnung (Stufe 1) C4628
ms.date: 11/04/2016
f1_keywords:
- C4628
helpviewer_keywords:
- C4628
ms.assetid: 20fdc6f8-5f6a-40cc-aff8-c7ccf3d8ec26
ms.openlocfilehash: ebb71155774ce32d6b4fc2b9920fdd31dd466841
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466025"
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