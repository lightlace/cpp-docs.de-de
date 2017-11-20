---
title: "Vorgehensweise: Zusammenführen mehrerer PGO-Profile in einem einzigen Profil | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- merging profiles
- profile-guided optimizations, merging profiles
ms.assetid: aab686b5-59dd-40d1-a04b-5064690f65a6
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dcd10c25e4512683b840bd2feeee287995ab8776
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-merge-multiple-pgo-profiles-into-a-single-profile"></a>Gewusst wie: Zusammenführen mehrerer PGO-Profile in einem einzigen Profil
Profilgesteuerte Optimierung (PGO) eignet sich hervorragend zum Erstellen von optimierte Binärdateien, die basierend auf einem Szenario, das ein Profil erstellt wird. Aber was geschieht, wenn Sie eine Anwendung haben, die mehrere wichtige, noch unterschiedliche Szenarien hat. Erstellen Sie ein einzelnes Profil, das für die profilgesteuerte Optimierung verwenden, können wie in verschiedenen Szenarien? In Visual Studio übernimmt der PGO-Manager Pgomgr.exe diese Aufgabe.  
  
 Die Syntax für das Zusammenführen von Profilen lautet:  
  
```  
pgomgr /merge[:num] [.pgc_files] .pgd_files  
```  
  
 wobei `num` ist eine optionale Gewichtung, die bei dieser Zusammenführung verwendet wird. Gewichtungen werden häufig verwendet, wenn es gibt einige Szenarios wichtiger als andere sind oder es gibt Szenarien, die mehrere Male ausgeführt werden sollen.  
  
> [!NOTE]
>  PGO-Manager funktioniert nicht mit veralteten Profildaten. Um eine PGC-Datei in einer PGD-Datei zusammenzuführen, muss die PGC-Datei durch eine ausführbare Datei generiert das durch den Aufruf der gleiche Link erstellt wurde, die die PGD-Datei generiert.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der Manager für die profilgesteuerte Optimierung Datei Datei sechs Mal hinzugefügt werden.  
  
```  
pgomgr /merge:6 pgcFile.pgc pgdFile.pgd  
```  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der Manager für die profilgesteuerte Optimierung beiden Dateien Pgcdatei1.pgc und Pgcdatei2.PGC Datei zweimal für jeden PGC-Datei hinzufügen.  
  
```  
pgomgr /merge:2 pgcFile1.pgc pgcFile2.pgc pgdFile.pgd  
```  
  
## <a name="example"></a>Beispiel  
 Wenn der PGO-Manager, ohne eine PGC-Datei ausgeführt wird wird das lokale Verzeichnis für alle PGC-Dateien gesucht, die den gleichen Namen wie die PGD-Datei mit einem Ausrufezeichen (!), gefolgt von beliebigen Zeichen haben. Wenn das lokale Verzeichnis, Dateien test.pgd, Test! 1.pgc test2.pgc und Test! Hello.pgc hat und der folgende Befehl aus dem lokalen Verzeichnis ausgeführt wird, werden anschließend Test! 1.pgc und Test! Hello.pgc test.pgd zusammengeführt werden.  
  
```  
pgomgr /merge test.pgd  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Profilgesteuerte Optimierungen](../../build/reference/profile-guided-optimizations.md)