---
title: "_fmode"
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
  - "fmode"
  - "_fmode"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Dateiübersetzung [C++], Standardmodus"
  - "fmode-Funktion"
  - "_fmode-Funktion"
ms.assetid: ac6df9eb-e5cc-4c54-aff3-373c21983118
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# _fmode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Variable `_fmode` wird der Standarddateiübersetzungsmodus für Text\- oder Binärdateiübersetzung fest.  Diese globale Variable ist für die sichereren funktionalen Versionen [\_get\_fmode](../c-runtime-library/reference/get-fmode.md) und [\_set\_fmode](../c-runtime-library/reference/set-fmode.md) veraltet, die anstelle der globalen Variable verwendet werden sollten.  Sie wird in Stdlib.h folgendermaßen deklariert.  
  
## Syntax  
  
```  
extern int _fmode;  
```  
  
## Hinweise  
 Die Standardeinstellung von `_fmode`  ist `_O_TEXT`  für Textmodusübersetzung.  `_O_BINARY`  ist die Einstellung für binären Modus.  
  
 Sie können den Wert von `_fmode` auf drei Arten ändern:  
  
-   Link mit Binmode.obj.  Dadurch ändert die ursprüngliche Einstellung von `_fmode` in `_O_BINARY` und führt alle Dateien mit Ausnahme von `stdin`, `stdout` und im binären Modus geöffnet werden sollen, `stderr`.  
  
-   Lassen Sie `_get_fmode` oder `_set_fmode` \- Aufruf die globale Variable `_fmode` abrufen oder festlegen, bzw.  
  
-   Ändern Sie den Wert von `_fmode` direkt, indem Sie sie in Ihrem Programm festlegen.  
  
## Siehe auch  
 [Globale Variablen](../c-runtime-library/global-variables.md)   
 [\_get\_fmode](../c-runtime-library/reference/get-fmode.md)   
 [\_set\_fmode](../c-runtime-library/reference/set-fmode.md)