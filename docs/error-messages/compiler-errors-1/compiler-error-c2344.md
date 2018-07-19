---
title: Compilerfehler C2344 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2344
dev_langs:
- C++
helpviewer_keywords:
- C2344
ms.assetid: a84c7b37-c84e-4345-8691-c23abb2dc193
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cdbe2ac9c1533a22e5e77f1d3f2db5c73ef93a3e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33222162"
---
# <a name="compiler-error-c2344"></a>Compilerfehler C2344
align(#): Die Ausrichtung muss eine Potenz von 2 sein.  
  
 Bei Verwendung des [align](../../cpp/align-cpp.md) -Schlüsselworts muss der übergebene Wert eine Potenz von zwei sein.  
  
 Im folgenden Code wird beispielsweise C2344 erzeugt, weil 3 keine Potenz von 2 ist:  
  
```  
// C2344.cpp  
// compile with: /c  
__declspec(align(3)) int a;   // C2344  
__declspec(align(4)) int b;   // OK  
```