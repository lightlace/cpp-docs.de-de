---
title: Linkertoolfehler LNK1318
ms.date: 05/29/2018
f1_keywords:
- LNK1318
helpviewer_keywords:
- LNK1318
ms.openlocfilehash: 8ed6489a27d4c0e117f7f18281ff188f40936e0a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160990"
---
# <a name="linker-tools-error-lnk1318"></a>Linkertoolfehler LNK1318

> Unerwarteter PDB-Fehler; *dazu führen, dass* "*Details*"

Der Linker hat einen unerwarteten Fehler beim Öffnen, lesen oder Schreiben in eine PDB-Datei gefunden.

Diese Fehlermeldung ist ungewöhnlich, dass Probleme in PDB-Dateien erstellt. Die *dazu führen, dass* und *Details* verfügbaren Informationen an den Linker darstellen, wenn der Fehler aufgetreten ist. Dies möglicherweise nicht sehr nützlich sein, wie häufige Fehler beim Umgang mit PDB-Dateien müssen separate, ausführlichere Fehlermeldungen.

Da die Quelle des Fehlers nicht üblich ist, besteht nur allgemeine Empfehlungen zur Lösung dieses Problems:

- Führen Sie eine saubere Operation in Ihrem Buildverzeichnisse, und führen Sie eine vollständige Erstellung der Projektmappe.

- Starten Sie Ihren Computer neu, oder vereinzelten oder nicht reagierende mspdbsrv.exe Prozesse überprüfen, und im Task-Manager zu beenden.

- Deaktivieren Sie antivirus-Überprüfungen in Ihren Projektverzeichnissen aus.

- Verwenden der [/ZF](../../build/reference/zf.md) Compileroption Wenn [/MP](../../build/reference/mp-build-with-multiple-processes.md) mit MSBuild oder einem anderen parallelen Buildprozess.

- Versuchen Sie es erstellen, mit dem gehosteten 64-Bit-Toolset.

- Verknüpfen zum Beheben von Problemen mit parallelen Link bei Bedarf zu serialisieren. Dieser Fehler kann verursacht werden, wenn mspdbsrv.exe wird heruntergefahren, bevor eine andere Instanz des Links abgeschlossen ist und, um eine Instanz des Links gestartet wird verwenden. Der Nachteil dieser Lösung ist, dass die Projektbuilds erheblich länger dauern können.