---
title: /Fe (Name der EXE-Datei)
ms.date: 11/04/2016
f1_keywords:
- /fe
helpviewer_keywords:
- -Fe compiler option [C++]
- executable files, renaming
- rename file compiler option [C++]
- /Fe compiler option [C++]
- Fe compiler option [C++]
ms.assetid: 49f594fd-5e94-45fe-a1bf-7c9f2abb6437
ms.openlocfilehash: 5901ef1997cfea84c97b6d91b30335ff7dbc1d9f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292614"
---
# <a name="fe-name-exe-file"></a>/Fe (Name der EXE-Datei)

Gibt einen Namen und ein Verzeichnis für die .exe-Datei oder DLL, die vom Compiler erstellt wird.

## <a name="syntax"></a>Syntax

> **/Fe**[_pathname_] **/Fe:** _pathname_

### <a name="arguments"></a>Argumente

*pathname*<br/>
Der relativer oder absoluter Pfad und ein Basisdateiname oder ein relativer oder absoluter Pfad zu einem Verzeichnis oder den Basisdateinamen für die generierte ausführbare Datei verwenden.

## <a name="remarks"></a>Hinweise

Die **/FE** Option können Sie das Ausgabeverzeichnis, Name der ausführbaren Datei Ausgabe oder für die generierte ausführbare Datei angeben. Wenn *Pfadnamen* endet in einem Pfadtrennzeichen (**&#92;**), wird angenommen, dass nur das Ausgabeverzeichnis angeben. Andernfalls die letzte Komponente *Pfadnamen* dient als Basis Name der Ausgabedatei und der Rest des *Pfadnamen* gibt das Ausgabeverzeichnis an. Wenn *Pfadnamen* verfügt nicht über alle Trennzeichen im Pfad, es wird davon ausgegangen, dass im aktuellen Verzeichnis den Namen der Ausgabedatei an. Die *Pfadnamen* muss in doppelte Anführungszeichen eingeschlossen werden (**"**) Wenn sie keine Zeichen enthält, die nicht in einen kurzen Pfad verwenden, z. B. Leerzeichen befinden können erweiterte Zeichen oder Pfadkomponenten mehr als acht Zeichen lang.

Wenn die **/FE** nicht angegeben wird, oder wenn eine Datei, die Basis wurde kein Name angegeben *Pfadnamen*, der Compiler gibt der Ausgabedatei ein Standardname, der mit dem Basisnamen der ersten angegebenen Quell- oder Datei auf der Befehlszeile und die Erweiterung .exe oder .dll.

Bei Angabe der [/c (Kompilieren ohne Verknüpfen)](c-compile-without-linking.md) Option **/FE** hat keine Auswirkungen.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Öffnen der **Konfigurationseigenschaften** > **Linker** > **allgemeine** Eigenschaftenseite.

1. Ändern der **Ausgabedatei** Eigenschaft. Klicken Sie auf **OK**, um die Änderungen zu speichern.

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

[Ausgabedatei (/F) Optionen](output-file-f-options.md)<br/>
[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)<br/>
[Festlegen des Pfadnamens](specifying-the-pathname.md)<br/>
