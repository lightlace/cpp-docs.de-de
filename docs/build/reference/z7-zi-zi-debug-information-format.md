---
title: -Z7, - Zi, - ZI (Debuginformationsformat) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 02/22/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.DebugInformationFormat
- /ZI
- /Zi
- /Z7
- VC.Project.VCCLWCECompilerTool.DebugInformationFormat
dev_langs:
- C++
helpviewer_keywords:
- C7 compatible compiler option [C++]
- Debug Information Format compiler option
- ZI compiler option
- -Zi compiler option [C++]
- /ZI compiler option [C++]
- Z7 compiler option [C++]
- debugging [C++], debug information files
- Zi compiler option [C++]
- /Zi compiler option [C++]
- program database compiler option [C++]
- full symbolic debugging information
- /Z7 compiler option [C++]
- line numbers only compiler option [C++]
- cl.exe compiler, debugging options
- -Z7 compiler option [C++]
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 271948368190ddf5110d8b1fb357fe770a72e1aa
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714271"
---
# <a name="z7-zi-zi-debug-information-format"></a>/Z7, /Zi, /ZI (Debuginformationsformat)

Gibt den Typ der Debuginformationen erstellt, die für Ihr Programm und ob diese Informationen als Objektdateien oder in einer Programmdatenbankdatei (PDB) gespeichert werden sollen.

## <a name="syntax"></a>Syntax

> **/Z**{**7**|**i**|**I**}

## <a name="remarks"></a>Hinweise

Bei der Code wird kompiliert und erstellt im Debugmodus ausgeführt, generiert der Compiler Symbolnamen für Funktionen und Variablen, Typinformationen und Line Number Speicherorte für die Verwendung durch den Debugger an. Diese symbolische Debuginformationen kann entweder in den Objektdateien (OBJ-Dateien), die vom Compiler erzeugten, oder klicken Sie in einer separaten PDB-Datei (PDB-Datei) für die ausführbare Datei enthalten sein.  Die Formatoptionen für Debug-Informationen werden in den folgenden Abschnitten beschrieben.

### <a name="none"></a>Keiner

Standardmäßig Wenn keine Debug Informationen Format-Option angegeben wird, generiert der Compiler keine Debuginformationen, damit die Kompilierung schneller ist.

### <a name="z7"></a>/Z7

Die **"/ Z7"** Option erzeugt Objektdateien, die auch vollständige symbolische Debuginformationen für die Verwendung mit dem Debugger enthalten. Diese Objektdateien und die erstellte ausführbare Datei können wesentlich größer als Dateien sein, die keine Informationen zum Debuggen. Zu den symbolischen Debuginformationen gehören die Namen und Typen von Variablen sowie Funktionen und Zeilennummern. Es wird keine PDB-Datei generiert.

Für die Verteiler von Debugversionen von Drittanbieter-Bibliotheken ist es ein Vorteil der ohne einer PDB-Datei. Die Objektdateien für alle vorkompilierten Header sind jedoch erforderlich, während der Linkphase Bibliothek sowie zum Debuggen. Wenn vorhanden ist, nur Typinformationen (und keinen Code) in der Objektdatei PCH geben, müssen Sie auch verwenden die [/Yl (PCH-Verweis für Debugbibliothek einfügen)](../../build/reference/yl-inject-pch-reference-for-debug-library.md) Option, die standardmäßig aktiviert ist, wenn Sie die Bibliothek erstellen.

Die [/GM (minimale Neuerstellung aktivieren)](../../build/reference/gm-enable-minimal-rebuild.md) Option ist nicht verfügbar, wenn **"/ Z7"** angegeben ist.

### <a name="zi"></a>/ZI

Die **"/ Zi"** Option generiert eine separate PDB-Datei, die alle den symbolischen Debuginformationen für die Verwendung mit dem Debugger enthält. Die Debuginformationen nicht in den Objektdateien enthalten ist, oder ausführbare Datei an, sodass sie wesentlich kleiner ist.

Verwenden von **"/ Zi"** wirkt sich nicht auf die Optimierungen. Allerdings **"/ Zi"** impliziert **/debug**; finden Sie unter [/Debug (Debuginfo generieren)](../../build/reference/debug-generate-debug-info.md) für Weitere Informationen.

Wenn Sie beide angeben **"/ Zi"** und **"/ CLR"**, <xref:System.Diagnostics.DebuggableAttribute> Attribut wird nicht in den Metadaten der Assembly platziert. Wenn Sie es möchten, müssen Sie es im Quellcode angeben. Dieses Attribut kann Auswirkungen auf die Laufzeitleistung der Anwendung haben. Weitere Informationen zur Funktionsweise des **Debuggable** Attribut wirkt sich auf die Leistung und wie Sie die Auswirkungen auf die Leistung ändern können, finden Sie unter [Making an Image Easier to Debug](/dotnet/framework/debug-trace-profile/making-an-image-easier-to-debug).

Der Compiler die PDB-Datei benannt *Projekt*PDB-Datei. Wenn Sie eine Datei außerhalb eines Projekts kompilieren, erstellt der Compiler eine PDB-Datei mit dem Namen VC*x*PDB-Datei, wobei *x* besteht aus einer Verkettung der Haupt-und Nebenversionsnummern Anzahl von der Compilerversion verwendet. Der Compiler bettet den Namen der PDB-Datei und eine identifizierende mit einem Zeitstempel-Signatur in einzelnen Objektdatei erstellt haben, verwenden diese Option, die den Debugger auf den Speicherort der Zeilennummer und symbolischen Informationen verweist. Name und Signatur in der PDB-Datei müssen die ausführbare Datei für die Symbole im Debugger geladen werden, übereinstimmen. Des WinDBG-Debuggers kann nicht übereinstimmende Symbole laden, indem Sie mit der `.symopt+0x40` Befehl. Visual Studio muss sich nicht auf eine ähnliche können nicht übereinstimmende Symbole laden aus.

Wenn Sie eine Bibliothek von Objekten erstellen, die mit kompiliert wurden **"/ Zi"**, die zugehörige PDB-Datei muss verfügbar sein, wenn die Bibliothek mit einem Programm verknüpft ist. Also, wenn Sie die Bibliothek weitergeben, müssen Sie auch die PDB-Datei verteilen. Zum Erstellen einer Bibliothek, die Debuginformationen ohne Verwendung von PDB-Dateien enthält, Sie müssen auswählen, die **"/ Z7"** Option. Wenn Sie Optionen für vorkompilierte Header verwenden, wird die Debuginformationen für den vorkompilierten Header und den Rest des Quellcodes in der PDB-Datei eingefügt.

### <a name="zi"></a>/ZI

Die **"/ Zi"** Option ist vergleichbar mit **"/ Zi"**, doch wird dadurch eine PDB-Datei in ein Format, unterstützt die [bearbeiten und Fortfahren](/visualstudio/debugger/edit-and-continue-visual-cpp) Feature. Zum Bearbeiten und fortfahren, Debuggen von Features zu verwenden, müssen Sie diese Option verwenden. Die Funktion bearbeiten und Fortfahren eignet sich für die Produktivität von Entwicklern, aber es kann zu Problemen im Code-Größe, Leistung und Compiler Conformance führen. Da die meisten Optimierungen nicht mit bearbeiten und Fortfahren kompatibel sind, mithilfe von **"/ Zi"** deaktiviert jede `#pragma optimize` -Anweisungen in Ihrem Code. Die **"/ Zi"** Option ist auch nicht mit Verwendung des der [ &#95; &#95;Zeile&#95; &#95; vordefiniertes Makro](../../preprocessor/predefined-macros.md); kompilierten Code mit **"/ Zi"** kannnichtverwendetwerden.**&#95; &#95;Zeile&#95; &#95;** als Nichttyp-Vorlagenargument, obwohl **&#95; &#95;Zeile&#95; &#95;** in makroerweiterungen verwendet werden kann.

Die **"/ Zi"** Option erzwingt, dass sowohl die [/Gy (Funktionslevel-Linking aktivieren)](../../build/reference/gy-enable-function-level-linking.md) und [/FC (vollständiger Pfad der Quellcodedatei in Diagnose)](../../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md) Optionen, die bei der Kompilierung verwendet werden.

**"/ Zi"** ist nicht kompatibel mit [/CLR (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md).

> [!NOTE]
> Die **"/ Zi"** Option ist nur in Compilern für X86 und X64-Prozessoren verfügbar; Diese Compileroption ist nicht in Compilern für ARM-Prozessoren verfügbar.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Öffnen der **Konfigurationseigenschaften** > **C/C++-** > **allgemeine** Eigenschaftenseite.

1. Ändern der **Debuginformationsformat** Eigenschaft. Wählen Sie **OK** zum Speichern der Änderungen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)

