---
title: Compilerfehler Fehler C2040 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2040
dev_langs:
- C++
helpviewer_keywords:
- C2040
ms.assetid: 74ca3592-1469-4965-ab34-a4815e2fbefe
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3504c8e18637ef907d5ab9c941ef7ad550daedf0
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2040"></a>Compilerfehler Fehler C2040
„Operator“: „Bezeichner1“ unterscheidet sich in Ebenen der Dereferenzierung von „Bezeichner2“.  
  
 Ein Ausdruck, der die angegebenen Operanden beinhaltet, verfügt über nicht kompatible oder implizit konvertierte Operandentypen. Wenn beide Operanden arithmetisch bzw. beide Operatoren nicht arithmetisch sind (z. B. Array oder Zeiger), werden sie unverändert verwendet. Wenn ein Operand arithmetisch ist und der andere nicht, wird der arithmetische Operand in den Typ des nicht arithmetischen Operanden konvertiert.  
  
 Im folgenden Beispiel wird C2040 generiert und gezeigt, wie Sie diesen Fehler beheben.  
  
```  
// C2040.cpp  
// Compile by using: cl /c /W3 C2040.cpp  
bool test() {  
   char c = '3';  
   return c == "3"; // C2446, C2040  
   // return c == '3'; // OK  
}  
```
