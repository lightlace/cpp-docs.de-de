---
title: Compilerfehler C2156 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2156
dev_langs:
- C++
helpviewer_keywords:
- C2156
ms.assetid: 136f9c67-2c27-4f61-b7e6-ccd202eca697
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1be9525cea208347e16a0b6a41a7c696ff340083
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2156"></a>Compilerfehler C2156
Pragma muss außerhalb der Funktion liegen  
  
 Ein Pragma, das auf globaler Ebene (außerhalb eines Funktionsrumpfs) angegeben werden muss, befindet sich innerhalb einer Funktion.  
  
 Im folgenden Beispiel wird C2156 generiert:  
  
```  
// C2156.cpp  
#pragma optimize( "l", on )   // OK  
int main() {  
   #pragma optimize( "l", on )   // C2156  
}  
```
