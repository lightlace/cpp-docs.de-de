---
title: Compilerfehler C2838 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2838
dev_langs:
- C++
helpviewer_keywords:
- C2838
ms.assetid: 176b2ad6-7a84-4019-b97e-328866054457
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 75f6cdae94cd1be386fbe6af2cc492404162d0d7
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2838"></a>Compilerfehler C2838
'Member': Unzulässiger gekennzeichneter Name in Memberdeklaration  
  
 Eine Klasse, Struktur oder Union verwendet einen vollqualifizierten Namen zum Deklarieren Sie ein Mitglied einer anderen Klasse, Struktur oder Union.  
  
 Im folgende Beispiel wird C2838 generiert:  
  
```  
// C2838.cpp  
// compile with: /c  
class Bellini {  
public:  
    void Norma();  
};  
  
class Bottesini {  
   Bellini::Norma();  // C2838  
};  
```
