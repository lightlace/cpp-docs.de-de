---
title: "Compilerwarnung (Stufe 1) C4794 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4794"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4794"
ms.assetid: badc9c36-fa1a-4fec-929b-7bfda7a7b79f
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerwarnung (Stufe 1) C4794
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Segment der Variable 'Variable' im lokalen Thread\-Speicher von 'Abschnittsname' nach '.tls$' verschoben  
  
 Sie haben [\#pragma data\_seg](../../preprocessor/data-seg.md) verwendet, um eine tls\-Variable in einem Abschnitt zu positionieren, der nicht mit „.tls$“ beginnt.  
  
 Der Abschnitt „.tls$*x*“ befindet sich in der Objektdatei, wo die [\_\_declspec\(thread\)](../../cpp/thread.md)\-Variablen definiert werden. Durch diese Abschnitte ergibt sich ein „.tls“\-Abschnitt in der EXE\- oder DLL\-Datei.  
  
## Beispiel  
 Im folgenden Beispiel wird C4794 generiert.  
  
```  
// C4794.cpp // compile with: /W1 /c #pragma data_seg(".someseg") __declspec(thread) int i;   // C4794 // OK #pragma data_seg(".tls$9") __declspec(thread) int j;  
```