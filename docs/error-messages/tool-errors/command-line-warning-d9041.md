---
title: "Befehlszeilenwarnung D9041 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "D9041"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9041"
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# Befehlszeilenwarnung D9041
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ungültiger Wert "Wert" für "\/Option"; "Wert" wird angenommen; bei Angabe dieser Warnung Befehlszeilenoptionen durch \/analyze ergänzen  
  
 Es wurde eine Codeanalysewarnungsnummer zur Befehlszeilenoption **\/wd**, **\/we**, **\/wo** oder **\/wl** hinzugefügt, ohne die Befehlszeilenoption **\/analyze** anzugeben.  Um den Fehler zu beheben, fügen Sie entweder die Befehlszeilenoption **\/analyze** hinzu oder entfernen die ungültige Warnungsnummer aus der entsprechenden **\/w**\-Befehlszeilenoption.  
  
## Beispiel  
 Im folgenden Befehlszeilenbeispiel wird die Warnung D9041 generiert:  
  
```  
cl /EHsc /LD /wd6001 filename.cpp  
```  
  
 Um die Warnung zu vermeiden, fügen Sie die Befehlszeilenoption **\/analyze** hinzu.  Wenn **\/analyze** von Ihrer Version des Compilers nicht unterstützt wird, entfernen Sie die ungültige Warnungsnummer aus der Befehlszeilenoption **\/wd**.  
  
## Siehe auch  
 [Befehlszeilenfehler D8000 bis D9000](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)