---
title: Compilerfehler C2149 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2149
dev_langs:
- C++
helpviewer_keywords:
- C2149
ms.assetid: 7a106dab-d79f-41b9-85be-f36e86e4d2ab
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3e181d4fc2d5ee10533d2a0e13142e827863d762
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2149"></a>Compilerfehler C2149
"Bezeichner": Die Breite des benannten Bitfelds muss größer als null (0) sein.  
  
 Nur nicht benannte Bitfelder können eine Breite von null (0) aufweisen.  
  
 Im folgenden Beispiel wird C2149 generiert:  
  
```  
// C2149.cpp  
// compile with: /c  
struct C {  
   int i : 0;   // C2149  
   int j : 2;   // OK  
};  
```
