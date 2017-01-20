---
title: "Gleitkommaunterst&#252;tzung f&#252;r &#228;lteren Code (Visual C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: a2a26b96-7bc2-418a-981a-51aa1a0294a2
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Gleitkommaunterst&#252;tzung f&#252;r &#228;lteren Code (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die MMX\- und Gleitkomma\-Stapelregister \(MM0\-MM7\/ST0\-ST7\) werden durch Kontextschalter beibehalten.  Es gibt keine explizite Aufrufkonvention für diese Register.  Die Verwendung dieser Register ist im Kernelmoduscode in keinem Fall zulässig.  
  
## Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)