---
title: Compilerfehler Fehler C2040 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2040
dev_langs:
- C++
helpviewer_keywords:
- C2040
ms.assetid: 74ca3592-1469-4965-ab34-a4815e2fbefe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6b19a5dd647e51efb46ef9798b7f7cdff5339b9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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