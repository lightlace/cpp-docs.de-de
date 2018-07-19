---
title: -Z7, - Zi - ZI (Debuginformationsformat) | Microsoft Docs
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
ms.openlocfilehash: a86605b8fd47c0febedfc9ab022dfc2c2728822a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379080"
---
# <a name="z7-zi-zi-debug-information-format"></a>/Z7, /Zi, /ZI (Debuginformationsformat)

Gibt den Typ der Debuginformationen für das Programm und gibt an, ob diese Informationen in Objektdateien oder in einer Programmdatenbankdatei (PDB) gespeichert werden erstellt.

## <a name="syntax"></a>Syntax

> **/Z**{**7**|**i**|**I**}  

## <a name="remarks"></a>Hinweise

Wenn der Code wird kompiliert und im Debugmodus befinden, erstellt, erstellt der Compiler Symbolnamen für Funktionen und Variablen, Typinformationen und Line Number Speicherorte für die Verwendung durch den Debugger an. Diese symbolische Debuginformationen kann entweder in die Objektdateien (OBJ-Dateien), die vom Compiler generierten oder in einer separaten PDB-Datei (PDB-Datei) für die ausführbare Datei enthalten sein.  Die Formatoptionen für Debug-Informationen werden in den folgenden Abschnitten beschrieben.  
  
### <a name="none"></a>Keiner

Standardmäßig Wenn keine Debug Informationen Format-Option angegeben wird, erzeugt der Compiler keine Debuginformationen, damit die Kompilierung schneller ist.  
  
### <a name="z7"></a>/Z7

Die **"/ Z7"** Option erzeugt Objektdateien, die auch vollständige symbolische Debuginformationen für die Verwendung mit dem Debugger enthalten. Diese Objektdateien und die erstellte ausführbare Datei können wesentlich größer als Dateien sein, die keine Debuginformationen aufweisen. Zu den symbolischen Debuginformationen gehören die Namen und Typen von Variablen sowie Funktionen und Zeilennummern. Es wird keine PDB-Datei erstellt.

Für die Verteiler von Debugversionen der Bibliotheken von Drittanbietern ist es ein Vorteil, keine PDB-Datei. Die Objektdateien für vorkompilierten Header sind jedoch erforderlich, während der Linkphase Bibliothek sowie zum Debuggen. Wenn es nur Informationen (und keinen Code) in der Objektdatei PCH geben gibt, müssen Sie auch verwenden die [/Yl (PCH-Verweis für Debugbibliothek einfügen)](../../build/reference/yl-inject-pch-reference-for-debug-library.md) Option, die standardmäßig aktiviert ist, wenn Sie die Bibliothek erstellen.

Die [/GM (minimale Neuerstellung aktivieren)](../../build/reference/gm-enable-minimal-rebuild.md) Option ist nicht verfügbar, wenn **"/ Z7"** angegeben ist.

### <a name="zi"></a>/ZI

Die **/Zi** Option erzeugt eine separaten PDB-Datei, die alle den symbolischen Debuginformationen zur Verwendung mit dem Debugger enthält. Die Debuginformationen nicht in den Objektdateien enthalten ist, oder ausführbare Datei, wodurch sie viel kleiner.

Verwenden von **/Zi** hat keinen Einfluss auf Optimierungen. Allerdings **/Zi** impliziert **/debug**; finden Sie unter [/Debug (Debuginfo generieren)](../../build/reference/debug-generate-debug-info.md) für Weitere Informationen.


Wenn Sie beide angeben **/Zi** und **"/ CLR"** die <xref:System.Diagnostics.DebuggableAttribute> Attribut nicht in den Metadaten der Assembly platziert wird. Wenn Sie es möchten, müssen Sie es im Quellcode angeben. Dieses Attribut kann Auswirkungen auf die Laufzeitleistung der Anwendung haben. Weitere Informationen darüber, wie die **Debuggable** Attribut wirkt sich auf Leistung und wie Sie die Auswirkungen auf die Leistung ändern können, finden Sie unter [erleichtern des Debugmodus für ein Abbild](/dotnet/framework/debug-trace-profile/making-an-image-easier-to-debug).

Der Compiler die PDB-Datei benannt *Projekt*PDB-Datei. Wenn Sie eine Datei außerhalb eines Projekts zu kompilieren, erstellt der Compiler eine PDB-Datei mit dem Namen VC*x*PDB-Datei, in denen *x* besteht aus einer Verkettung der Haupt-und Nebenversionsnummern Anzahl von der Compilerversion verwendet. Der Compiler bettet den Namen der PDB-Datei und einer identifizierende Zeitstempelserver Signatur in jeder Objektdatei erstellt haben, verwenden diese Option, die den Debugger auf den Speicherort der Zeilennummer und symbolischen Informationen verweist. Die Namen und derselben Signatur in der PDB-Datei müssen die ausführbare Datei für die Symbole in den Debugger geladen werden sollen übereinstimmen. WinDBG-Debugger kann nicht übereinstimmende Symbole laden, indem Sie mit der `.symopt+0x40` Befehl. Visual Studio muss sich nicht auf eine ähnliche Option aus, um nicht übereinstimmende Symbole laden aus.

Wenn Sie eine Bibliothek von Objekten erstellen, die kompiliert wurden mit **/Zi**, die zugehörige PDB-Datei muss verfügbar sein, wenn die Bibliothek mit einem Programm verknüpft ist. Daher, wenn Sie die Bibliothek weitergeben, müssen Sie auch die PDB-Datei verteilen. Zum Erstellen einer Bibliothek, die Debuginformationen ohne Verwendung von PDB-Dateien enthält, wählen Sie die **"/ Z7"** Option. Wenn Sie Optionen für vorkompilierte Header verwenden, werden Debuginformationen für den vorkompilierten Header und den Rest des Quellcodes in der PDB-Datei abgelegt.

### <a name="zi"></a>/ZI

Die **/Zi** Option ist vergleichbar mit **/Zi**, aber es erzeugt eine PDB-Datei in ein Format, unterstützt die [bearbeiten und Fortfahren](/visualstudio/debugger/edit-and-continue-visual-cpp) Funktion. Zum Bearbeiten und fortfahren, Debuggen von Features verwenden zu können, müssen Sie diese Option verwenden. Die Funktion bearbeiten und Fortfahren eignet sich für die Produktivität der Entwickler, jedoch Probleme im Code-Größe, Leistung und Compiler Conformance verursacht werden kann. Da die meisten Optimierungen nicht mit bearbeiten und Fortfahren kompatibel sind, verwenden **/Zi** deaktiviert jede `#pragma optimize` Anweisungen in Ihrem Code. Die **/Zi** Option ist auch nicht kompatibel mit der [ &#95; &#95;Zeile&#95; &#95; vordefiniertes Makro](../../preprocessor/predefined-macros.md); Code kompiliert wird, mit **/Zi** kannnichtverwendetwerden.**&#95; &#95;Zeile&#95; &#95;** als Nichttyp-Vorlagenargument, obwohl **&#95; &#95;Zeile&#95; &#95;** in makroerweiterungen verwendet werden kann.

Die **/Zi** Option erzwingt, dass sowohl die [/Gy (Funktionslevel Linking aktivieren)](../../build/reference/gy-enable-function-level-linking.md) und [/FC (vollständiger Pfad der Quellcodedatei in Diagnostics)](../../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md) Optionen, die bei der Kompilierung verwendet werden.

**/ Zi** ist nicht kompatibel mit [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).

> [!NOTE]
> Die **/Zi** Option ist nur in Compilern X86- und X64-Prozessoren abzielen; diese Compileroption steht nicht in Compilern ARM-Prozessoren abzielen.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Öffnen der **Konfigurationseigenschaften** > **C/C++-** > **allgemeine** Eigenschaftenseite.

1. Ändern der **Debuginformationsformat** Eigenschaft. Wählen Sie **OK** zum Speichern der Änderungen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)  
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)  

