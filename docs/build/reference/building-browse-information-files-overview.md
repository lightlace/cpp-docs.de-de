---
title: 'Erstellen von Browseinformationsdateien: Übersicht'
ms.date: 05/06/2019
helpviewer_keywords:
- .bsc files, about .bsc files
- bsc files, about bsc files
- browse information files (.bsc)
- browse information files (.bsc), creating
ms.assetid: b5c12832-51f6-4953-8044-4264dd0fb242
ms.openlocfilehash: 5d33460ba63e50d31e44384be382e98cfbea4c91
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220548"
---
# <a name="building-browse-information-files-overview"></a>Erstellen von Browseinformationsdateien: Übersicht


> [!WARNING]
> Obwohl BSCMAKE weiterhin mit Visual Studio installiert wird, wird es nicht mehr von der IDE verwendet. Seit Visual Studio 2008 werden Browse- und Symbolinformationen automatisch in einer SQL Server-.SDF-Datei im Projektmappenordner gespeichert.

Zum Durchsuchen von Informationen für die Symbolsuche zu erstellen, erstellt der Compiler eine SBR-Datei für jede Quelldatei im Projekt, klicken Sie dann BSCMAKE an. EXE-Datei wird die SBR-Dateien in einer BSC-Datei.

SBR- und BSC-Dateien generieren nimmt Zeit in Anspruch, damit Visual Studio diese Funktionen standardmäßig deaktiviert. Wenn Sie aktuelle Informationen durchsuchen möchten, müssen Sie die Durchsuchen-Optionen aktivieren und das Projekt erneut erstellen.

Verwendung [/FR](fr-fr-create-dot-sbr-file.md) oder [/FR](fr-fr-create-dot-sbr-file.md) um den Compiler SBR-Dateien zu erstellen. Sie können zum Erstellen von BSC-Dateien aufrufen [BSCMAKE](bscmake-command-line.md) über die Befehlszeile. Mithilfe von BSCMAKE über die Befehlszeile, bietet Ihnen eine präzisere Kontrolle über die Bearbeitung von Browserinformationsdateien. Finden Sie unter [BSCMAKE-Referenz](bscmake-reference.md) für Weitere Informationen.

> [!TIP]
>  Sie können einschalten SBR-Datei generieren jedoch BSC-Datei generieren, die deaktiviert. Dadurch schnell erstellt, aber auch können Sie schnell eine neue .bsc-Datei erstellen, durch das Aktivieren der Generierung von BSC-Dateien und beim Erstellen des Projekts.

Sie können die Zeit, Arbeitsspeicher und Speicherplatz erforderlich, um eine BSC-Datei zu erstellen, durch die Reduzierung der BSC-Datei reduzieren.

Finden Sie unter [Eigenschaftenseite "Allgemein" (Projekt)](general-property-page-project.md) für Informationen über das eine Browserdatei in der Entwicklungsumgebung zu erstellen.

### <a name="to-create-a-smaller-bsc-file"></a>Um eine kleinere BSC-Datei zu erstellen.

1. Verwendung [BSCMAKE-Befehlszeilenoptionen](bscmake-options.md) Ausschließen von Informationen aus der Browserinformationsdatei aus.

1. Lassen Sie die lokalen Symbole in eine oder mehrere .sbr-Dateien beim Kompilieren oder assemblieren.

1. Wenn eine Objektdatei nicht für die aktuelle Schritt des Debugvorgangs erforderlichen Informationen enthält, lassen Sie beim Neuerstellen der Browserinformationsdatei die SBR-Datei aus dem BSCMAKE-Befehl.

### <a name="to-combine-the-browse-information-from-several-projects-into-one-browser-file-bsc"></a>Kombinieren Sie die Durchsuchen-Informationen aus mehreren Projekten in einer Datei (.bsc)

1. Entweder nicht erstellen Sie die BSC-Datei auf Projektebene zu oder verwenden Sie den/n-Schalter, um zu verhindern, dass die SBR-Dateien abgeschnitten wird.

1. Nachdem alle Projekte erstellt werden, führen Sie BSCMAKE mit allen die SBR-Dateien als Eingabe. Platzhalter sind zulässig. Wenn Sie Projektverzeichnissen C:\X C:\Y und C:\Z SBR-Dateien in und diese in einer BSC-Datei kombinieren möchten mussten, klicken Sie dann verwenden Sie z. B. BSCMAKE C:\X\\\*SBR C:\Y\\\*SBR C:\Z\\ \*SBR/o c:\whatever_directory\combined.bsc zum Erstellen der kombinierten BSC-Datei.

## <a name="see-also"></a>Siehe auch

[Zusätzliche MSVC-Buildtools](c-cpp-build-tools.md)<br/>
[BSCMAKE-Referenz](bscmake-reference.md)
