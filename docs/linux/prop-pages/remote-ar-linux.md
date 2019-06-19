---
title: Remotearchiveigenschaften (C++ Linux)
ms.date: 06/07/2019
ms.assetid: 5ee1e44c-8337-4c3a-b2f3-35e4be954f9f
f1_keywords: []
ms.openlocfilehash: 00de4ac56a9ce390672019c7fe5a838367823100
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821271"
---
# <a name="remote-archive-properties-c-linux"></a>Remotearchiveigenschaften (C++ Linux)

::: moniker range="vs-2015"

Die Unterstützung für Linux ist in Visual Studio 2017 und höher verfügbar.

::: moniker-end

::: moniker range=">=vs-2017"

Eigenschaft | Beschreibung
--- | ---
Erstellen eines Archivindex | Einen Archivindex erstellen (vgl. ranlib). Diese Option kann das Verknüpfen beschleunigen und die Abhängigkeit innerhalb der eigenen Bibliothek verringern.
Schlankes Archiv erstellen | Erstellt ein schlankes Archiv.  Ein schlankes Archiv enthält relative Pfade zu den Objekten, anstatt die Objekte einzubetten.  Um zwischen schlank und normal zu wechseln, muss die vorhandene Bibliothek gelöscht werden.
Keine Warnung beim Erstellen | Gibt keine Warnung aus, falls oder wenn die Bibliothek erstellt wird.
Zeitstempel abschneiden | Verwendet NULL für Zeitstempel und UIDs/GIDs.
Startbanner unterdrücken | Versionsnummer nicht anzeigen.
Ausführlich | Ausführlich
Zusätzliche Optionen | Zusätzliche Optionen.
Ausgabedatei | Die Option /OUT überschreibt den Standardnamen und den Speicherort des Programms, das die Bibliothek erstellt.
Archivierungsprogramm | Gibt das Programm an, das beim Linken statischer Objekte aufgerufen werden soll, oder den Pfad zum Archivierungsprogramm auf dem Remotesystem.
Archivierungsprogrammtimeout | Remote-Archivierungsprogrammtimeout in Millisekunden.
Ausgabe kopieren | Gibt an, ob die Buildausgabedatei vom Remotesystem auf den lokalen Computer kopiert werden soll.

::: moniker-end
