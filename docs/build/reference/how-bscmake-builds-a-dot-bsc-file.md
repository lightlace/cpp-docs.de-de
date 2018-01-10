---
title: Wie BSCMAKE erstellt ein. BSC-Datei | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: browse information files (.bsc), building
ms.assetid: 8512b33e-c856-44a2-87bd-01ab10b52a95
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cb8e03bed85a5e466a3c41f0cffc51d35c4b4561
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-bscmake-builds-a-bsc-file"></a>Erstellen einer BSC-Datei mit BSCMAKE
BSCMAKE erstellt oder neu erstellt eine BSC-Datei in die effizienteste Methode können. Um potenzielle Probleme zu vermeiden, ist es wichtig zu verstehen, die Build-Prozesses.  
  
 Wenn eine Browseinformationsdatei von BSCMAKE erstellt wird, schneidet die SBR-Dateien, um die Länge 0. Während einer nachfolgenden Builds der gleichen Datei weist eine leere (oder leer) SBR-Datei BSCMAKE, dass die SBR-Datei keine neuen Beiträge. Sie können wissen, dass ein Update dieses Teils der Datei nicht erforderlich ist und ein inkrementeller Build ausreicht, BSCMAKE. Bei jedem Build (es sei denn, die/n-Option angegeben ist), BSCMAKE zuerst versucht wird, aktualisieren die Datei inkrementell, mit der nur die SBR-Dateien, die geändert wurden.  
  
 BSCMAKE sucht nach einer BSC-Datei, die den Namen, die mit der/o-Option angegeben hat. Wenn/o nicht angegeben wird, sucht BSCMAKE für eine Datei mit den Basisnamen der ersten SBR-Datei mit der Erweiterung BSC. Wenn die Datei vorhanden ist, führt BSCMAKE der Browserinformationsdatei, die nur die zugehörigen SBR-Dateien mit einen inkrementellen Build aus. Wenn die Datei nicht vorhanden ist, führt BSCMAKE einen vollständigen Build mit allen SBR-Dateien. Die Regeln für Builds sind wie folgt aus:  
  
-   Für einen vollständigen Build erfolgreich ist alle angegebenen SBR-Dateien müssen vorhanden sein und müssen nicht abgeschnitten werden. Wenn eine SBR-Datei abgeschnitten ist, müssen Sie ihn neu erstellen (durch erneutes kompilieren oder Assemblieren) vor dem Ausführen von BSCMAKE.  
  
-   Für inkrementelle Builds erfolgreich ausgeführt werden kann muss die BSC-Datei vorhanden sein. Alle zugehörigen SBR-Dateien, dies gilt auch für leere Dateien, muss vorhanden sein und muss in der BSCMAKE-Befehlszeile angegeben werden. Wenn Sie eine SBR-Datei über die Befehlszeile weglassen, wird BSCMAKE seinen Beitrag aus der Datei entfernt.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen einer BSC-Datei](../../build/reference/building-a-dot-bsc-file.md)