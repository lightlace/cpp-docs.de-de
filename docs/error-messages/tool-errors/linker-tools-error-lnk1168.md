---
title: Linkertoolfehler LNK1168
ms.date: 11/04/2016
f1_keywords:
- LNK1168
helpviewer_keywords:
- LNK1168
ms.assetid: 97ead151-fd99-46fe-9a1d-7e84dc0b8cc8
ms.openlocfilehash: f0eb63c124162dbb515782bbd014c556c12de153
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450889"
---
# <a name="linker-tools-error-lnk1168"></a>Linkertoolfehler LNK1168

'Dateiname' kann nicht zum Schreiben geöffnet werden

Der Linker kann nicht in die Datei `filename` schreiben. Die Datei wird möglicherwiese verwendet und ihr Handle wird von einem anderen Prozess gesperrt oder Sie haben keine Schreibberechtigung für die Datei bzw. für das Verzeichnis oder die Netzwerkfreigabe, in der sich die Datei befindet. Dieser Fehler wird häufig durch eine vorübergehende Bedingung verursacht, z. B. eine Sperre durch ein Antivirenprogramm, eine Datei suchen, der Vorgang der Volltextindizierung oder eine Verzögerung bei der Freigabe einer Sperre frei, die das Buildsystem von Visual Studio.

Vergewissern Sie sich zur Behebung dieses Problems, dass das Handle für die Datei `filename` nicht gesperrt ist, und dass Sie über Schreibberechtigungen für die Datei verfügen. Wenn es sich um eine ausführbare Datei handelt, überprüfen Sie, ob diese nicht bereits ausgeführt wird.

Sie können die Windows SysInternals-Dienstprogramme verwenden [behandeln](/sysinternals/downloads/handle) oder [Process Explorer](/sysinternals/downloads/process-explorer) um zu bestimmen, welcher Prozess eine Datei, die Sperre zu verarbeiten hat `filename`. Sie können den Prozess-Explorer auch verwenden, um Sperren auf Handles von offenen Dateien aufzuheben. Weitere Informationen über die Verwendung der Hilfsprogramme finden Sie in den entsprechenden Hilfedateien zu den Programmen.

Wenn die Datei von einem Antivirenprogramm gesperrt wird, können Sie dieses Problem beheben, indem Sie die Buildausgabeverzeichnisse vom automatischen Scannen durch das Antivirenprogramm ausschließen. Virenscanner werden häufig bei der Erstellung neuer Dateien im Dateisystem ausgelöst und sperren die entsprechenden Dateien während des Scanprozesses. Informationen dazu, wie Sie bestimmte Verzeichnisse vom Scannen ausschließen können, finden Sie in der Dokumentation zum Antivirenprogramm.

Wenn die Datei durch einen Indexdienst für Suchvorgänge gesperrt wird, können Sie dieses Problem beheben, indem Sie die Buildausgabeverzeichnisse von der automatischen Indizierung ausschließen. Weitere Informationen zum Indexdienst finden Sie in der Dokumentation. Verwenden Sie zum Ändern der Windows-Suche Indexdienst **Indizierungsoptionen** in der Windows **Systemsteuerung**. Weitere Informationen finden Sie unter [suchen Sie in Windows 10-Indizierung: HÄUFIG GESTELLTE FRAGEN ZU](https://support.microsoft.com/help/4098843/windows-10-search-indexing-faq).

Wenn die ausführbare Datei nicht vom Buildprozess überschrieben werden kann, wird sie möglicherweise durch den Datei-Explorer gesperrt. Wenn die **Anwendungskomfort** Dienst wurde deaktiviert, Datei-Explorer kann an eine Sperre der ausführbaren Datei-Handle für einen längeren Zeitraum fest. Um dieses Problem zu beheben, führen Sie **"Services.msc"** und öffnen Sie dann die **Eigenschaften** im Dialogfeld für die **Anwendungskomfort** Service. Ändern der **Starttyp** aus **deaktiviert** zu **manuelle**.
