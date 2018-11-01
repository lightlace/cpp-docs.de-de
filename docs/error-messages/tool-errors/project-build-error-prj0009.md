---
title: Projektbuildfehler PRJ0009
ms.date: 11/04/2016
f1_keywords:
- PRJ0009
helpviewer_keywords:
- PRJ0009
ms.assetid: 89291778-cda4-495d-983f-ddcc06dfc98b
ms.openlocfilehash: 963b7c861f9e8ee7105ebdc23afff08c4be46465
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438095"
---
# <a name="project-build-error-prj0009"></a>Projektbuildfehler PRJ0009

Erstellen Sie Protokoll konnte nicht zum Schreiben geöffnet werden.

**Stellen Sie sicher, dass die Datei nicht von einem anderen Prozess geöffnet ist und nicht schreibgeschützt.**

Nach dem Festlegen der **Buildprotokollierung** Eigenschaft **Ja** und Durchführen einer Erstellung oder Neuerstellung, Visual C++ konnte das Buildprotokoll im exklusiven Modus zu öffnen.

Überprüfen der **Buildprotokollierung** festlegen, indem Sie öffnen die **Optionen** (Dialogfeld) (auf der **Tools** im Menü klicken Sie auf **Optionen** Befehl) und klicken Sie dann Auswählen von **VC++-Build** in die **Projekte** Ordner. Die Builddatei "BuildLog.htm" aufgerufen wird und in das Zwischenverzeichnis $(intdir) geschrieben.

Mögliche Ursachen für diesen Fehler zu erhalten:

- Sie zwei Prozesse von Visual C++ ausführen und die gleiche Konfiguration eines Projekts in beiden gleichzeitig erstellen möchten.

- In einem Prozess, der die Datei sperrt, wird die Buildprotokolldatei geöffnet.

- Der Benutzer nicht über die Berechtigung zum Erstellen einer Datei.

- Der aktuelle Benutzer besitzt keine Schreibzugriff auf die Datei "BuildLog.htm".