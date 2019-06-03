---
title: / Fp (Name &period;Pch-Datei)
description: Verwenden Sie die/Fp-Compileroption, um den Namen der vorkompilierten Headerdatei anzugeben.
ms.date: 05/31/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.PrecompiledHeaderFile
- /fp
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderFile
helpviewer_keywords:
- Fp compiler option [C++]
- -Fp compiler option [C++]
- naming precompiler header files
- PCH files, naming
- names [C++], PCH
- .pch files, naming
- precompiled header files, naming
- /Fp compiler option [C++]
ms.assetid: 0fcd9cbd-e09f-44d3-9715-b41efb5d0be2
ms.openlocfilehash: 6e7faa934d14acb5d129173c5e0c7ee67d6caf2b
ms.sourcegitcommit: 540fa2f5015de1adfa7b6bf823f6eb4ed5a6a4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2019
ms.locfileid: "66460873"
---
# <a name="fp-name-periodpch-file"></a>/ Fp (Name &period;Pch-Datei)

Stellt einen Pfadnamen für einen vorkompilierten Header anstelle des Standardpfadnamens bereit.

## <a name="syntax"></a>Syntax

> **/ Fp**<em>Pfadname</em>

## <a name="remarks"></a>Hinweise

Verwenden der **/fp** mit option ["/ Yc" (Erstellen vorkompilierter Headerdatei)](yc-create-precompiled-header-file.md) oder [/Yu (vorkompilierte Headerdatei verwenden)](yu-use-precompiled-header-file.md) an den Pfad und den Namen für die vorkompilierte Headerdatei (PCH) die Datei. In der Standardeinstellung die **"/ Yc"** Option erstellt ein Name der PCH-Datei mithilfe der Basisname der Quelldatei und *Pch* Erweiterung.

Wenn Sie nicht als Teil eine Erweiterung angeben der *Pfadnamen*, eine Erweiterung der *Pch* wird angenommen. Wenn Sie einen Verzeichnisnamen angeben, durch Verwendung von einem Schrägstrich ( **/** ) am Ende der *Pfadnamen*, der Standarddateiname ist vc*Version*0.pch, in denen  *Version* ist die Hauptversion des Visual Studio-Toolsets. Dieses Verzeichnis muss vorhanden sein, oder Fehler C1083 generiert.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Öffnen der **Konfigurationseigenschaften** > **C /C++**  > **vorkompilierte Header** Eigenschaftenseite.

1. Ändern der **vorkompilierte Headerausgabedatei** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="examples"></a>Beispiele

Um einen separaten benannten Version der vorkompilierten Headerdatei für die Debugbuild des Programms zu erstellen, können Sie z. B. einen Befehl angeben:

```CMD
CL /DDEBUG /Zi /Yc /FpDPROG.PCH PROG.CPP
```

Der folgende Befehl gibt die Verwendung einer vorkompilierten Headerdatei mit dem Namen MYPCH.pch. Der Compiler kompiliert den Quellcode in PROG.cpp bis zum Ende von MYAPP.h und setzt den vorkompilierten Code in MYPCH.pch. Klicken Sie dann verwendet den Inhalt des MYPCH.pch, und die restlichen PROG.cpp zum Erstellen einer OBJ-Datei kompiliert wird. Die Ausgabe dieses Beispiels wird eine Datei namens PROG.exe.

```CMD
CL /YuMYAPP.H /FpMYPCH.PCH PROG.CPP
```

## <a name="see-also"></a>Siehe auch

[Ausgabedatei (/F) Optionen](output-file-f-options.md)<br/>
[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)<br/>
[Festlegen des Pfadnamens](specifying-the-pathname.md)
