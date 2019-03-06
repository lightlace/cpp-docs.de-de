---
title: 'Erstellen von Browseinformationsdateien: Übersicht'
ms.date: 11/04/2016
helpviewer_keywords:
- .bsc files, about .bsc files
- bsc files, about bsc files
- browse information files (.bsc)
- browse information files (.bsc), creating
ms.assetid: b5c12832-51f6-4953-8044-4264dd0fb242
ms.openlocfilehash: 02f2107469e2fbbc4ea3591e1211e600d16fb9e9
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413016"
---
# <a name="building-browse-information-files-overview"></a>Erstellen von Browseinformationsdateien: Übersicht

Zum Durchsuchen von Informationen für die Symbolsuche zu erstellen, erstellt der Compiler eine SBR-Datei für jede Quelldatei im Projekt, klicken Sie dann BSCMAKE an. EXE-Datei wird die SBR-Dateien in einer BSC-Datei.

SBR- und BSC-Dateien generieren nimmt Zeit in Anspruch, damit Visual C++ diese Funktionen standardmäßig deaktiviert. Wenn Sie aktuelle Informationen durchsuchen möchten, müssen Sie die Durchsuchen-Optionen aktivieren und das Projekt erneut erstellen.

Verwendung [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) oder [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) um den Compiler SBR-Dateien zu erstellen. Sie können zum Erstellen von BSC-Dateien aufrufen [BSCMAKE](../../build/reference/bscmake-command-line.md) über die Befehlszeile. Mithilfe von BSCMAKE über die Befehlszeile, bietet Ihnen eine präzisere Kontrolle über die Bearbeitung von Browserinformationsdateien. Finden Sie unter [BSCMAKE-Referenz](../../build/reference/bscmake-reference.md) für Weitere Informationen.

> [!TIP]
>  Sie können einschalten SBR-Datei generieren jedoch BSC-Datei generieren, die deaktiviert. Dadurch schnell erstellt, aber auch können Sie schnell eine neue .bsc-Datei erstellen, durch das Aktivieren der Generierung von BSC-Dateien und beim Erstellen des Projekts.

Sie können die Zeit, Arbeitsspeicher und Speicherplatz erforderlich, um eine BSC-Datei zu erstellen, durch die Reduzierung der BSC-Datei reduzieren.

Finden Sie unter [Eigenschaftenseite "Allgemein" (Projekt)](../../ide/general-property-page-project.md) für Informationen über das eine Browserdatei in der Entwicklungsumgebung zu erstellen.

### <a name="to-create-a-smaller-bsc-file"></a>Um eine kleinere BSC-Datei zu erstellen.

1. Verwendung [BSCMAKE-Befehlszeilenoptionen](../../build/reference/bscmake-options.md) Ausschließen von Informationen aus der Browserinformationsdatei aus.

1. Lassen Sie die lokalen Symbole in eine oder mehrere .sbr-Dateien beim Kompilieren oder assemblieren.

1. Wenn eine Objektdatei nicht für die aktuelle Schritt des Debugvorgangs erforderlichen Informationen enthält, lassen Sie beim Neuerstellen der Browserinformationsdatei die SBR-Datei aus dem BSCMAKE-Befehl.

### <a name="to-combine-the-browse-information-from-several-projects-into-one-browser-file-bsc"></a>Kombinieren Sie die Durchsuchen-Informationen aus mehreren Projekten in einer Datei (.bsc)

1. Entweder nicht erstellen Sie die BSC-Datei auf Projektebene zu oder verwenden Sie den/n-Schalter, um zu verhindern, dass die SBR-Dateien abgeschnitten wird.

1. Nachdem alle Projekte erstellt werden, führen Sie BSCMAKE mit allen die SBR-Dateien als Eingabe. Platzhalter sind zulässig. Wenn Sie Projektverzeichnissen C:\X C:\Y und C:\Z SBR-Dateien in und diese in einer BSC-Datei kombinieren möchten mussten, klicken Sie dann verwenden Sie z. B. BSCMAKE C:\X\\\*SBR C:\Y\\\*SBR C:\Z\\ \*SBR/o c:\whatever_directory\combined.bsc zum Erstellen der kombinierten BSC-Datei.

## <a name="see-also"></a>Siehe auch

[C/C++-Buildtools](../../build/reference/c-cpp-build-tools.md)<br/>
[BSCMAKE-Referenz](../../build/reference/bscmake-reference.md)
