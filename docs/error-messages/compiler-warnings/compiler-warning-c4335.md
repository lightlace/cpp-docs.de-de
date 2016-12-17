---
title: "Compilerwarnung C4335"
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
  - "C4335"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4335"
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung C4335
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mac\-Dateiformat erkannt: Konvertieren Sie die Quelldatei in das DOS\- oder UNIX\-Format  
  
 Das abschließende Zeichen der ersten Zeile einer Quelldatei entspricht dem Macintosh\-Format \(‘\\r’\) und nicht dem UNIX\-\(‘\\n’\) oder DOS\-\(‘\\r\\n’\) Format.  
  
 Diese Warnmeldung wird immer als Fehler ausgegeben.  Im [warning](../../preprocessor/warning.md)\-Pragma finden Sie weitere Informationen zum Deaktivieren dieser Warnung.  Zudem wird diese Warnung nur einmal pro Kompiliereinheit herausgegeben.  Wenn es mehrere `#include`\-Direktiven gibt, die Dateien im Macintosh\-Format angeben, wird C4335 somit nur einmal ausgegeben.  
  
 Eine Möglichkeit zur Erstellung von Dateien im Macintosh\-Format ist im Dialogfeld **Erweiterte Speicheroptionen** \(Menü **Datei**\) in Visual Studio enthalten.  
  
## Beispiel  
 Im folgenden Beispiel wird C4335 generiert.  
  
```  
// C4335 expected  
#include "c4335.h"   // assume both include files are in Macintosh format  
#include "c4335_2.h"  
```