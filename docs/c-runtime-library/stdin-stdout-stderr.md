---
title: "stdin, stdout, stderr"
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
  - "stdin"
  - "stderr"
  - "stdout"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Standardfehlerstream"
  - "Standardeingabestream"
  - "Standardausgabestream"
  - "stderr-Funktion"
  - "stdin-Funktion"
  - "stdout-Funktion"
ms.assetid: badd4735-596d-4498-857c-ec8b7e670e4c
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# stdin, stdout, stderr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
      FILE *stdin;   
FILE *stdout;   
FILE *stderr;   
#include <stdio.h>  
```  
  
## Hinweise  
 Diese sind Standardstreams für Eingaben, Ausgaben und Fehlerausgabe.  
  
 Standardmäßig wird von der Standardeingabe Tastatur gelesen, während Standardausgabe und Standardfehler dem Bildschirm gedruckt werden.  
  
 Die folgenden Stream\-Zeiger sind verfügbar, auf die Standardstreams zuzugreifen:  
  
|Zeiger|Stream|  
|------------|------------|  
|`stdin`|Standardeingabe|  
|**stdout**|Standardausgabe|  
|`stderr`|Standardfehler|  
  
 Diese Zeiger können als Argumente an Funktionen verwendet werden.  Einige Funktionen, wie **getchar** und `putchar`, verwenden `stdin` und **stdout** automatisch.  
  
 Diese Zeiger sind Konstanten und können neuen Werte nicht zugewiesen werden.  Die `freopen`\-Funktion kann verwendet werden, um die Streams auf Datenträgerdateien oder anderen Medien umzuleiten.  Das Betriebssystem ermöglicht es Ihnen, einen typisierten Standardeinstellung des Programms und Ausgabe umleiten auf der Befehlsebene.  
  
## Siehe auch  
 [Stream\-E\/A](../c-runtime-library/stream-i-o.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)