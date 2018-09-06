---
title: Compilerfehler C3851 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3851
dev_langs:
- C++
helpviewer_keywords:
- C3851
ms.assetid: da30c21c-33aa-4439-8fb3-2f5021ea4985
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f495a61fd3c157862fe65d82c1ffe5f047d798dd
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43895174"
---
# <a name="compiler-error-c3851"></a>Compilerfehler C3851

> "*Char*': eine universelle Zeichenname darf kein Zeichen im Basiszeichensatz bezeichnen

## <a name="remarks"></a>Hinweise

Im als C++ kompilierten Code können Sie keinen universellen Zeichennamen verwenden, der ein Zeichen des einfachen Quellzeichensatzes außerhalb einer Zeichenfolge oder eines Zeichenliterals darstellt. Weitere Informationen finden Sie unter [Zeichensätze](../../cpp/character-sets.md). Im als C kompilierten Code, Sie können keine keinen universellen Zeichennamen für Zeichen im Bereich von 0 x 20-0x7f (einschließlich), mit Ausnahme von 0 x 24 ("$"), 0 x 40 ("\@"), oder 0 x 60 ("\`").

## <a name="example"></a>Beispiel

In den folgenden Beispielen wird C3851 generiert und anschließend gezeigt, wie dieses Problem behoben wird:

```cpp
// C3851.cpp
int main()  
{
   int test1_\u0041 = 0;   // C3851, \u0041 = 'A' in basic character set
   int test2_A = 0;        // OK
}
```