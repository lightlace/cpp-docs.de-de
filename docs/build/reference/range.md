---
title: "/RANGE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/RANGE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/RANGE (dumpbin-Option)"
  - "-RANGE (dumpbin-Option)"
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /RANGE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn \/RANGE mit anderen dumpbin\-Optionen wie \/RAWDATA oder \/DISASM verwendet wird, dient diese Option dem Ändern der Ausgabe von dumpbin.  
  
## Syntax  
  
```  
/RANGE:vaMin[,vaMax]  
```  
  
## Flags  
 **vaMin**  
 Die virtuelle Adresse, an der die dumpbin\-Operation starten soll.  
  
 **vaMax** \(optional\)  
 Die virtuelle Adresse, an der die dumpbin\-Operation beendet werden soll.  Wenn dieser Parameter nicht angegeben wird, wird dumpbin bis zum Ende der Datei ausgeführt.  
  
## Hinweise  
 Um die virtuellen Adressen für ein Bild anzuzeigen, verwenden Sie die Zuordnungsdatei für das Bild \(RVA \+ Basis\), die **\/DISASM**\-Option oder **\/HEADERS**\-Option von dumpbin oder im Visual Studio\-Debugger das Disassemblyfenster.  
  
## Beispiel  
 In diesem Beispiel wird mit **\/range** die Anzeige der **\/disasm**\-Option geändert.  Der Startwert wird in diesem Beispiel als Dezimalzahl ausgedrückt, und der Endwert wird als Hexadezimalzahl angegeben.  
  
```  
dumpbin /disasm /range:4219334,0x004061CD t.exe  
```  
  
## Siehe auch  
 [DUMPBIN\-Optionen](../../build/reference/dumpbin-options.md)