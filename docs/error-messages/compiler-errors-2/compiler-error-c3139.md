---
title: "Compilerfehler C3139"
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
  - "C3139"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3139"
ms.assetid: 95c92263-10ac-4ff3-b385-6312dd92adbc
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3139
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Struktur': Ein UDT kann nicht ohne Member exportiert werden  
  
 Sie haben versucht, das [export](../../windows/export.md)\-Attribut auf einen leeren UDT \(benutzerdefinierten Typ\) anzuwenden.  Beispiel:  
  
```  
// C3139.cpp  
#include "unknwn.h"  
[emitidl];  
[module(name=xx)];  
  
[export] struct MyStruct {   // C3139 empty type  
};  
int main(){}  
```