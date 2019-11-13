---
title: Compilerwarnung (Stufe 1) C4628
ms.date: 11/04/2016
f1_keywords:
- C4628
helpviewer_keywords:
- C4628
ms.assetid: 20fdc6f8-5f6a-40cc-aff8-c7ccf3d8ec26
ms.openlocfilehash: 6063755db5ac517d868bc47d2c417356ccef5d58
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051441"
---
# <a name="compiler-warning-level-1-c4628"></a>Compilerwarnung (Stufe 1) C4628

'digraphs' werden mit '-Ze' nicht unterstützt. Die Zeichensequenz 'Digraph' wird nicht als alternativer Token für 'Zeichen' interpretiert.

Digraphen werden unter [/Ze](../../build/reference/za-ze-disable-language-extensions.md)nicht unterstützt. Auf diese Warnung folgt ein Fehler.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Im folgenden Beispiel wird C4628 generiert:

```cpp
// C4628.cpp
// compile with: /WX
#pragma warning(default : 4628)
int main()
<%   // C4628 <% digraph for {
}
```