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
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: d5e6006c3951f8bc435e7a450347ed525d8bfcad
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="general-properties-linux-c"></a>Allgemeine Eigenschaften (Linux C++)

Eigenschaft | description | Auswahlmöglichkeiten
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
