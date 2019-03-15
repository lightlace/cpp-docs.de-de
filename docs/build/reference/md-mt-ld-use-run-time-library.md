---
title: / MD, -MT, -LD (Laufzeitbibliothek verwenden)
ms.date: 11/04/2016
f1_keywords:
- /ld
- /mt
- VC.Project.VCCLWCECompilerTool.RuntimeLibrary
- VC.Project.VCCLCompilerTool.RuntimeLibrary
- /md
- /ml
helpviewer_keywords:
- /MT compiler option [C++]
- -MD compiler option [C++]
- threading [C++], multithread compiler option
- MSVCRTD.lib
- MSVCRT.lib
- LIBCMT.lib
- MD compiler option [C++]
- /MD compiler option [C++]
- MT compiler option [C++]
- LD compiler option [C++]
- MDd compiler option [C++]
- -MDd compiler option [C++]
- LIBCD.lib
- -MTd compiler option [C++]
- MTd compiler option [C++]
- /MTd compiler option [C++]
- -LD compiler option [C++]
- /MDd compiler option [C++]
- multithread compiler option
- _STATIC_CPPLIB symbol
- LIBC.lib
- /LD compiler option [C++]
- DLLs [C++], compiler options
- LIBCMTD.lib
- -MT compiler option [C++]
ms.assetid: cf7ed652-dc3a-49b3-aab9-ad60e5395579
ms.openlocfilehash: 59b0483d76a2a98c1f278a323a827b243d21adea
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822489"
---
# <a name="md-mt-ld-use-run-time-library"></a>/MD, /MT, /LD (Laufzeitbibliothek verwenden)

Zeigt an, ob es sich bei einem Multithread-Modul um eine DLL handelt, und gibt Veröffentlichungs- oder Debugversionen der Laufzeitbibliothek an.

## <a name="syntax"></a>Syntax

```
/MD[d]
/MT[d]
/LD[d]
```

## <a name="remarks"></a>Hinweise

|Option|Beschreibung|
|------------|-----------------|
|**/MD**|Bewirkt, dass die Anwendung die DLL-spezifische und Multithreaded-Version der Laufzeitbibliothek verwendet. Definiert `_MT` und `_DLL` und veranlasst, dass der Compiler den Bibliotheksnamen "MSVCRT.lib" in der OBJ-Datei positioniert.<br /><br /> Mit dieser Option kompilierte Anwendungen werden statisch mit der Bibliothek "MSVCRT.lib" verknüpft. Diese Bibliothek stellt eine Codeschicht bereit, die dem Linker ermöglicht, externe Verweise aufzulösen. Der tatsächlichen funktionierenden Code befindet sich im MSVCR*Versionnumber*. Die DLL, die zur Laufzeit mit "Msvcrt.lib" verknüpften Anwendungen verfügbar sein müssen.|
|**/MDd**|Definiert `_DEBUG`, `_MT` und `_DLL` und veranlasst, dass die Anwendung die DLL-spezifische und Multithreaded-Version der Laufzeitbibliothek verwendet. Außerdem wird verursacht, dass der Compiler den Bibliotheksnamen "MSVCRTD.lib" in der .obj-Datei positioniert.|
|**/MT**|Bewirkt, dass die Anwendung die statische Multithreaded-Version der Laufzeitbibliothek verwendet. Definiert `_MT` und bewirkt, dass der Compiler den Bibliotheksnamen "LIBCMT.LIB" in der OBJ-Datei ablegt, sodass diese Bibliothek vom Linker zum Auflösen externer Symbole verwendet wird.|
|**/MTd**|Definiert `_DEBUG` und `_MT`. Diese Option führt auch dazu, dass der Compiler den Bibliotheksnamen "LIBCMTD.lib" in der .obj-Datei positioniert, sodass der Linker "LIBCMTD.lib" für das Auflösen externer Symbole verwendet.|
|**/LD**|Erstellt eine DLL.<br /><br /> Übergibt die **/DLL** Option für den Linker. Der Linker sucht nach einer `DllMain`-Funktion, die jedoch nicht unbedingt erforderlich ist. Wenn Sie keine `DllMain`-Funktion schreiben, fügt der Linker eine `DllMain`-Funktion ein, die TRUE zurückgibt.<br /><br /> Verknüpft den DLL-Startcode.<br /><br /> Erstellt eine Importbibliothek (LIB), wenn in der Befehlszeile keine Exportdatei (EXP) angegeben wurde. Sie verknüpfen die Importbibliothek mit Anwendungen, die die DLL aufrufen.<br /><br /> Interpretiert [/FE (Name der EXE-Datei)](fe-name-exe-file.md) als Benennung einer DLL anstelle einer .exe-Datei. Standardmäßig wird der Name des Programms *Basename*.dll und nicht *Basename*.exe.<br /><br /> Impliziert **"/ MT"** ohne explizite Angabe **/MD**.|
|**/LDd**|Erstellt eine Debug-DLL. Definiert `_MT` und `_DEBUG`.|

Weitere Informationen zu C-Laufzeitbibliotheken und welche Bibliotheken verwendet werden, wenn die Kompilierung mit [/CLR (Common Language Runtime Compilation)](clr-common-language-runtime-compilation.md), finden Sie unter [CRT-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md).

Alle an einen bestimmten Aufruf des Linkers übergebenen Module müssen mit derselben Compileroption für die Laufzeitbibliothek kompiliert wurde (**/MD**, **"/ MT"**, **/ld**).

Weitere Informationen zur Verwendung der Debugversionen der Laufzeitbibliotheken finden Sie unter [C Run-Time Library Reference](../../c-runtime-library/c-run-time-library-reference.md).

Weitere Informationen über DLLs finden Sie unter [-DLLs in Visual C++](../dlls-in-visual-cpp.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Erweitern Sie die **C/C++-** Ordner.

1. Wählen Sie die **Codegenerierung** Eigenschaftenseite.

1. Ändern der **Laufzeitbibliothek** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeLibrary%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)
