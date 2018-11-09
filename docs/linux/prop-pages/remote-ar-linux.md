---
title: Remotearchiveigenschaften (C++ Linux)
ms.date: 9/26/2017
ms.assetid: 5ee1e44c-8337-4c3a-b2f3-35e4be954f9f
f1_keywords: []
ms.openlocfilehash: bcd0e0eef16addc60743000b6ed8cba12276e29c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50439223"
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
