---
title: Compilerfehler C2803 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2803
dev_langs:
- C++
helpviewer_keywords:
- C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: efa9efa2dc204d302f69d873c0199d4431efccb1
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2803"></a>Compilerfehler C2803
'Operator Operator' muss mindestens einen formalen Parameter des Klassentyps haben.  
  
 Der überladene Operator hat einen Parameter vom Klassentyp.  
  
 Müssen Sie mindestens einen Parameter als Verweis (ohne Verwendung der Zeiger jedoch Verweise) oder als Wert zu schreiben können übergeben "ein < b" (ein und b wird der Typklasse ein).  
  
 Wenn beide Parameter Zeiger werden ein reiner Vergleich der Zeigeradressen und die benutzerdefinierte Konvertierung wird nicht verwendet.  
  
 Im folgenden Beispiel wird C2803 generiert:  
  
```  
// C2803.cpp  
// compile with: /c  
class A{};  
bool operator< (const A *left, const A *right);   // C2803  
// try the following line instead  
// bool operator< (const A& left, const A& right);  
```
