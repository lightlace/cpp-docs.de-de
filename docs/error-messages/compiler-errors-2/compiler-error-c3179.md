---
title: Compilerfehler Fehler C3179 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3179
dev_langs:
- C++
helpviewer_keywords:
- C3179
ms.assetid: 60d7e41b-25fd-48ac-8b79-830c062f4dcd
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d8ce81f56a9cbdfda7ddef7ac1a6f9fcd7954d7c
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3179"></a>Compilerfehler Fehler C3179
Ein unbenannter verwalteter oder WinRT-Typ ist nicht zulässig.  
  
Alle CLR- und WinRT-Klassen und -Strukturen müssen Namen haben.  
  
Im folgenden Beispiel wird C3179 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3179a.cpp  
// compile with: /clr /c  
typedef value struct { // C3179  
// try the following line instead  
// typedef value struct MyStruct {  
   int i;  
} V;  
```  

