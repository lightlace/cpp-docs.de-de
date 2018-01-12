---
title: Compilerfehler Fehler C2040 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2040
dev_langs: C++
helpviewer_keywords: C2040
ms.assetid: 74ca3592-1469-4965-ab34-a4815e2fbefe
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f102b1fea23c89debc86970d7548ba7da152cd37
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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