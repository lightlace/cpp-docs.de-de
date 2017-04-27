---
title: Linkertoolfehler Lnk1104 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1104
dev_langs:
- C++
helpviewer_keywords:
- LNK1104
ms.assetid: 9ca6f929-0efc-4055-8354-3cf5b4e636dc
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: 7fce9c60da4bceafb9ee81231a8630acb4397d83
ms.lasthandoff: 04/24/2017

---
# <a name="linker-tools-error-lnk1104"></a>Linkertoolfehler LNK1104
Öffnen der Datei "*Filename*"  
  
Der Linker konnte die angegebene Datei nicht geöffnet werden.  
  
Um diesen Fehler zu beheben, überprüfen Sie die folgenden möglichen Ursachen:  
  
-   Die Datei *Filename* ist nicht vorhanden. Wenn Ihr Projekt auf einem anderen Projekt diese Datei erzeugen abhängig ist, stellen Sie sicher, dass Ihre projektabhängigkeiten richtig festgelegt sind.  
  
-   Bei Angabe von Bibliotheken im Dialogfeld Eigenschaftenseiten des Projekts müssen die Bibliotheksnamen durch Leerzeichen, nicht durch Kommas getrennt werden.  
  
-   Der Dateiname und der in der Befehlszeile angegebene Pfad ist falsch, oder der Pfad weist eine ungültige Laufwerksangabe. Überprüfen Sie die Schreibweise, und überprüfen Sie, den Dateinamen und Speicherort. Wenn Sie ein Projekt erstellen, die von einem anderen Computer kopiert wurde, überprüfen Sie die Pfade für die [VC++-Verzeichnisse Eigenschaftenseite](../../ide/vcpp-directories-property-page.md) und bei Bedarf zu aktualisieren.  
  
-   Die Bibliotheken für die Projektkonfiguration oder Plattformtoolset sind nicht installiert. Überprüfen Sie das Plattformtoolset und das Windows-SDK auf den Eigenschaftenseiten für das Projekt angegeben ist installiert und enthält das Toolset und Bibliotheken, die erforderlich sind, indem Sie Ihre Konfigurationseinstellungen. Es gibt separate Einstellungen für die Debug-und die Verkaufsversion, wenn Erstellung funktioniert, aber die andere einen Fehler verursacht, achten Sie darauf die Einstellungen richtig sind und die erforderlichen Tools für beide Konfigurationen installiert werden.  
  
-   Sie haben keine genügend Speicherplatz vorhanden. Es ist nicht ungewöhnlich, dass der Linker speicherintensiv temporären Speicherplatz während einer Verknüpfung.  
  
-   Sie haben nicht genügend Berechtigungen zum Zugreifen auf *Filename*.  
  
-   Der Pfad für *Filename* wird auf mehr als 260 Zeichen erweitert. Ändern Sie die Namen oder ordnen Sie die Verzeichnisstruktur neu an, bei Bedarf, um die Pfade zu den erforderlichen Dateien zu kürzen.  
  
-   Wenn die *Filename* heißt LNK*n*, also einen vom Linker für eine temporäre Datei generierten Dateinamen, die in der TMP-Umgebungsvariablen angegebene Verzeichnis ist möglicherweise nicht vorhanden oder kann mehr als ein Verzeichnis für die TMP-Umgebungsvariable angegeben werden. Nur ein Verzeichnispfad sollte für die TMP-Umgebungsvariable angegeben werden.  
  
-   Wenn die Fehlermeldung für einen Bibliotheksnamen auftritt und Sie kürzlich die MAK-Datei von einem früheren Microsoft Visual C++-Entwicklungssystem portiert haben, ist die Bibliotheksdatei möglicherweise nicht mehr gültig. Stellen Sie sicher, dass der Bibliotheksname richtig ist und noch am angegebenen Speicherort vorhanden ist, oder aktualisieren Sie die LIB-Pfad, um auf den neuen Speicherort zu verweisen.  
  
-   Möglicherweise ist die Datei in einem anderen Programm geöffnet, und der Linker kann nicht in sie schreiben. Oft blockiert Antivirusprogramme vorübergehend den Zugriff auf die neu erstellte Dateien. Versuchen Sie, Ihr Build Projektverzeichnisse von der Antivirenscanner ausschließen.  
  
-   Sie haben eine falsche LIB-Umgebungsvariable. Informationen zum Aktualisieren der LIB-Umgebungsvariablen finden Sie unter [VC++-Verzeichnisse Eigenschaftenseite](../../ide/vcpp-directories-property-page.md). Achten Sie darauf, dass hier alle benötigten Verzeichnisse mit Bibliotheken aufgeführt sind.  
  
-   Der Linker verwendet im verschiedenen Fällen temporäre Dateien. Auch wenn Sie über ausreichend Speicherplatz verfügen, kann eine sehr umfangreiche Verknüpfung ausschöpfen oder fragmentieren den verfügbare Speicherplatz. Erwägen Sie die [/OPT (Optimierungen)](../../build/reference/opt-optimizations.md) Option; auf diese Weise transitive Comdat-Eliminierung liest alle Objektdateien mehrfach.
