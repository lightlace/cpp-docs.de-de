---
title: "Mathematische Fehlerkonstanten"
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
  - "_PLOSS"
  - "_UNDERFLOW"
  - "_TLOSS"
  - "_SING"
  - "_DOMAIN"
  - "_OVERFLOW"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_DOMAIN-Konstante"
  - "_OVERFLOW-Konstante"
  - "_PLOSS-Konstante"
  - "_SING-Konstante"
  - "_TLOSS-Konstante"
  - "_UNDERFLOW-Konstante"
  - "DOMAIN-Konstante"
  - "Mathematische Fehlerkonstanten"
  - "OVERFLOW-Konstante"
  - "PLOSS-Konstante"
  - "SING-Konstante"
  - "TLOSS-Konstante"
  - "UNDERFLOW-Konstante"
ms.assetid: 4be933a6-674e-45a5-8ac9-090023542f5b
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Mathematische Fehlerkonstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
#include <math.h>  
  
```  
  
## Hinweise  
 Die mathematischen Routinen der Laufzeitbibliothek können mathematische Fehlerkonstanten generieren.  
  
 Diese Fehler, wie folgt beschrieben, entsprechen den Ausnahmetypen, die in MATH.H definiert und werden durch die `_matherr`\-Funktion zurückgegeben, wenn eine mathematische Fehler auftritt.  
  
|Konstante|Bedeutung|  
|---------------|---------------|  
|`_DOMAIN`|Das Argument umgehen äußere Domäne der Funktion.|  
|`_OVERFLOW`|Ergebnis ist zu groß, im Rückgabetyp der Funktion dargestellt.|  
|`_PLOSS`|Teilverlust an Signifikanz aufgetreten.|  
|`_SING`|Argumenteigenheit: Argument für Funktion verfügt über ungültige Wert. \(Beispiel, wird der Wert 0 übergeben, um zu arbeiten, der ungleich 0 \(null\) erfordert.\)|  
|`_TLOSS`|Gesamter Verlust des Schritts ist aufgetreten.|  
|`_UNDERFLOW`|Ergebnis ist zu klein dargestellt.|  
  
## Siehe auch  
 [\_matherr](../c-runtime-library/reference/matherr.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)