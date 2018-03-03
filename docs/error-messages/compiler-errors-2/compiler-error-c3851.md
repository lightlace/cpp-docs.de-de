---
title: Compilerfehler C3851 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3851
dev_langs:
- C++
helpviewer_keywords:
- C3851
ms.assetid: da30c21c-33aa-4439-8fb3-2f5021ea4985
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6c5f0cca8f3c1dfc4b3b35d494ebf73459a74d03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3851"></a>Compilerfehler C3851
„char“: Ein universeller Zeichenname darf kein Zeichen im Basiszeichensatz bezeichnen.  
  
 Im als C++ kompilierten Code können Sie keinen universellen Zeichennamen verwenden, der ein Zeichen des einfachen Quellzeichensatzes außerhalb einer Zeichenfolge oder eines Zeichenliterals darstellt. Weitere Informationen finden Sie unter [Character Sets](../../cpp/character-sets2.md). Im als C kompilierten Code können Sie keinen universellen Zeichennamen für Zeichen im Bereich 0x20-0x7f (einschließlich) verwenden, ausgenommen 0x24 („$“), 0x40 („@“) oder 0x60 („`“).  
  
 In den folgenden Beispielen wird C3851 generiert und anschließend gezeigt, wie dieses Problem behoben wird:  
  
```cpp  
// C3851.cpp  
int main()  
{  
   int test1_\u0041 = 0;   // C3851, \u0041 = 'A' in basic character set  
   int test2_A = 0;        // OK  
}  
```