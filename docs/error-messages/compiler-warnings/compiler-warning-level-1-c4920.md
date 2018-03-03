---
title: Compilerwarnung (Stufe 1) C4920 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4920
dev_langs:
- C++
helpviewer_keywords:
- C4920
ms.assetid: 1e501f2e-93c1-4d27-a4fa-54fc86271ae7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c87237f5ac2240cfd2063c58055d626b72285287
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4920"></a>Compilerwarnung (Stufe 1) C4920
enum-Enumerationsmember 'member=value' ist bereits in der enum-Enumerarion als 'member=value' aufgetreten  
  
 Wenn in einer TLB-Datei, die Sie an '#import' übergeben, in zwei oder mehr Enumerationen das gleiche Symbol definiert ist, weist diese Warnung darauf hin, dass nachfolgende identische Symbole ignoriert werden und in der TLH-Datei auskommentiert werden.  
  
 Bei Zugrundelegung einer TLB-Datei, die folgendes enthält:  
  
```  
library MyLib  
{  
    typedef enum {  
        enumMember = 512  
    } AProblem;  
  
    typedef enum {  
        enumMember = 1024  
    } BProblem;  
};  
```  
  
 wird im folgenden Beispiel C4920 generiert,  
  
```  
// C4920.cpp  
// compile with: /W1  
#import "t4920.tlb"   // C4920  
  
int main() {  
}  
```