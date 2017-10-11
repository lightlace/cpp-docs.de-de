---
title: Compilerfehler Fehler C2071 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2071
dev_langs:
- C++
helpviewer_keywords:
- C2071
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c62bb735a84b04bfb0c1addd5e3dd20a48a3eb33
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2071"></a>Compilerfehler Fehler C2071
'Bezeichner': Ungültige Speicherklasse  
  
 `identifier`wurde mit einem ungültigen deklariert [Speicherklasse](../../c-language/c-storage-classes.md). Dieser Fehler kann verursacht werden, wenn mehr als eine Speicherklasse für einen Bezeichner angegeben ist oder wenn die Definition mit der Speicherklassen-Deklaration nicht kompatibel ist.  
  
 Verstehen Sie zur Behebung dieses Problems die beabsichtigte Speicherklasse des Bezeichners – z. B. `static` oder `extern`–, und korrigieren Sie die Deklaration zur Übereinstimmung.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2071 generiert.  
  
```  
// C2071.cpp  
// compile with: /c  
struct C {  
   extern int i;   // C2071  
};  
struct D {  
   int i;   // OK, no extern on an automatic  
};  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2071 generiert.  
  
```  
// C2071_b.cpp  
// compile with: /c  
typedef int x(int i) { return i; }   // C2071  
typedef int (x)(int);   // OK, no local definition in typedef  
```
