---
title: Compilerfehler C3697 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3697
dev_langs: C++
helpviewer_keywords: C3697
ms.assetid: 2d3f63c4-b7f8-421d-a7a5-2bf17fd054f9
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0d14bd3de0fb2ddf6c44babb10c2ec1edcb87a21
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3697"></a>Compilerfehler C3697
"Qualifizierer": Verwenden Sie diese Qualifizierer kann nicht auf "^"  
  
 Die Trackinghandle (^) wurde auf einen Qualifizierer angewendet, für die er nicht entworfen wurde.  
  
 Im folgende Beispiel wird C3697 generiert:  
  
```  
// C3697.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String ^__restrict s;   // C3697  
   String ^ s2;   // OK  
}  
```