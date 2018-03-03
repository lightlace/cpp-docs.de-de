---
title: Compilerfehler C2157 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2157
dev_langs:
- C++
helpviewer_keywords:
- C2157
ms.assetid: babbca24-16dc-4b69-be14-a675029249c1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 365218bccff744be577e5abf2a1472e40edccf7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2157"></a>Compilerfehler C2157
'Funktion': muss vor der Verwendung in der Pragma-Liste deklariert werden.  
  
 Der Funktionsname ist nicht deklariert, bevor auf ihn in der Liste der Funktionen für ein [alloc_text](../../preprocessor/alloc-text.md) -Pragma verwiesen wird.  
  
 Im folgenden Beispiel wird C2157 generiert:  
  
```  
// C2157.cpp  
// compile with: /c  
#pragma alloc_text( "func", func)   // C2157  
  
// OK  
extern "C" void func();  
#pragma alloc_text( "func", func)  
```