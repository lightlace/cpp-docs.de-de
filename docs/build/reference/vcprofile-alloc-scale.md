---
title: "VCPROFILE_ALLOC_SCALE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VCPROFILE_ALLOC_SCALE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VCPROFILE_ALLOC_SCALE-Umgebungsvariable"
ms.assetid: 5cb5ce27-f9b8-489b-b46c-d6e9bcab2d34
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# VCPROFILE_ALLOC_SCALE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ändern Sie den für die Profildaten belegten Arbeitsspeicher.  
  
## Syntax  
  
```  
VCPROFILE_ALLOC_SCALE=scale_value  
```  
  
#### Parameter  
 `scale_value`  
 Der Skalierungswert für den Arbeitsspeicher, den Sie für die Ausführung von Testszenarien reservieren möchten.  Standardwert: 1.  
  
## Hinweise  
 In seltenen Fällen kann es vorkommen, dass während der Ausführung von Testszenarien der freie Arbeitsspeicher für die Erfassung von Profildaten nicht ausreicht.  In diesem Fall können Sie den verfügbaren Arbeitsspeicher mit `VCPROFILE_ALLOC_SCALE` erhöhen.  
  
 Wenn bei einem Testlauf aufgrund von unzureichendem Arbeitspeicher eine Fehlermeldung ausgegeben wird, weisen Sie `VCPROFILE_ALLOC_SCALE` einen höheren Wert zu, bis der Testlauf ohne eine solche Fehlermeldung ausgeführt und abgeschlossen wird.  
  
## Beispiel  
  
```  
set VCPROFILE_ALLOC_SCALE=2  
```  
  
## Siehe auch  
 [Umgebungsvariablen für profilgesteuerte Optimierungen](../../build/reference/environment-variables-for-profile-guided-optimizations.md)