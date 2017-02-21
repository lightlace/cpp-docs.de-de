---
title: "Gewusst wie: Zusammenf&#252;hren mehrerer PGO-Profile in einem einzigen Profil | Microsoft Docs"
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
  - "Zusammenführen von Profilen"
  - "Profilgesteuerte Optimierungen, Zusammenführen von Profilen"
ms.assetid: aab686b5-59dd-40d1-a04b-5064690f65a6
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Gewusst wie: Zusammenf&#252;hren mehrerer PGO-Profile in einem einzigen Profil
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die profilgesteuerte Optimierung \(PGO\) ist ein hilfreiches Tool, um auf der Grundlage eines Szenarios mit Profilen optimierte Binärdateien zu erstellen.  Es stellt sich jedoch die Frage, was man im Falle mehrerer wichtiger Szenarios für eine Anwendung tun kann, die sich voneinander unterschieden. Wie kann aus den verschiedenen Szenarios ein einziges Profil erstellt werden, das PGO verwenden kann?  In Visual Studio übernimmt der PGO\-Manager "Pgomgr.exe" diese Aufgabe.  
  
 Die Syntax für das Zusammenführen von Profilen sieht folgendermaßen aus:  
  
```  
pgomgr /merge[:num] [.pgc_files] .pgd_files  
```  
  
 Dabei ist `num` eine optionale Gewichtung, die bei dieser Zusammenführung verwendet werden soll.  Gewichte werden häufig verwendet, wenn einige Szenarios wichtiger als andere sind oder wenn vorhandene Szenarios mehrfach ausgeführt werden.  
  
> [!NOTE]
>  Der PGO\-Manager funktioniert nicht mit veralteten Profildaten.  Um eine PGC\-Datei mit einer PGD\-Datei zusammenzuführen, muss die PGC\-Datei von einer ausführbaren Datei generiert werden, die mit demselben Aufruf des Linkers erstellt wurde, mit dem auch die PGD\-Datei generiert wurde.  
  
## Beispiel  
 In diesem Beispiel fügt der PGO\-Manager der Datei pgdDatei.pgd sechsmal die Datei pgcDatei.pgc hinzu.  
  
```  
pgomgr /merge:6 pgcFile.pgc pgdFile.pgd  
```  
  
## Beispiel  
 In diesem Beispiel fügt der PGO\-Manager der Datei pgdDatei.pgd jede der beiden Dateien pgcDatei1.pgc und pgcDatei2.pgc zweimal hinzu.  
  
```  
pgomgr /merge:2 pgcFile1.pgc pgcFile2.pgc pgdFile.pgd  
```  
  
## Beispiel  
 Wenn der PGO\-Manager ohne eine PGC\-Datei ausgeführt wird, sucht er im lokalen Verzeichnis nach allen PGC\-Dateien, die den gleichen Namen wie die PGD\-Datei besitzen, gefolgt von einem Ausrufezeichen \(\!\) und beliebigen weiteren Zeichen.  Wenn im lokalen Verzeichnis die Dateien test.pgd, test\!1.pgc, test2.pgc und test\!hello.pgc vorhanden sind und im lokalen Verzeichnis der folgende Befehl ausgeführt wird, werden test\!1.pgc und test\!hello.pgc in der Datei test.pgd zusammengeführt.  
  
```  
pgomgr /merge test.pgd  
```  
  
## Siehe auch  
 [Profilgesteuerte Optimierungen \(PGO\)](../../build/reference/profile-guided-optimizations.md)