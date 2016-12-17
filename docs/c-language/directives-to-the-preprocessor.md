---
title: "Direktiven f&#252;r den Pr&#228;prozessor"
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
  - "C"
ms.assetid: adc6251e-cf6b-4508-bdbb-55f446c838d3
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Direktiven f&#252;r den Pr&#228;prozessor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

"Direktiven" weisen den C\-Präprozessor an, eine bestimmte Aktion für den Text des Programms vor der Kompilierung auszuführen.  [Präprozessordirektiven](../preprocessor/preprocessor-directives.md) sind vollständig in *Präprozessorverweis* beschrieben.  In diesem Beispiel wird die `#define`\-Präprozessordirektive verwendet:  
  
```  
#define MAX 100  
```  
  
 Diese Anweisung weist den Compiler an, vor der Kompilierung jedes Vorkommen von `MAX` durch `100` zu ersetzen.  Die Präprozessordirektiven des C\-Compilers sind:  
  
|\#define|\#endif|\#ifdef|\#line|  
|--------------|-------------|-------------|------------|  
|`#elif`|`#error`|**\#ifndef**|**\#pragma**|  
|`#else`|`#if`|`#include`|`#undef`|  
  
## Siehe auch  
 [Quelldateien und Quellprogramme](../c-language/source-files-and-source-programs.md)