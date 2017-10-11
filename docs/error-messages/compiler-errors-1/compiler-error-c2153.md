---
title: Compilerfehler C2153 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2153
dev_langs:
- C++
helpviewer_keywords:
- C2153
ms.assetid: cfc50cb7-9a0f-4b5b-879a-d419c99f7be1
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a1370e665708db783cf030c226de9de32c6c6b3f
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2153"></a>Compilerfehler C2153
hexadezimale Konstanten müssen mindestens eine hexadezimale Ziffer enthalten.  
  
 Hexadezimale Konstanten 0 x 0 X und \x sind nicht gültig. Es muss mindestens eine hexadezimale Ziffer folgen x oder X.  
  
 Im folgenden Beispiel wird C2153 generiert:  
  
```  
// C2153.cpp  
int main() {  
   int a= 0x;    // C2153  
   int b= 0xA;   // OK  
}  
```
