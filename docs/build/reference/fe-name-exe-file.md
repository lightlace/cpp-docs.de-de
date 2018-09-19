---
title: -Fe (Name der EXE-Datei) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /fe
dev_langs:
- C++
helpviewer_keywords:
- -Fe compiler option [C++]
- executable files, renaming
- rename file compiler option [C++]
- /Fe compiler option [C++]
- Fe compiler option [C++]
ms.assetid: 49f594fd-5e94-45fe-a1bf-7c9f2abb6437
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad2683f79fdca845245fd266555e688aa8cf7374
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716234"
---
# <a name="fe-name-exe-file"></a>/Fe (Name der EXE-Datei)

Gibt einen Namen und ein Verzeichnis für die .exe-Datei oder DLL, die vom Compiler erstellt wird.

## <a name="syntax"></a>Syntax

> **/ FE**[_Pfadnamen_] **/FE:** _Pfadname_

### <a name="arguments"></a>Argumente

*Pfadname*<br/>
Der relativer oder absoluter Pfad und ein Basisdateiname oder ein relativer oder absoluter Pfad zu einem Verzeichnis oder den Basisdateinamen für die generierte ausführbare Datei verwenden.

## <a name="remarks"></a>Hinweise

Die **/FE** Option können Sie das Ausgabeverzeichnis, Name der ausführbaren Datei Ausgabe oder für die generierte ausführbare Datei angeben. Wenn *Pfadnamen* endet in einem Pfadtrennzeichen (**&#92;**), wird angenommen, dass nur das Ausgabeverzeichnis angeben. Andernfalls die letzte Komponente *Pfadnamen* dient als Basis Name der Ausgabedatei und der Rest des *Pfadnamen* gibt das Ausgabeverzeichnis an. Wenn *Pfadnamen* verfügt nicht über alle Trennzeichen im Pfad, es wird davon ausgegangen, dass im aktuellen Verzeichnis den Namen der Ausgabedatei an. Die *Pfadnamen* muss in doppelte Anführungszeichen eingeschlossen werden (**"**) Wenn sie keine Zeichen enthält, die nicht in einen kurzen Pfad verwenden, z. B. Leerzeichen befinden können erweiterte Zeichen oder Pfadkomponenten mehr als acht Zeichen lang.

Wenn die **/FE** nicht angegeben wird, oder wenn eine Datei, die Basis wurde kein Name angegeben *Pfadnamen*, der Compiler gibt der Ausgabedatei ein Standardname, der mit dem Basisnamen der ersten angegebenen Quell- oder Datei auf der Befehlszeile und die Erweiterung .exe oder .dll.

Bei Angabe der [/c (Kompilieren ohne Verknüpfen)](c-compile-without-linking.md) Option **/FE** hat keine Auswirkungen.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Öffnen der **Konfigurationseigenschaften** > **Linker** > **allgemeine** Eigenschaftenseite.

1. Ändern der **Ausgabedatei** Eigenschaft. Wählen Sie **OK** zum Speichern der Änderungen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>.

## <a name="example"></a>Beispiel

Die folgende Befehlszeile kompiliert und verknüpft alle C-Quelldateien im aktuellen Verzeichnis. Die resultierende ausführbare Datei heißt PROCESS.exe und wird in das Verzeichnis "C:\Users\User Name\repos\My Project\bin" erstellt.

```
CL /Fe"C:\Users\User Name\repos\My Project\bin\PROCESS" *.C
```

## <a name="example"></a>Beispiel

Die folgende Befehlszeile erstellt eine ausführbare Datei im `C:\BIN` mit den gleichen Basisnamen wie die ersten Quelldatei im aktuellen Verzeichnis:

```
CL /FeC:\BIN\ *.C
```

## <a name="see-also"></a>Siehe auch

[Ausgabedatei (/F) Optionen](../../build/reference/output-file-f-options.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)<br/>
