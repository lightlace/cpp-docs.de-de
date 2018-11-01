---
title: / SOURCELINK (umfassen Sourcelink-Datei in die PDB-Datei)
ms.date: 08/20/2018
f1_keywords:
- /sourcelink
helpviewer_keywords:
- /SOURCELINK linker option
- /SOURCELINK
ms.openlocfilehash: 5c742a37803f450aa6084c862800583f70bcedde
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480989"
---
# <a name="sourcelink-include-sourcelink-file-in-pdb"></a>/ SOURCELINK (umfassen Sourcelink-Datei in die PDB-Datei)

Gibt eine SourceLink-Konfigurationsdatei in der vom Linker generierte PDB-Datei eingeschlossen werden sollen.

## <a name="syntax"></a>Syntax

> **/ SOURCELINK:**_Dateiname_

## <a name="arguments"></a>Argumente

*filename*<br/>
Gibt eine JSON-formatierte Konfigurationsdatei, die eine einfache Zuordnung der lokalen Dateipfade, URLs enthält, in dem die Quelldatei abgerufen werden kann, für die Anzeige durch den Debugger. Weitere Informationen zum Format dieser Datei finden Sie unter [JSON-Schema der Datenquellensicht-Link](https://github.com/dotnet/designs/blob/master/accepted/diagnostics/source-link.md#source-link-json-schema).

## <a name="remarks"></a>Hinweise

SourceLink ist eine Sprache – und unabhängig Quellcodeverwaltungssystem für die Bereitstellung von Quelle für Binärdateien zu debuggen. SourceLink werden für systemeigene C++-Binärdateien, die in Visual Studio 2017 Version 15.8 ab. Einen Überblick über die SourceLink, finden Sie unter [Link "Quelle"](https://github.com/dotnet/designs/blob/master/accepted/diagnostics/source-link.md). Informationen zum SourceLink in Ihren Projekten zu verwenden und wie Sie die SourceLink-Datei als Teil Ihres Projekts zu generieren, finden Sie unter [mithilfe SourceLink](https://github.com/dotnet/sourcelink#using-sourcelink).

### <a name="to-set-the-sourcelink-linker-option-in-visual-studio"></a>So legen Sie die /SOURCELINK-Linkeroption in Visual Studio fest

1. Öffnen der **Eigenschaftenseiten** im Dialogfeld für das Projekt. Weitere Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

1. In der **zusätzliche Optionen** fügen **/SOURCELINK:**_Filename_ und wählen Sie dann **OK** oder **übernehmen**zum Speichern der Änderungen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Diese Option ist keine programmgesteuerte Variante verfügbar sein.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)
