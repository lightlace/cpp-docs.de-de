---
title: "pgosweep | Microsoft Docs"
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
  - "pgosweep (Programm)"
  - "Profilgesteuerte Optimierungen, pgosweep"
ms.assetid: f39dd3b7-1cd9-4c3b-8e8b-fb794744b757
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# pgosweep
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird in profilgesteuerter Optimierung verwendet, um alle Profildaten von einem laufenden Programm in die PGC\-Datei zu schreiben.  
  
## Syntax  
  
```  
pgosweep [options] image pgcfile  
```  
  
#### Parameter  
 `options`  
 Ein optionaler Parameter, der leer gelassen werden kann.  Die gültigen Werte für `options` sind:  
  
-   **\/?** oder **\/help,** zeigt die Hilfemeldung an.  
  
-   **\/noreset,** behält die Anzahl in den Laufzeitdatenstrukturen bei.  
  
 `image`  
 Der vollständige Pfad einer EXE\-Datei oder DLL\-Datei, die mit der \/LTCG:PGINSTRUMENT\-Compileroption erstellt wurde.  
  
 `pgcfile`  
 Die PGC\-Datei, in die dieser Befehl die Datenmenge schreibt.  
  
## Hinweise  
 Dieser Befehl funktioniert in Programmen, die mit der \/LTCG: PGINSTRUMENT\-Compileroption erstellt wurden.  Er unterbricht ein laufendes Programm und schreibt die Profildaten in eine neue PGC\-Datei.  Standardmäßig setzt der Befehl nach jedem Schreibvorgang die Anzahl zurück.  Wenn Sie die **\/noreset**\-Option angeben, zeichnet der Befehl die Werte auf, setzt sie aber im laufenden Programm nicht zurück.  Mit dieser Option erhalten Sie doppelte Daten, wenn Sie die Profildaten später abrufen.  
  
 Eine alternative Verwendung für `pgosweep` ist das Abrufen von Profilinformationen nur für die Laufzeit der Anwendung.  Zum Beispiel könnten Sie `pgosweep` ausführen, kurz nachdem Sie die Anwendung gestartet haben und diese Datei verwerfen.  Damit würden Profildaten entfernt, die mit Startkosten zusammenhängen.  Dann können Sie `pgosweep` vor dem Beenden der Anwendung ausführen.  Jetzt weisen die gesammelten Daten nur Profilinformationen von der Laufzeit auf.  
  
 Wenn Sie eine PGC\-Datei \(`pgcfile`\) benennen können Sie das Standardformat verwenden, das *appname\!n*.pgc ist.  Wenn dieses Format verwendet wird, findet der Compiler diese Daten in der \/LTCG:PGO\-Phase.  Wenn Sie das Standardformat nicht verwenden, müssen Sie die PGC\-Dateien mithilfe von [pgomgr](../../build/reference/pgomgr.md) zusammenführen.  
  
## Beispiel  
  
```  
pgosweep myapp.exe myapp!1.pgc  
```  
  
 In diesem Beispiel schreibt `pgosweep` die aktuellen Profilinformationen für myapp.exe in myapp\!1.pgc.  
  
## Siehe auch  
 [Tools für die profilgesteuerte Optimierung \(PGO\)](../../build/reference/tools-for-manual-profile-guided-optimization.md)