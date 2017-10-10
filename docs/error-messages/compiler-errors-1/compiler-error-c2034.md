---
title: Compilerfehler Fehler C2034 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2034
dev_langs:
- C++
helpviewer_keywords:
- C2034
ms.assetid: 953d70fa-bde9-4ce6-a55d-741e7bc63ff4
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: df3d2310a5f066fdb937900abe545c16f5526508
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2034"></a>Compilerfehler Fehler C2034
'Bezeichner': Typ der Bitfeld ist zu klein für die Anzahl von Bits  
  
 Die Anzahl der Bits in der Deklaration Bitfeld überschreitet die Größe des Basistyps.  
  
 Im folgende Beispiel wird C2034 generiert:  
  
```  
// C2034.cpp  
struct A {  
   char test : 9;   // C2034, char has 8 bits  
};  
```  
  
 Mögliche Lösung:  
  
```  
// C2034b.cpp  
// compile with: /c  
struct A {  
   char test : 8;  
};  
```
