---
title: Compilerwarnung (Stufe 2) C4285 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4285
dev_langs:
- C++
helpviewer_keywords:
- C4285
ms.assetid: fa14de1f-fc19-4eec-8bea-81003636e12f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c4366142c14ec77c1c344312e50e7295c71ca93
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33291699"
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