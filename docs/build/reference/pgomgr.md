---
title: "pgomgr"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pgomgr (Programm)"
  - "Profilgesteuerte Optimierungen, pgomgr"
ms.assetid: 74589126-df18-42c9-8739-26d60e148d6a
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "corob"
manager: "ghogen"
---
# pgomgr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fügt der PGD\-Datei Profildaten aus einer oder mehreren PGC\-Dateien hinzu.  
  
## Syntax  
  
```  
pgomgr [options] pgcfiles pgdfile  
```  
  
#### Parameter  
 `options`  
 Die folgenden Optionen können für pgomgr angegeben werden:  
  
 **\/help—**: Zeigt die verfügbaren pgomgr\-Optionen an \(Kurzform von \/?\).  
  
 **\/clear—**: Veranlasst, dass alle Profilinformationen in der PGD\-Datei gelöscht werden.  Mit der Option **\/clear** können Sie keine PGC\-Datei angeben.  
  
 **\/detail**: Zeigt eine ausführliche Statistik an, einschließlich eines Verlaufsdiagramms der Abdeckungsinformationen.  
  
 **\/summary**: Zeigt Statistiken für einzelne Funktionen an.  
  
 **\/unique**: Bei Verwendung mit **\/summary** werden ergänzte Funktionsnamen angezeigt.  Wenn \/unique nicht angegeben wird, werden nicht ergänzte Funktionsnamen angezeigt.  
  
 **\/merge**\[**:***n*\]**:**Bewirkt, dass die Daten der PGC\-Datei\(en\) der PGD\-Datei hinzugefügt werden.  Mit dem optionalen Parameter *n* können Sie angeben, dass die Daten *n* Mal hinzugefügt werden sollen.  Wenn z. B. ein Szenario normalerweise sechsmal ausgeführt würde, können Sie es einmal in einem Testlauf ausführen und es mit **pgomgr \/merge:6** sechsmal der PGD\-Datei hinzufügen.  
  
 `pgcfiles`  
 Eine oder mehrere PGC\-Dateien, deren Profildaten Sie in der PGD\-Datei zusammenführen möchten.  Sie können eine oder mehrere PGC\-Dateien angeben.  Wenn Sie keine PGC\-Dateien angeben, werden alle PGC\-Dateien mit demselben Dateinamen wie die PGD\-Datei von pgomgr zusammengeführt.  
  
 `pgdfile`  
 Die PGD\-Datei, in der Sie Daten aus einer oder mehreren PGC\-Dateien zusammenführen.  
  
## Hinweise  
  
> [!NOTE]
>  Sie können dieses Tool nur von der [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]\-Eingabeaufforderung aus starten.  Sie können es nicht von einer Systemeingabeaufforderung oder vom Datei\-Explorer aus starten.  
  
## Beispiel  
 Im folgenden Beispiel wurden die Profildaten aus der PGD\-Datei gelöscht.  
  
```  
pgomgr /clear myapp.pgd  
```  
  
 Im folgenden Beispiel wurden die Profildaten aus myapp1.pgc der PGD\-Datei dreimal hinzufügt.  
  
```  
pgomgr /merge:3 myapp1.pgc myapp.pgd  
```  
  
 Im folgenden Beispiel werden die Profildaten aller myapp\#.pgc\-Dateien der Datei myapp.pgd hinzugefügt.  
  
```  
pgomgr -merge myapp1.pgd  
```  
  
## Siehe auch  
 [Tools für die profilgesteuerte Optimierung \(PGO\)](../../build/reference/tools-for-manual-profile-guided-optimization.md)