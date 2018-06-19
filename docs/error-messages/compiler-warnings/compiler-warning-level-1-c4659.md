---
title: Compilerwarnung (Stufe 1) C4659 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4659
dev_langs:
- C++
helpviewer_keywords:
- C4659
ms.assetid: e29ba8db-7917-43f6-8e34-868b752279ae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 643b599cd11d0935f1769ad37dca4e764f0418e6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33285615"
---
# <a name="compiler-warning-level-1-c4659"></a>Compilerwarnung (Stufe 1) C4659
\#Pragma 'Pragma': Verwendung von reservierten Segments "Segment" weist ein nicht definiertes Verhalten, verwenden Sie die #pragma-Kommentar (Linker,...)  
  
 Die .drectve-Option wurde verwendet, um eine Option an den Linker übergeben. Verwenden Sie stattdessen Pragma [Kommentar](../../preprocessor/comment-c-cpp.md) für eine Linkeroption übergeben.  
  
```  
// C4659.cpp  
// compile with: /W1 /LD  
#pragma code_seg(".drectve")   // C4659  
```