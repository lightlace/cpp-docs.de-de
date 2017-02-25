---
title: "Compilerwarnung (Stufe 1) C4920 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4920"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4920"
ms.assetid: 1e501f2e-93c1-4d27-a4fa-54fc86271ae7
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4920
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

enum\-Enumerationsmember 'member\=value' ist bereits in der enum\-Enumerarion als 'member\=value' aufgetreten  
  
 Wenn in einer TLB\-Datei, die Sie an '\#import' übergeben, in zwei oder mehr Enumerationen das gleiche Symbol definiert ist, weist diese Warnung darauf hin, dass nachfolgende identische Symbole ignoriert werden und in der TLH\-Datei auskommentiert werden.  
  
 Bei Zugrundelegung einer TLB\-Datei, die folgendes enthält:  
  
```  
library MyLib { typedef enum { enumMember = 512 } AProblem; typedef enum { enumMember = 1024 } BProblem; };  
```  
  
 wird im folgenden Beispiel C4920 generiert,  
  
```  
// C4920.cpp // compile with: /W1 #import "t4920.tlb"   // C4920 int main() { }  
```