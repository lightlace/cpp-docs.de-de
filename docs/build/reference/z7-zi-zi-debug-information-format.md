---
title: -Z7, - Zi - ZI (Debuginformationsformat) | Microsoft Docs
ms.custom: 
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
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f6e3de89c5336cda98960b67b80932df8f67d183
ms.sourcegitcommit: 2cca90d965f76ebf1d741ab901693a15d5b8a4df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2018
---
# <a name="z7-zi-zi-debug-information-format"></a>/Z7, /Zi, /ZI (Debuginformationsformat)

Gibt den Typ der Debuginformationen für das Programm und gibt an, ob diese Informationen in Objektdateien oder in einer Programmdatenbankdatei (PDB) gespeichert werden erstellt.

## <a name="syntax"></a>Syntax

> **/Z**{**7**|**i**|**I**}  

## <a name="remarks"></a>Hinweise

Die Formatoptionen für Debug-Informationen werden in den folgenden Abschnitten beschrieben.  
  
### <a name="none"></a>Keiner

Standardmäßig Wenn keine Debug Informationen Format-Option angegeben wird, erzeugt der Compiler keine Debuginformationen, damit die Kompilierung schneller ist.  
  
### <a name="z7"></a>/Z7

Die **"/ Z7"** option erzeugt einen *Objektdatei*, eine Datei mit einer OBJ-Erweiterung, die mit vollständigen symbolischen Debuginformationen zur Verwendung mit dem Debugger. Zu den symbolischen Debuginformationen gehören die Namen und Typen von Variablen sowie Funktionen und Zeilennummern. Nicht *PDB-Datei*, eine Datei mit einer Erweiterung ".pdb" wird erstellt.

Für die Verteiler von Drittanbieterbibliotheken ist es ein Vorteil, keine PDB-Datei. Die Objektdateien für die vorkompilierten Header sind jedoch erforderlich, während der Linkphase und für das Debuggen. Wenn es nur Informationen (und keinen Code) in die PCH-Objektdateien geben ist, müssen Sie auch verwenden die [/Yl (PCH-Verweis für Debugbibliothek einfügen)](../../build/reference/yl-inject-pch-reference-for-debug-library.md) Option, die standardmäßig aktiviert ist.

### <a name="zi"></a>/ZI

Die **/Zi** Option erstellt eine PDB-Datei, die Typinformationen und symbolische Debuginformationen für die Verwendung mit dem Debugger enthält. Zu den symbolischen Debuginformationen gehören die Namen und Typen von Variablen sowie Funktionen und Zeilennummern.

Verwenden von **/Zi** hat keinen Einfluss auf Optimierungen. Allerdings **/Zi** impliziert **/debug**; finden Sie unter [/Debug (Debuginfo generieren)](../../build/reference/debug-generate-debug-info.md) für Weitere Informationen.

Wenn **/Zi** angegeben ist, werden Typinformationen in der PDB-Datei und nicht in der Objektdatei platziert.

Sie können [/GM (minimale Neuerstellung aktivieren)](../../build/reference/gm-enable-minimal-rebuild.md) zusammen mit **/Zi**, aber **/GM** ist nicht verfügbar, wenn **"/ Z7"** angegeben ist.

Wenn Sie beide angeben **/Zi** und **"/ CLR"**die <xref:System.Diagnostics.DebuggableAttribute> Attribut nicht in den Metadaten der Assembly platziert wird. Wenn Sie es möchten, müssen Sie es im Quellcode angeben. Dieses Attribut kann Auswirkungen auf die Laufzeitleistung der Anwendung haben. Weitere Informationen darüber, wie die **Debuggable** Attribut wirkt sich auf Leistung und wie Sie die Auswirkungen auf die Leistung ändern können, finden Sie unter [erleichtern des Debugmodus für ein Abbild](/dotnet/framework/debug-trace-profile/making-an-image-easier-to-debug).

### <a name="zi"></a>/ZI

Die **/Zi** Option erstellt eine PDB-Datei in ein Format, unterstützt die [bearbeiten und Fortfahren](/visualstudio/debugger/edit-and-continue-visual-cpp) Funktion. Wenn Sie mit "Bearbeiten und Fortfahren" debuggen möchten, müssen Sie diese Option verwenden. Die Funktion bearbeiten und Fortfahren eignet sich für die Produktivität der Entwickler, jedoch Probleme in Compilerkonformität, Codegröße und Leistung verursacht werden kann. Da die meisten Optimierungen nicht mit bearbeiten und Fortfahren kompatibel sind, verwenden **/Zi** deaktiviert jede `#pragma optimize` Anweisungen in Ihrem Code. Die **/Zi** Option ist auch nicht kompatibel mit der [&#95; &#95; LINE #95; &#95; Das vordefinierte Makro](../../preprocessor/predefined-macros.md). Mit Code kompiliert **/Zi** können keine **&#95; &#95; LINE #95; &#95;**  als Nichttyp-Vorlagenargument, obwohl **&#95; &#95; LINE #95; &#95;**  können in makroerweiterungen verwendet.

Die **/Zi** Option erzwingt, dass sowohl die [/Gy (Funktionslevel Linking aktivieren)](../../build/reference/gy-enable-function-level-linking.md) und [/FC (vollständiger Pfad der Quellcodedatei in Diagnostics)](../../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md) Optionen, die bei der Kompilierung verwendet werden.

**/ Zi** ist nicht kompatibel mit [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).

> [!NOTE]
> Die **/Zi** Option ist nur in Compilern X86- und X64-Prozessoren abzielen; diese Compileroption steht nicht in Compilern ARM-Prozessoren abzielen.

Der Compiler die PDB-Datei benannt *Projekt*PDB-Datei. Wenn Sie eine Datei außerhalb eines Projekts zu kompilieren, erstellt der Compiler eine PDB-Datei mit dem Namen VC*x*0.pdb, wobei *x* die Hauptversionsnummer der Visual Studio-Version verwendet wird. Der Compiler bettet den Namen der PDB in jede mit dieser Option erstellte OBJ-Datei ein und verweist so den Debugger auf den Standort von symbolischen Informationen und Zeilennummern. Wenn Sie diese Option verwenden, werden die OBJ-Dateien kleiner, da Debuginformationen in PDB-Datei nicht in OBJ-Dateien gespeichert werden.

Wenn Sie eine Bibliothek von Objekten erstellen, die mit dieser Option kompiliert worden sind, muss die zugeordnete PDB-Datei verfügbar sein, wenn die Bibliothek zu einem Programm gelinkt wird. Daher müssen Sie auch die PDB weitergeben, wenn Sie die Bibliothek weitergeben.

Zum Erstellen einer Bibliothek, die Debuginformationen ohne Verwendung von PDB-Dateien enthält, müssen Sie auswählen, der Compiler C 7.0-kompatibel (**"/ Z7"**) Option. Wenn Sie Optionen für vorkompilierte Header verwenden, werden Debuginformationen für den vorkompilierten Header und den Rest des Quellcodes in der PDB-Datei abgelegt. Die **/Yd ablegen** Option wird ignoriert, wenn die Programmdatenbank-Option angegeben wird.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Öffnen der **Konfigurationseigenschaften** > **C/C++-** > **allgemeine** Eigenschaftenseite.

1. Ändern der **Debuginformationsformat** Eigenschaft. Wählen Sie **OK** zum Speichern der Änderungen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)  
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)  

