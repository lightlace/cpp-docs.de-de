---
title: "Compilerfehler C2218"
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
  - "C2218"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2218"
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2218
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"\_\_vectorcall" kann nicht zusammen mit "\/arch:IA32" verwendet werden.  
  
 Die Aufrufkonvention `__vectorcall` wird nur in systemeigenem Code auf x86\- und x64\-Prozessoren unterstützt, die zusätzlich SIMD\-Streamingerweiterungen 2 \(SSE2\) und höher einschließen.  Weitere Informationen finden Sie unter [\_\_vectorcall](../../cpp/vectorcall.md).  
  
 Um diesen Fehler zu beheben, ändern Sie die Compileroptionen in die Befehlssätze Ziel SSE2, AVX oder AVX2.  Weitere Informationen finden Sie unter [\/arch \(x86\)](../../build/reference/arch-x86.md).