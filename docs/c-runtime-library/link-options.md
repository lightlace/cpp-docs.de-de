---
title: "Linkoptionen"
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
helpviewer_keywords: 
  - "nothrownew.obj"
  - "newmode.obj"
  - "noenv.obj"
  - "psetargv.obj"
  - "loosefpmath.obj"
  - "smallheap.obj"
  - "fp10.obj"
  - "nochkclr.obj"
  - "chkstk.obj"
  - "pcommode.obj"
  - "pnoenv.obj"
  - "Linkoptionen [C++]"
  - "invalidcontinue.obj"
  - "pnothrownew.obj"
  - "pwsetargv.obj"
  - "pinvalidcontinue.obj"
  - "wsetargv.obj"
  - "binmode.obj"
  - "setargv.obj"
  - "noarg.obj"
  - "pnewmode.obj"
  - "commode.obj"
  - "pthreadlocale.obj"
  - "pbinmode.obj"
  - "threadlocale.obj"
  - "pnoarg.obj"
ms.assetid: 05b5a77b-9dd1-494b-ae46-314598c770bb
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Linkoptionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Verzeichnis CRT lib enthält einige kleine Objektdateien, die bestimmte CRT\-Funktionen ohne eine Codeänderung aktivieren.  Diese werden Linkoptionen" bezeichnet, da sie nur der Linkerbefehlszeile hinzufügen müssen, um sie zu verwenden.  
  
 Reine Modusversionen wurden hinzugefügt.  Verwenden Sie reguläre die Versionen für systemeigen und \/clr\- Code, verwenden die reinen Versionen \(mit dem Präfix einem P\) für \/clr:pure Modus.  
  
|Systemeigene und \/clr|Reiner Modus|**Beschreibung**|  
|----------------------------|------------------|----------------------|  
|binmode.obj|pbinmode.obj|Legt den Standarddateiübersetzungsmodus auf Binärdatei fest.  Siehe [\_fmode](../c-runtime-library/fmode.md).|  
|chkstk.obj|nicht verfügbar|Bietet StapelÜberprüfungs\- und allocaunterstützung wenn nicht mit CRT.|  
|commode.obj|pcommode.obj|Legt das globale Commitflag auf "\-" fest.  Weitere Informationen finden Sie unter [fopen, \_wfopen](../c-runtime-library/reference/fopen-wfopen.md) und [fopen\_s, \_wfopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md).|  
|fp10.obj|nicht verfügbar|Ändert das Standardgenauigkeitssteuerelement zu 64 Bits.  Siehe [Gleitkommaunterstützung](../c-runtime-library/floating-point-support.md).|  
|invalidcontinue.obj|pinvalidcontinue.obj|Legt einen ungültigen Parameterhandler standardmäßigen, der ohne konkrete fest heißt, dass ungültige Parameter von CRT\-Funktionen nur festlegen errno und zurückgeben ein Fehlerergebnis zurück übergeben.|  
|loosefpmath.obj|nicht verfügbar|Stellt sicher, dass Gleitkommacode denormal Werte zulässt.|  
|newmode.obj|pnewmode.obj|Veranlasst [malloc](../c-runtime-library/reference/malloc.md), den neuen Handler auf Fehler aufzurufen.  Siehe [\_set\_new\_mode](../c-runtime-library/reference/set-new-mode.md), [\_set\_new\_handler](../c-runtime-library/reference/set-new-handler.md), [calloc](../c-runtime-library/reference/calloc.md) und [realloc](../c-runtime-library/reference/realloc.md).|  
|noarg.obj|pnoarg.obj|Deaktiviert alle Verarbeitung von argc und von argv.|  
|nochkclr.obj|nicht verfügbar|Keine Aktion  Entfernen Sie aus dem Projekt.|  
|noenv.obj|pnoenv.obj|Deaktiviert die Erstellung einer zwischengespeicherten Umgebung für CRT.|  
|nothrownew.obj|pnothrownew.obj|Aktiviert die nicht\-auslösende Version von neuem im CRT.  Siehe [Operatoren "new" und "delete"](../cpp/new-and-delete-operators.md).|  
|setargv.obj|psetargv.obj|Ermöglicht Befehlszeilenargument\-Platzhaltererweiterung.  Siehe [Erweitern von Platzhalterargumenten](../c-language/expanding-wildcard-arguments.md).|  
|smalheap.obj|nicht verfügbar|Installiert einen sehr einfachen kleinen Heapmanager.|  
|threadlocale.obj|pthreadlocale.obj|Ermöglicht threadspezifisches Gebietsschema für alle neuen Threads standardmäßig.|  
|wsetargv.obj|pwsetargv.obj|Ermöglicht Befehlszeilenargument\-Platzhaltererweiterung.  Siehe [Erweitern von Platzhalterargumenten](../c-language/expanding-wildcard-arguments.md).|  
  
## Siehe auch  
 [CRT\-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)