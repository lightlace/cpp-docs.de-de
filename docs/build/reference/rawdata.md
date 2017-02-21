---
title: "/RAWDATA | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/rawdata"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/RAWDATA (dumpbin-Option)"
  - "Unformatierte Daten"
  - "RAWDATA (dumpbin-Option)"
  - "-RAWDATA (dumpbin-Option)"
ms.assetid: 41cba845-5e1f-415e-9fe4-604a52235983
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /RAWDATA
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/RAWDATA[:{1|2|4|8|NONE[,number]]  
```  
  
## Hinweise  
 Durch diese Option wird der unformatierte Inhalt jedes Abschnitts der Datei angezeigt.  Die Argumente steuern das Format der Anzeige, wie unten dargestellt:  
  
|Argument|Ergebnis|  
|--------------|--------------|  
|1|Der Standardwert.  Der Inhalt wird in hexadezimalen Bytes sowie zusätzlich als ASCII\-Zeichen angezeigt, wenn es eine druckbare Darstellung gibt.|  
|2|Der Inhalt wird in Form von 2\-Byte\-Hexadezimalwerten angezeigt.|  
|4|Der Inhalt wird in Form von 4\-Byte\-Hexadezimalwerten angezeigt.|  
|8|Der Inhalt wird in Form von 8\-Byte\-Hexadezimalwerten angezeigt.|  
|NONE|Unformatierte Daten werden unterdrückt.  Dieses Argument ist sinnvoll für die Steuerung der Ausgabe von **\/ALL**.|  
|*Zahl*|Die angezeigten Zeilen werden auf eine Länge festgelegt, die eine entsprechende Anzahl von Werten pro Zeile aufnehmen kann.|  
  
 Für Dateien, die mit der [\/GL](../../build/reference/gl-whole-program-optimization.md)\-Compileroption erstellt wurden, kann nur die DUMPBIN\-Option [\/HEADERS](../../build/reference/headers.md) verwendet werden.  
  
## Siehe auch  
 [DUMPBIN\-Optionen](../../build/reference/dumpbin-options.md)