---
title: ".DOSSEG"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - ".DOSSEG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".DOSSEG directive"
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# .DOSSEG
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sortiert die Segmente in der MS\-DOS Segment konvention: CODE nicht in Segmente dann zuerst, und klicken Sie dann DGROUP Segmenten in DGROUP.  
  
## Syntax  
  
```  
  
.DOSSEG  
  
```  
  
## Hinweise  
 Die Segmente in DGROUP folgenden Reihenfolge ausführen: Segmente nicht in BSS oder im STAPEL, BSS\-Segmente IN und schließlich den STAPEL segmenten.  Hauptsächlich wird für die Gewährleistung von CodeView\-Unterstützung in eigenständige Programme MASM.  Identisch mit [DOSSEG](../../assembler/masm/dosseg.md).  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)