---
title: "Compilerfehler C2537"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2537"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2537"
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2537
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Spezifizierer': Unzulässige Angabe für Bindung  
  
 Mögliche Ursachen:  
  
1.  Der Bindungsspezifizierer wird nicht unterstützt.  Es wird nur der C\-Bindungsspezifizierer unterstützt.  
  
2.  Die C\-Bindung wurde für mehr als eine Funktion aus einer Gruppe überladener Funktionen angegeben.  Dies ist nicht zulässig.  
  
 Im folgenden Beispiel wird C2537 generiert:  
  
```  
// C2537.cpp  
// compile with: /c  
extern "c" void func();   // C2537  
extern "C" void func2();   // OK  
```