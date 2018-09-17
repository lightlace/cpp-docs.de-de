---
title: Verwalten einer Bibliothek | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLibrarianTool.OVERWRITEAllDefaultLibraries
- VC.Project.VCLibrarianTool.AdditionalDependencies
- VC.Project.VCLibrarianTool.RemoveObjects
- VC.Project.VCLibrarianTool.LibraryPaths
- VC.Project.VCLibrarianTool.OutputFile
- VC.Project.VCLibrarianTool.OVERWRITEDefaultLibraryNames
- VC.Project.VCLibrarianTool.AdditionalLibraryDirectories
- VC.Project.VCLibrarianTool.ListContentsFile
- VC.Project.VCLibrarianTool.ListContents
- VC.Project.VCLibrarianTool.SubSystemVersion
- VC.Project.VCLibrarianTool.OVERWRITEDefaultLibraryName
- VC.Project.VCLibrarianTool.SubSystem
dev_langs:
- C++
helpviewer_keywords:
- /LIBPATH library manager option
- OUT library manager option
- CONVERT library manager option
- LIBPATH library manager option
- /LIST library manager option
- object files, building and modifying
- -LINK50COMPAT library manager option
- REMOVE library manager option
- SUBSYSTEM library manager option
- /LINK50COMPAT library manager option
- /OUT library manager option
- LIB [C++], managing COFF libraries
- -CONVERT library manager option
- LINK50COMPAT library manager option
- -OUT library manager option
- -REMOVE library manager option
- -LIST library manager option
- /SUBSYSTEM library manager option
- -SUBSYSTEM library manager option
- /REMOVE library manager option
- -LIBPATH library manager option
- object files
- LIST library manager option
- /CONVERT library manager option
ms.assetid: f56a8b85-fbdc-4c09-8d8e-00f0ffe1da53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd6fff812d200e16b82994f9f9bbe598aface547
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713153"
---
# <a name="managing-a-library"></a>Verwalten einer Bibliothek

Der Standardmodus für LIB ist eine Bibliothek von COFF-Objekten zu erstellen. LIB wird in diesem Modus ausgeführt, wenn Sie nicht/Extract (zum Kopieren eines Objekts in eine Datei) oder/DEF (zum Erstellen einer Importbibliothek) angeben.

Um eine Bibliothek von Objekten und/oder Bibliotheken zu erstellen, verwenden Sie die folgende Syntax:

```
LIB [options...] files...
```

Dieser Befehl erstellt eine Bibliothek aus einer oder mehreren Eingabedateien *Dateien*. Die *Dateien* COFF-Objektdateien, 32-Bit-OMF-Objektdateien oder bestehende COFF-Bibliotheken sind möglich. LIB erstellt eine Bibliothek, die alle Objekte in den angegebenen Dateien enthält. Wenn eine Eingabedatei eine 32-Bit-OMF-Objekt-Datei ist, konvertiert LIB in COFF-Format vor dem Erstellen der Bibliotheks. LIB kann kein 32-Bit-OMF-Objekt akzeptieren, die in einer Bibliothek, die von der 16-Bit-Version der LIB erstellt wird. Zum Extrahieren des Objekts müssen Sie zuerst die 16-Bit-Bibliothek verwenden. dann können Sie die Datei extrahierte Objekt als Eingabe für die 32-Bit-Bibliothek.

In der Standardeinstellung benennt LIB Ausgabedatei mit dem Basisnamen der ersten Datei Objekt- oder Bibliotheksdateien und der Erweiterung. Lib. Die Ausgabedatei wird im aktuellen Verzeichnis abgelegt. Wenn eine Datei mit dem gleichen Namen bereits vorhanden ist, ersetzt die Ausgabedatei die vorhandene Datei an. Um eine vorhandene Bibliothek beizubehalten, verwenden Sie die/Out-Option, um einen Namen für die Ausgabedatei anzugeben.

Die folgenden Optionen gelten für erstellen und Ändern einer Bibliothek:

**/ LIBPATH:** *Dir*<br/>
Überschreibt den Bibliothekspfad der Umgebung. Weitere Informationen finden Sie unter der Beschreibung des Links [/LIBPATH](../../build/reference/libpath-additional-libpath.md) Option.

**/ AUFLISTEN**<br/>
Zeigt Informationen über die Ausgabebibliothek an die Standardausgabe. Die Ausgabe kann in eine Datei umgeleitet werden. Sie können/List / verwenden, um den Inhalt einer vorhandenen Bibliothek zu bestimmen, ohne es zu ändern.

**/ NAME:** *Dateiname*<br/>
Beim Erstellen einer Importbibliothek gibt den Namen der DLL für die die Importbibliothek erstellt wird.

**/ NODEFAULTLIB**<br/>
Entfernt eine oder mehrere Standardbibliotheken aus der Liste der Bibliotheken, die beim Auflösen externer Verweise durchsucht. Finden Sie unter [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) für Weitere Informationen.

**/ OUT:** *Dateiname*<br/>
Überschreibt den standardmäßigen Ausgabedateinamen. Standardmäßig wird die Ausgabebibliothek im aktuellen Verzeichnis, mit dem Basisnamen der ersten Datei Bibliothek oder Objektdatei in der Befehlszeile und die Erweiterung erstellt. Lib.

**/ REMOVE:** *Objekt*<br/>
Unterdrückt das angegebene *Objekt* in der Ausgabebibliothek. LIB erstellt eine Ausgabebibliothek durch Kombinieren aller Objekte (in Objektdateien und Bibliotheken) und anschließendes Löschen aller mithilfe von/Remove angegeben.

**/ SUBSYSTEM:**{**KONSOLE** &AMP;#124; **EFI_APPLICATION** &AMP;#124; **EFI_BOOT_SERVICE_DRIVER** &AMP;#124; **EFI_ROM** &AMP;#124; **EFI_RUNTIME_DRIVER** &AMP;#124; **NATIVE** &AMP;#124; **POSIX** &AMP;#124; **WINDOWS** &AMP;#124; **WINDOWSCE**} [, #[. ##]]<br/>
Teilt dem Betriebssystem Gewusst wie: Ausführen eines Programms erstellt, indem Sie mit der Ausgabebibliothek verknüpfen. Weitere Informationen finden Sie unter der Beschreibung des Links [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) Option.

LIB-Optionen, die in der Befehlszeile angegeben sind nicht in der Groß-/Kleinschreibung beachtet.

LIB können Sie die folgenden Bibliothek-Management-Aufgaben ausführen:

- Um die Objekte in einer Bibliothek hinzufügen möchten, geben Sie den Dateinamen für die vorhandene Bibliothek und den Dateinamen für die neuen Objekte.

- Bibliotheken zu kombinieren, geben Sie die Namen der Bibliothek. Sie können Objekte hinzufügen und Kombinieren von Bibliotheken mit einem einzigen LIB-Befehl.

- Um eines Bibliothekmembers durch ein neues Objekt zu ersetzen, geben Sie die Bibliothek, die das Memberobjekt, das ersetzt werden und den Dateinamen für das neue Objekt (oder die Bibliothek, die er enthält). Wenn ein Objekt mit demselben Namen in mehr als eine Eingabedatei vorhanden ist, setzt LIB das letzte Objekt in der LIB-Befehl angegeben werden, in der Ausgabebibliothek. Wenn Sie ein Bibliothekmembers ersetzen, achten Sie darauf, dass Sie an das neue Objekt oder die Bibliothek nach der Bibliothek, die das alte Objekt enthält.

- Um ein Element aus einer Bibliothek zu löschen, verwenden Sie die/Remove-Option. LIB verarbeitet von/Remove nach der Kombination aller Eingabeobjekte, unabhängig von der Reihenfolge.

> [!NOTE]
>  Sie können nicht sowohl ein Element zu löschen und extrahieren Sie es in eine Datei in demselben Schritt. Sie müssen zuerst extrahieren Sie das Memberobjekt, das mithilfe von/Extract sind und anschließend Ausführen von LIB/Remove erneut mit. Dieses Verhalten unterscheidet sich von den 16-Bit-lib (für OMF-Bibliotheken) und in andere Microsoft-Produkte bereitgestellt.

## <a name="see-also"></a>Siehe auch

[LIB-Referenz](../../build/reference/lib-reference.md)