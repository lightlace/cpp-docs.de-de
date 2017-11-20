---
title: Compilerfehler C2495 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2495
dev_langs: C++
helpviewer_keywords: C2495
ms.assetid: bb7066fe-3549-4901-97e4-157f3c04dd57
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7daef885e27c30a78f7eb02f2573f700146af6ff
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2495"></a>Compilerfehler C2495
'Bezeichner': 'Nothrow' kann nur auf Funktionsdeklarationen oder-Definitionen angewendet werden  
  
 Die [Nothrow](../../cpp/nothrow-cpp.md) erweiterte Attribut kann nur auf Funktionsdeklarationen oder-Definitionen angewendet werden.  
  
 Im folgende Beispiel wird C2495 generiert:  
  
```  
// C2495.cpp  
// compile with: /c  
__declspec(nothrow) class X {   // C2495  
   int m_data;  
} x;  
  
__declspec(nothrow) void test();   // OK  
```