---
title: "Suchpfade in Regeln | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Rückschlussregeln in NMAKE"
  - "Regeln, Rückschluss"
  - "Suchpfade in NMAKE-Rückschlussregeln"
ms.assetid: 38feded6-536d-425d-bf40-fff3173a5506
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Suchpfade in Regeln
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

```  
{frompath}.fromext{topath}.toext:  
   commands  
```  
  
## Hinweise  
 Eine Rückschlussregel ist nur dann auf eine Abhängigkeit anwendbar, wenn die in der Abhängigkeit angegebenen Pfade genau mit den Pfaden der Rückschlussregel übereinstimmen.  Das Verzeichnis der abhängigen Datei wird in *frompath* und das Verzeichnis des Ziels in *topath* angegeben. Es sind keine Leerzeichen zulässig.  Nur ein Pfad pro Erweiterung soll angegeben werden.  Ein Pfad auf eine Erweiterung erfordert einen Pfad auf die andere Erweiterung.  Um das aktuelle Verzeichnis anzugeben, werden entweder ein Punkt \(.\) oder leere geschweifte Klammern \({ {\) verwendet.  Makros können *frompath* und *topath* repräsentieren; sie werden während des Präprozessorlaufs aufgerufen.  
  
## Beispiel  
  
### Code  
  
```  
{dbi\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUDBI) $<  
  
{ilstore\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $<  
  
{misc\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUPDB) $<  
  
{misc\}.c{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $<  
  
{msf\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $<  
  
{bsc\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUPDB) $<  
  
{mre\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUPDB) $<  
  
{namesrvr\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUPDB) $<  
  
{src\cvr\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $<  
```  
  
## Siehe auch  
 [Definieren einer Regel](../build/defining-a-rule.md)