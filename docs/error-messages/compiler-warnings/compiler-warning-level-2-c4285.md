---
title: Compilerwarnung (Stufe 2) C4285 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4285
dev_langs: C++
helpviewer_keywords: C4285
ms.assetid: fa14de1f-fc19-4eec-8bea-81003636e12f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0893334b46ed4b0790996482dd5625978705d3ac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-2-c4285"></a>Compilerwarnung (Stufe 2) C4285
Rückgabetyp wird für "Identifier:: Operator ->" rekursiv, wenn mit Infix-Notation verwendet.  
  
 Das angegebene **Operator -> ()** Funktion kann nicht der Rückgabetyp für die er definiert ist oder ein Verweis auf den Typ für die es definiert ist.  
  
 Im folgenden Beispiel wird C4285 generiert:  
  
```  
// C4285.cpp  
// compile with: /W2  
class C  
{  
public:  
    C operator->();   // C4285  
   // C& operator->();  C4285, also  
};  
  
int main()  
{  
}  
```