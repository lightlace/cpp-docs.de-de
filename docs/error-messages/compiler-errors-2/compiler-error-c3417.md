---
title: Compilerfehler C3417 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3417
dev_langs:
- C++
helpviewer_keywords:
- C3417
ms.assetid: 3e7869ea-8948-42fb-ba30-6ccafe499c35
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e25adc1b699998235c1cfa16edbb50c2b774f983
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3417"></a>Compilerfehler C3417
'Member': Werttypen sind keine speziellen Memberfunktionen  
  
 Werttypen können keine Funktionen, z. B. eine Instanz der Standardkonstruktor, Destruktor oder Kopierkonstruktor enthalten.  
  
 Im folgende Beispiel wird C3517 generiert:  
  
```  
// C3417.cpp  
// compile with: /clr /c  
value class VC {  
   VC(){}   // C3417  
  
   // OK  
   static VC(){}  
   VC(int i){}  
};  
```
