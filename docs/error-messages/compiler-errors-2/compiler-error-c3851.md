---
title: Compilerfehler C3851 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 82104776b2d1153310d0552bd873238333e746f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33268831"
---
# <a name="compiler-error-c3851"></a>Compilerfehler C3851
„char“: Ein universeller Zeichenname darf kein Zeichen im Basiszeichensatz bezeichnen.  
  
 Im als C++ kompilierten Code können Sie keinen universellen Zeichennamen verwenden, der ein Zeichen des einfachen Quellzeichensatzes außerhalb einer Zeichenfolge oder eines Zeichenliterals darstellt. Weitere Informationen finden Sie unter [Zeichensätze](../../cpp/character-sets.md). Im als C kompilierten Code können Sie keinen universellen Zeichennamen für Zeichen im Bereich 0x20-0x7f (einschließlich) verwenden, ausgenommen 0x24 („$“), 0x40 („@“) oder 0x60 („`“).  
  
 In den folgenden Beispielen wird C3851 generiert und anschließend gezeigt, wie dieses Problem behoben wird:  
  
```cpp  
// C3851.cpp  
int main()  
{  
   int test1_\u0041 = 0;   // C3851, \u0041 = 'A' in basic character set  
   int test2_A = 0;        // OK  
}  
```