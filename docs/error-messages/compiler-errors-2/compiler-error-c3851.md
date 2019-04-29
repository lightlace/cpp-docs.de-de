---
title: Compilerfehler C3851
ms.date: 09/05/2018
f1_keywords:
- C3851
helpviewer_keywords:
- C3851
ms.assetid: da30c21c-33aa-4439-8fb3-2f5021ea4985
ms.openlocfilehash: 52c4f3a393ffaf2b61a65c8e2e0dcc8efac08288
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62380941"
---
# <a name="compiler-error-c3851"></a>Compilerfehler C3851

> "*Char*': eine universelle Zeichenname darf kein Zeichen im Basiszeichensatz bezeichnen

## <a name="remarks"></a>Hinweise

Im als C++ kompilierten Code können Sie keinen universellen Zeichennamen verwenden, der ein Zeichen des einfachen Quellzeichensatzes außerhalb einer Zeichenfolge oder eines Zeichenliterals darstellt. Weitere Informationen finden Sie unter [Character Sets](../../cpp/character-sets.md). Im als C kompilierten Code, Sie können keine keinen universellen Zeichennamen für Zeichen im Bereich von 0 x 20-0x7f (einschließlich), mit Ausnahme von 0 x 24 ("$"), 0 x 40 ("\@"), oder 0 x 60 ("\`").

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