---
title: Compilerfehler C3279 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3279
dev_langs:
- C++
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 16bb13d226b6d4d5d5846f8302070bf0c9579cfb
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3279"></a>Compilerfehler C3279
Teilweise oder explizite Spezialisierungen sowie explizite Instanziierungen von Klassenvorlagen, die im cli-Namespace deklariert sind, sind nicht zulässig.  
  
 Der `cli` -Namespace wird von Microsoft definiert und enthält Pseudovorlagen. Der Visual C++-Compiler lässt keine benutzerdefinierten partiellen und expliziten Spezialisierungen und keine expliziten Instanziierungen von Klassenvorlagen in diesem Namespace zu.  
  
 Im folgenden Beispiel wird C3279 generiert:  
  
```  
// C3279.cpp  
// compile with: /clr  
namespace cli {  
   template <> ref class array<int> {};   // C3279  
   template <typename T> ref class array<T, 2> {};   // C3279  
}  
```
