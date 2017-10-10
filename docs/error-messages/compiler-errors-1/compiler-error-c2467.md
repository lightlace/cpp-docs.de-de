---
title: Compilerfehler C2467 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2467
dev_langs:
- C++
helpviewer_keywords:
- C2467
ms.assetid: f9ead270-5d0b-41cc-bdcd-586a647c67a7
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a51321e6597bffe0dded58ffa481f054e770f9b7
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2467"></a>Compilerfehler C2467
Ungültige Deklaration eines anonymen '-benutzerdefinierte-Typ"  
  
 Ein geschachtelter benutzerdefinierten Typ deklariert wurde. Dies ist ein Fehler beim Kompilieren von C#-Quellcode mit der Option ANSI-Kompatibilität (["/ Za"](../../build/reference/za-ze-disable-language-extensions.md)) aktiviert.  
  
 Im folgende Beispiel wird C2467 generiert:  
  
```  
//C2467.c  
// compile with: /Za   
int main() {  
   struct X {  
      union { int i; };   // C2467, nested declaration  
   };  
}  
```
