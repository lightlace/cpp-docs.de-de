---
title: -BASE (Basisadresse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /base
- VC.Project.VCLinkerTool.BaseAddress
dev_langs:
- C++
helpviewer_keywords:
- base addresses [C++]
- programs [C++], preventing relocation
- semicolon [C++], specifier
- -BASE linker option
- key address size
- environment variables [C++], LIB
- programs [C++], base address
- LIB environment variable
- BASE linker option
- DLLs [C++], linking
- /BASE linker option
- '@ symbol for base address'
- executable files [C++], base address
- at sign symbol for base address
ms.assetid: 00b9f6fe-0bd2-4772-a69c-7365eb199069
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1f6f287f98b542a3d8eb24f9cc2b5e725e27dceb
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725971"
---
# <a name="base-base-address"></a>/BASE (Basisadresse)

Gibt die Basisadresse für ein Programm an.

## <a name="syntax"></a>Syntax

> **/ BASE:**{*Adresse*[**,**<em>Größe</em>] | **\@** <em>Filename</em>**,**<em>Schlüssel</em>}

## <a name="remarks"></a>Hinweise

> [!NOTE]
> Aus Sicherheitsgründen empfiehlt Microsoft Sie verwenden die [/DynamicBase](../../build/reference/dynamicbase-use-address-space-layout-randomization.md) Option anstelle von Basisadressen für Ihre ausführbaren Dateien. Dadurch wird ein ausführbares Image, das nach dem Zufallsprinzip zur Ladezeit ein REBASE ausgeführt werden kann mithilfe der Address Space Layout Randomization (ASLR)-Funktion von Windows generiert. Der/DynamicBase-Option ist standardmäßig aktiviert.

Der/BASE-Option legt eine Basisadresse für das Programm, das Überschreiben des Standardspeicherort für eine .exe oder DLL-Datei fest. Die Standard-Basisadresse für eine .exe-Datei ist 0 x 400000 für 32-Bit-Images oder 0x140000000 für 64-Bit-Images. Für eine DLL ist die Standard-Basisadresse 0 x 10000000 für 32-Bit-Images oder 0x180000000 für 64-Bit-Images. Bei Betriebssystemen, die Adresse Space Layout Randomization (ASLR) nicht unterstützen, oder die /DYNAMICBASE:NO-Option wurde festgelegt, wenn, versucht das Betriebssystem zuerst, um ein Programm an seine angegebene oder die Standard-Basisadresse zu laden. Wenn Sie über genügend Speicherplatz vorhanden nicht verfügbar ist, verschiebt das System das Programm. Verwenden, um zu verhindern, dass die Verschiebung der [/FIXED](../../build/reference/fixed-fixed-base-address.md) Option.

Der Linker gibt einen Fehler aus, wenn *Adresse* ist kein Vielfaches von 64 KB. Sie können optional auch die Größe des Programms angeben. der Linker gibt eine Warnung aus, wenn die Anwendung nicht in der Größe passen, die Sie angegeben haben.

In der Befehlszeile ist eine weitere Möglichkeit zum Angeben der Basisadresse mit einer Antwortdatei für die Basisadresse. Eine Antwortdatei für die Basisadresse ist eine Textdatei, die die Basisadressen und optional Größen enthält alle DLLs, die Ihr Programm verwendet und eine eindeutige Schlüssel für alle Basisadressen. Verwenden Sie zum Angeben einer Basisadresse mithilfe einer Antwortdatei ein at-Zeichen (**\@**) gefolgt vom Namen der Antwortdatei, *Filename*, gefolgt von einem Komma und dann die *Schlüssel*Wert für die Basisadresse für die Verwendung in der Datei. Der Linker sucht nach *Filename* in entweder dem angegebenen Pfad, oder wenn kein Pfad angegeben ist, die in der LIB-Umgebungsvariablen angegebenen Verzeichnisse. Jede Zeile in *Filename* entspricht einer DLL und weist die folgende Syntax:

> *Schlüssel* *Adresse* [*Größe*] **;** *Kommentar*

Die *Schlüssel* ist eine Zeichenfolge mit alphanumerischen Zeichen und wird Groß-/ Kleinschreibung nicht berücksichtigt. Dies ist normalerweise der Name einer DLL, aber nicht zwingend erforderlich. Die *Schlüssel* gefolgt von einer Basis *Adresse* in der Programmiersprache C, Hexadezimal- oder Dezimalformat Notation und optional eine maximale Größe *Größe*. Alle drei Argumente werden durch Leerzeichen oder Tabstopps getrennt. Der Linker eine Warnung ausgibt, wenn das angegebene *Größe* ist kleiner als der virtuelle Adressraum von der Anwendung erforderlich sind. Ein *Kommentar* angegeben ist, durch ein Semikolon (**;**) und kann auf demselben oder auf einer separaten Zeile. Der Linker ignoriert allen Text aus dem Semikolon am Ende der Zeile. In diesem Beispiel zeigt einen Teil einer solchen Datei:

```
main   0x00010000    0x08000000    ; for PROJECT.exe
one    0x28000000    0x00100000    ; for DLLONE.DLL
two    0x28100000    0x00300000    ; for DLLTWO.DLL
```

Wenn die Datei, die folgenden Zeilen enthält DLLS.txt aufgerufen wird, werden diese Informationen von der folgende Beispielbefehl angewendet:

```
link dlltwo.obj /dll /base:@dlls.txt,two
```

Eine weitere Möglichkeit zum Festlegen der Basisadresse ist die Verwendung der *Basis* -Argument in einem [Namen](../../build/reference/name-c-cpp.md) oder [Bibliothek](../../build/reference/library.md) Anweisung. Der/Base und [/DLL](../../build/reference/dll-build-a-dll.md) Optionen zusammen entsprechen den **Bibliothek** Anweisung.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

2. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **erweitert** Eigenschaftenseite.

3. Ändern der **Basisadresse** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.BaseAddress%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)