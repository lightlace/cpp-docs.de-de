---
title: "jitintrinsic | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "jitintrinsic"
  - "jitintrinsic_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec-Schlüsselwort [C++], jitintrinsic"
  - "jitintrinsic __declspec-Modifizierer"
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# jitintrinsic
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Markiert die Funktion als signifikant bei der 64\-Bit\-Common Language Runtime.  Dies wird in bestimmten Funktionen in von Microsoft bereitgestellten Bibliotheken verwendet.  
  
## Syntax  
  
```  
__declspec(jitintrinsic)  
```  
  
## Hinweise  
 `jitintrinsic` fügt ein MODOPT \(<xref:System.Runtime.CompilerServices.IsJitIntrinsic>\) zu einer Funktionssignatur hinzu.  
  
 Benutzern wird von der Verwendung dieses `__declspec`\-Modifizierers abgeraten, da unerwartete Ergebnisse auftreten können.  
  
## Siehe auch  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)