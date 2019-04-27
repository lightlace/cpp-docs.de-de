---
title: Linkertoolfehler LNK1168
ms.date: 11/04/2016
f1_keywords:
- LNK1168
helpviewer_keywords:
- LNK1168
ms.assetid: 97ead151-fd99-46fe-9a1d-7e84dc0b8cc8
ms.openlocfilehash: d18aacd23a7ce9ed49f12a62f8358bb6d668c778
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62254935"
---
# <a name="linker-tools-error-lnk1168"></a>Linkertoolfehler LNK1168

'Dateiname' kann nicht zum Schreiben geöffnet werden

Der Linker kann nicht in die Datei `filename` schreiben. Die Datei wird möglicherwiese verwendet und ihr Handle wird von einem anderen Prozess gesperrt oder Sie haben keine Schreibberechtigung für die Datei bzw. für das Verzeichnis oder die Netzwerkfreigabe, in der sich die Datei befindet. Dieser Fehler wird häufig durch eine vorübergehende Bedingung verursacht, z. B. eine Sperre durch ein Antivirenprogramm, eine Datei suchen, der Vorgang der Volltextindizierung oder eine Verzögerung bei der Freigabe einer Sperre frei, die das Buildsystem von Visual Studio.

Vergewissern Sie sich zur Behebung dieses Problems, dass das Handle für die Datei `filename` nicht gesperrt ist, und dass Sie über Schreibberechtigungen für die Datei verfügen. Wenn es sich um eine ausführbare Datei handelt, überprüfen Sie, ob diese nicht bereits ausgeführt wird.

Sie können die Windows SysInternals-Dienstprogramme verwenden [behandeln](http://technet.microsoft.com/sysinternals/bb896655.aspx) oder [Process Explorer](http://technet.microsoft.com/sysinternals/bb896653) um zu bestimmen, welcher Prozess eine Datei, die Sperre zu verarbeiten hat `filename`. Sie können den Prozess-Explorer auch verwenden, um Sperren auf Handles von offenen Dateien aufzuheben. Weitere Informationen über die Verwendung der Hilfsprogramme finden Sie in den entsprechenden Hilfedateien zu den Programmen.

Wenn die Datei von einem Antivirenprogramm gesperrt wird, können Sie dieses Problem beheben, indem Sie die Buildausgabeverzeichnisse vom automatischen Scannen durch das Antivirenprogramm ausschließen. Virenscanner werden häufig bei der Erstellung neuer Dateien im Dateisystem ausgelöst und sperren die entsprechenden Dateien während des Scanprozesses. Informationen dazu, wie Sie bestimmte Verzeichnisse vom Scannen ausschließen können, finden Sie in der Dokumentation zum Antivirenprogramm.

Wenn die Datei durch einen Indexdienst für Suchvorgänge gesperrt wird, können Sie dieses Problem beheben, indem Sie die Buildausgabeverzeichnisse von der automatischen Indizierung ausschließen. Weitere Informationen zum Indexdienst finden Sie in der Dokumentation. Verwenden Sie zum Ändern der Windows-Suche Indexdienst **Indizierungsoptionen** in der Windows **Systemsteuerung**. Weitere Informationen finden Sie unter [Windows verbessern Suchvorgängen mithilfe des Index: häufig gestellte Fragen](http://windows.microsoft.com/windows/improve-windows-searches-using-index-faq#1TC=windows-7).

Wenn die ausführbare Datei nicht vom Buildprozess überschrieben werden kann, wird sie möglicherweise durch den Datei-Explorer gesperrt. Wenn die **Anwendungskomfort** Dienst wurde deaktiviert, Datei-Explorer kann an eine Sperre der ausführbaren Datei-Handle für einen längeren Zeitraum fest. Um dieses Problem zu beheben, führen Sie **"Services.msc"** und öffnen Sie dann die **Eigenschaften** im Dialogfeld für die **Anwendungskomfort** Service. Ändern der **Starttyp** aus **deaktiviert** zu **manuelle**.
