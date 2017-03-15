---
title: "Compilerfehler C2489 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2489"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2489"
ms.assetid: 67d8cd98-db7e-4f7f-86b4-4af7bc89ec8b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2489
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Initialisierte automatische oder Registervariable ist im Funktionsgültigkeitsbereich einer 'naked'\-Funktion nicht erlaubt  
  
 Weitere Informationen finden Sie unter [naked](../../cpp/naked-cpp.md).  
  
 Im folgenden Beispiel wird C2489 generiert:  
  
```  
// C2489.cpp  
// processor: x86  
__declspec( naked ) int func() {  
   int i = 1;   // C2489  
   register int j = 1;   // C2489  
}  
```