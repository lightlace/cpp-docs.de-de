---
title: Allgemeine Eigenschaften (Linux C++-Projekt) | Microsoft Docs
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56c800a9-3df9-4196-87b2-81adb00e4767
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.VCConfiguration.OutputDirectory
- VC.Project.VCConfiguration.IntermediateDirectory
- VC.Project.VCConfiguration.TargetName
- VC.Project.VCConfiguration.TargetExt
- VC.Project.VCConfiguration.DeleteExtensionsOnClean
- VC.Project.VCConfiguration.PlatformToolset
- VC.Project.VCConfiguration.BuildLogFile
- VC.Project.VCConfiguration.ConfigurationType
- VC.Project.VCConfiguration.UseOfSTL
ms.openlocfilehash: 4de08a00ddedf1eec97d1872646a986e09c22547
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2017
---
# <a name="general-properties-linux-c"></a>Allgemeine Eigenschaften (Linux C++)

Eigenschaft | Beschreibung | Auswahlmöglichkeiten
--- | ---| ---
Ausgabeverzeichnis | Gibt einen relativen Pfad zum Ausgabedateiverzeichnis an. Kann Umgebungsvariablen enthalten.
Zwischenverzeichnis | Gibt einen relativen Pfad zum Zwischendateiverzeichnis an. Kann Umgebungsvariablen enthalten.
Target Name | Gibt einen Dateinamen an, den dieses Projekt generiert.
Zielerweiterung | Gibt eine Dateierweiterung an, die dieses Projekt generiert. (Beispiel: .a)
Bei der Bereinigung zu löschende Erweiterungen | Durch Semikolons getrennte Platzhalterspezifikation, die angibt, welche Dateien im Zwischenverzeichnis beim Bereinigen oder erneuten Erstellen gelöscht werden sollen.
Buildprotokolldatei | Gibt die zu schreibende Buildprotokolldatei an, wenn die Buildprotokollierung aktiviert ist.
Plattformtoolset | Gibt das Toolset zum Erstellen der aktuellen Konfiguration an. Wenn keine Angabe erfolgt, wird das Standardtoolset verwendet.
Remotebuildcomputer | Der Zielcomputer oder das Gerät, der bzw. das für den Remotebuild, die Bereitstellung und das Debuggen verwendet werden soll.
Remotebuild-Stammverzeichnis | Gibt einen Pfad zu einem Verzeichnis auf dem Remotecomputer oder -Gerät an.
Remotebuild-Projektverzeichnis | Gibt einen Pfad zu einem Verzeichnis auf dem Remotecomputer oder -Gerät für das Projekt an.
Konfigurationstyp | Gibt den Typ der Ausgabe an, die diese Konfiguration generiert. | **Dynamische Bibliothek (.so)**: Dynamische Bibliothek (.so)<br>**Statische Bibliothek (.a)**: Statische Bibliothek (.a)<br>**Anwendung (.out)**: Anwendung (.out)<br>**Makefile**: Makefile<br>
Verwendung von STL | Gibt an, welche C++-Standardbibliothek für diese Konfiguration verwendet werden soll. | **Freigegebene GNU C++-Standardbibliothek**<br>**Statische GNU C++-Standardbibliothek (-static)**<br>
