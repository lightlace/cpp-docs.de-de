---
title: "VCPROFILE_ALLOC_SCALE"
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
  - "VCPROFILE_ALLOC_SCALE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VCPROFILE_ALLOC_SCALE-Umgebungsvariable"
ms.assetid: 5cb5ce27-f9b8-489b-b46c-d6e9bcab2d34
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
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