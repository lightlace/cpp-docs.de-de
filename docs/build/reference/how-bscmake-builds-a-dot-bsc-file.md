---
title: "Erstellen einer BSC-Datei mit BSCMAKE"
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
helpviewer_keywords: 
  - "Browserinformationsdateien (.bsc), Erstellen"
ms.assetid: 8512b33e-c856-44a2-87bd-01ab10b52a95
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Erstellen einer BSC-Datei mit BSCMAKE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

BSCMAKE versucht, bei der Erstellung bzw. Neuerstellung einer BSC\-Datei das effizienteste Verfahren anzuwenden.  Um mögliche Probleme zu vermeiden, ist es wichtig, den Buildprozess zu verstehen.  
  
 Beim Erstellen einer Browserinformationsdatei kürzt BSCMAKE die SBR\-Dateien auf Nulllänge.  Während eines nachfolgenden Erstellungsvorgangs für dieselbe Datei gibt eine SBR\-Datei mit Nulllänge \(oder leere SBR\-Datei\) die Information, dass diese SBR\-Datei keine neuen Beiträge enthält, an BSCMAKE weiter.  BSCMAKE entnimmt dieser Information, dass eine Aktualisierung dieses Teiles der Datei nicht erforderlich ist und ein inkrementelles Erstellen ausreicht.  Bei jedem Erstellungsvorgang versucht BSCMAKE zunächst, die Datei inkrementell zu aktualisieren und nur die SBR\-Dateien zu verwenden, die sich geändert haben. Dabei wird vorausgesetzt, dass die \/n\-Option nicht angegeben ist.  
  
 BSCMAKE sucht nach einer BSC\-Datei, deren Name mit der \/o\-Option angegeben ist.  Wenn \/o nicht angegeben ist, sucht BSCMAKE nach einer Datei, die den Basisnamen der ersten SBR\-Datei und die Erweiterung BSC besitzt.  Ist diese Datei vorhanden, erstellt BSCMAKE die Browserinformationsdatei inkrementell. Dabei werden lediglich die beitragenden SBR\-Dateien verwendet.  Wenn diese Datei nicht vorhanden ist, führt BSCMAKE einen vollständigen Erstellungsvorgang mit allen SBR\-Dateien aus.  Für den Erstellungsvorgang gelten folgende Regeln:  
  
-   Für einen erfolgreichen, vollständigen Erstellungsvorgang müssen alle angegebenen SBR\-Dateien vorhanden und dürfen nicht abgeschnitten sein.  Eine abgeschnittene SBR\-Datei muss vor dem Ausführen von BSCMAKE neu erstellt werden, indem sie neu kompiliert oder assembliert wird.  
  
-   Für einen erfolgreichen inkrementellen Erstellungsvorgang muss die BSC\-Datei vorhanden sein.  Alle beitragenden SBR\-Dateien, auch wenn diese leer sind, müssen vorhanden und in der BSCMAKE\-Befehlszeile angegeben sein.  Wenn Sie eine SBR\-Datei nicht in der Befehlszeile angeben, entfernt BSCMAKE deren Beitrag aus der Datei.  
  
## Siehe auch  
 [Erstellen einer BSC\-Datei](../../build/reference/building-a-dot-bsc-file.md)