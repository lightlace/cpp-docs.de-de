---
title: -Fe (Name der EXE-Datei) | Microsoft Docs
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
ms.openlocfilehash: 0afd8a863c9b8482e2b7f3868047845818bd2923
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377056"
---
# <a name="fe-name-exe-file"></a>/Fe (Name der EXE-Datei)

Gibt einen Namen und ein Verzeichnis für die .exe-Datei oder DLL, die vom Compiler erstellt.

## <a name="syntax"></a>Syntax

> **/ FE**[_Pathname_]  
> **/ Fe:** _Pfadnamen_  

### <a name="arguments"></a>Argumente

*Pfadnamen*<br/>
Der relative oder absolute Pfad und Basisdateiname oder relativer oder absoluter Pfad auf ein Verzeichnis oder der Basisdateiname für die generierte ausführbare Datei verwenden.

## <a name="remarks"></a>Hinweise

Die **/FE** Option können Sie das Ausgabeverzeichnis, ausführbares Ausgabenamen oder sowohl für die generierte ausführbare Datei angeben. Wenn *Pathname* endet in einem Pfadtrennzeichen (**&#92;**), es wird davon ausgegangen, dass nur das Ausgabeverzeichnis angeben. Andernfalls, die letzte Komponente *Pfadnamen* dient als Basis Name der Ausgabedatei und der Rest des *Pfadnamen* gibt das Ausgabeverzeichnis an. Wenn *Pathname* verfügt nicht über alle Pfadtrennzeichen, es wird angenommen, dass die Namen der Ausgabedatei im aktuellen Verzeichnis angeben. Die *Pathname* muss in doppelte Anführungszeichen eingeschlossen werden (**"**), wenn er Zeichen enthält, die in einen kurzen Pfad verwenden, z. B. Leerzeichen, kann nicht erweiterte Zeichen oder Pfadkomponenten mehr als acht Zeichen lang.

Wenn die **/FE** nicht angegeben wird, oder wenn eine Datei, die Basis Name nicht angegeben ist *Pathname*, generiert der Compiler der Ausgabedatei einen Standardnamen, der mit den Basisnamen der ersten angegebenen Quell- oder Datei auf der Befehlszeile und der Erweiterung .exe oder. dll.

Bei Angabe der [/c (Kompilieren ohne Verknüpfen)](c-compile-without-linking.md) Option **/FE** hat keine Auswirkungen.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Öffnen der **Konfigurationseigenschaften** > **Linker** > **allgemeine** Eigenschaftenseite.

1. Ändern der **Ausgabedatei** Eigenschaft. Wählen Sie **OK** zum Speichern der Änderungen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>.

## <a name="example"></a>Beispiel

Die folgende Befehlszeile kompiliert und verknüpft alle C#-Quelldateien im aktuellen Verzeichnis. Die resultierende ausführbare Datei heißt PROCESS.exe und wird im Verzeichnis "C:\Users\User Name\repos\My Project\bin" erstellt.

```
CL /Fe"C:\Users\User Name\repos\My Project\bin\PROCESS" *.C
```

## <a name="example"></a>Beispiel

Die folgende Befehlszeile erstellt eine ausführbare Datei in `C:\BIN` mit den gleichen Basisnamen wie die ersten Quelldatei im aktuellen Verzeichnis:

```
CL /FeC:\BIN\ *.C
```

## <a name="see-also"></a>Siehe auch

[Ausgabedatei (/F) Optionen](../../build/reference/output-file-f-options.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)<br/>
