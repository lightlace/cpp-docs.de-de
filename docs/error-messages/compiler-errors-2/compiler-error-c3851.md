---
title: Compilerfehler C3851 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C3851
dev_langs:
- C++
helpviewer_keywords:
- C3851
ms.assetid: da30c21c-33aa-4439-8fb3-2f5021ea4985
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 792d13ece8b864b3d8d7e251bf530f685a02ccf7
ms.sourcegitcommit: 770f6c4a57200aaa9e8ac6e08a3631a4b4bdca05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
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