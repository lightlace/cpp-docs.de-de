---
title: "Compilerfehler C2341"
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
  - "C2341"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2341"
ms.assetid: aa2a7da5-e1c8-4225-9939-5bdc50158f31
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2341
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Abschnittsname': Das Segment muss vor der Verwendung mit \#pragma data\_seg, code\_seg oder section definiert werden  
  
 Eine [allocate](../../cpp/allocate.md)\-Anweisung bezieht sich auf ein Segment, das noch nicht durch die Pragmas [code\_seg](../../preprocessor/code-seg.md), [data\_seg](../../preprocessor/data-seg.md) oder [section](../../preprocessor/section.md) definiert wurde.  
  
 Im folgenden Beispiel wird C2341 generiert:  
  
```  
// C2341.cpp  
// compile with: /c  
__declspec(allocate(".test"))   // C2341  
int j = 1;  
```  
  
 Mögliche Lösung:  
  
```  
// C2341b.cpp  
// compile with: /c  
#pragma data_seg(".test")  
__declspec(allocate(".test"))  
int j = 1;  
```