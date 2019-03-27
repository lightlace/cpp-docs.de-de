---
title: BSCMAKE-Befehlszeile
ms.date: 11/04/2016
helpviewer_keywords:
- BSCMAKE, command line
ms.assetid: 8006e8cf-8bfe-4c23-868a-b0a25e6bbf0f
ms.openlocfilehash: 61035ce0f211e6a474bb83fc7de7d95b4a29cf3d
ms.sourcegitcommit: 06fc71a46e3c4f6202a1c0bc604aa40611f50d36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "58508766"
---
# <a name="bscmake-command-line"></a>BSCMAKE-Befehlszeile

> [!WARNING]
> Obwohl BSCMAKE weiterhin mit Visual Studio installiert wird, wird es nicht mehr von der IDE verwendet. Seit Visual Studio 2008 werden Browse- und Symbolinformationen automatisch in einer SQL Server-.SDF-Datei im Projektmappenordner gespeichert.

Verwenden Sie die folgende Befehlszeilensyntax, führen Sie BSCMAKE:

```
BSCMAKE [options] sbrfiles
```

Optionen stehen nur in der `options` Feld in der Befehlszeile.

Die *Sbrfiles* Feld gibt einen oder mehrere .sbr-Dateien, die von einem Compiler oder den Assembler erstellt. Trennen Sie die Namen der SBR-Dateien mit Leerzeichen oder Tabstopps. Sie müssen die Erweiterung angeben. Es gibt keinen Standardwert. Sie können einen Pfad angeben, mit dem Dateinamen, und können Sie Betriebssystem-Platzhalter verwenden (\* und?).

Bei einem inkrementellen Build können Sie neue .sbr-Dateien angeben, die nicht Teil des ursprünglichen Builds waren. Wenn Sie alle Beiträge in die Browserinformationsdatei bleiben möchten, müssen Sie alle .sbr-Dateien (einschließlich abgeschnittene Dateien) angeben, die ursprünglich zum Erstellen der BSC-Datei verwendet wurden. Wenn Sie eine SBR-Datei weglassen, wird diese Datei Beitrag auf der Browserinformationsdatei entfernt.

Geben Sie eine verkürzten .sbr-Datei für einen vollständigen Build nicht. Ein vollständiger Build muss es sich um Beiträge aus allen angegebenen SBR-Dateien. Bevor Sie einen vollständigen Build durchzuführen, kompilieren Sie das Projekt erneut, und erstellen Sie eine neue .sbr-Datei für jede Datei leer.

Der folgende Befehl führt BSCMAKE zum Erstellen der Datei Main von drei SBR-Dateien:

```
BSCMAKE main.sbr file1.sbr file2.sbr
```

Weitere Informationen finden Sie unter [BSCMAKE-Befehlsdatei](bscmake-command-file-response-file.md) und [BSCMAKE-Optionen](bscmake-options.md).

## <a name="see-also"></a>Siehe auch

[BSCMAKE-Referenz](bscmake-reference.md)
