---
title: "Compilerfehler C2393 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2393"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2393"
ms.assetid: 4bd95728-e813-4ce8-844a-c6ebe235ca82
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C2393
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Symbol' : Ein anwendungsdomänenspezifisches Symbol kann nicht in Segment 'Segment' zugewiesen werden  
  
 Die Verwendung von [appdomain](../../cpp/appdomain.md)\-Variablen setzt voraus, dass Sie mit **\/clr:pure** oder **\/clr:safe** kompilieren. Ein safe\- oder pure\-Bild kann jedoch keine Datensegmente enthalten.  
  
 Weitere Informationen finden Sie unter [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C2393 generiert.  
  
```  
// C2393.cpp  
// compile with: /clr:pure /c  
#pragma data_seg("myseg")  
int n = 0;   // C2393  
```