---
title: Remotearchiveigenschaften (C++ Linux) | Microsoft Docs
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ee1e44c-8337-4c3a-b2f3-35e4be954f9f
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.Ar.CreateIndex
- VC.Project.Ar.CreateThinArchive
- VC.Project.Ar.NoWarnOnCreate
- VC.Project.Ar.TruncateTimestamp
- VC.Project.Ar.SuppressStartupBanner
- VC.Project.Ar.Verbose
- vc.project.AdditionalOptionsPage
- VC.Project.Ar.OutputFile
- VC.Project.VCConfiguration.BuildLogFile
ms.openlocfilehash: 402fa1f752b311014c828027e45a92a3dc6a2917
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2017
---
# <a name="remote-archive-properties-c-linux"></a>Remotearchiveigenschaften (C++ Linux)

Eigenschaft | Beschreibung
--- | ---
Erstellen eines Archivindex | Erstellt einen Archivindex (vgl. ranlib).  Dies kann das Linken beschleunigen und die Abhängigkeit innerhalb der eigenen Bibliothek verringern.
Schlankes Archiv erstellen | Erstellt ein schlankes Archiv.  Ein schlankes Archiv enthält relative Pfade zu den Objekten, anstatt die Objekte einzubetten.  Um zwischen schlank und normal zu wechseln, muss die vorhandene Bibliothek gelöscht werden.
Keine Warnung beim Erstellen | Gibt keine Warnung aus, wenn die Bibliothek erstellt wird.
Zeitstempel abschneiden | Verwendet NULL für Zeitstempel und UIDs/GIDs.
Startbanner unterdrücken | Zeigt die Versionsnummer nicht an.
Ausführlich | Ausführlich
Zusätzliche Optionen | Zusätzliche Optionen.
Ausgabedatei | Die Option /OUT überschreibt den Standardnamen und den Speicherort des Programms, das die Bibliothek erstellt.
Archivierungsprogramm | Gibt das Programm an, das beim Linken statischer Objekte aufgerufen werden soll, oder den Pfad zum Archivierungsprogramm auf dem Remotesystem.
Archivierungsprogrammtimeout | Remote-Archivierungsprogrammtimeout in Millisekunden.
Ausgabe kopieren | Gibt an, ob die Buildausgabedatei vom Remotesystem auf den lokalen Computer kopiert werden soll.
