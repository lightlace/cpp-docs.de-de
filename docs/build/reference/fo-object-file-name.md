---
title: /Fo (Name der Objektdatei)
ms.date: 11/04/2016
f1_keywords:
- /Fo
- VC.Project.VCCLCompilerTool.ObjectFile
- VC.Project.VCCLWCECompilerTool.ObjectFile
helpviewer_keywords:
- Fo compiler option [C++]
- object files, naming
- /Fo compiler option [C++]
- -Fo compiler option [C++]
ms.assetid: 0e6d593e-4e7f-4990-9e6e-92e1dcbcf6e6
ms.openlocfilehash: 19e84cbb1be53c8e1a7ae32b6ea2fc3ceeb2edae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50640335"
---
# <a name="fo-object-file-name"></a>/Fo (Name der Objektdatei)

Gibt einen Namen für die Objektdatei (OBJ) oder das Verzeichnis an, der anstelle des Standardwerts verwendet werden soll.

## <a name="syntax"></a>Syntax

```
/Fopathname
```

## <a name="remarks"></a>Hinweise

Wenn Sie diese Option nicht verwenden, wird die Objektdatei der Basisname der Quelldatei und die OBJ-Erweiterung verwendet. Können Sie alle Namen und die Erweiterung, die Sie möchten, aber die empfohlene Konvention ist die Verwendung. obj.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken  Sie auf die Eigenschaftenseite **Ausgabedateien** .

1. Ändern der **Name der Objektdatei** Eigenschaft.  Die Objektdatei muss in der Entwicklungsumgebung, eine Erweiterung der aufweisen. obj.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ObjectFile%2A>.

## <a name="example"></a>Beispiel

Die folgende Befehlszeile erstellt eine Objektdatei, die mit dem Namen THIS.obj in ein vorhandenes Verzeichnis \OBJECT auf Laufwerk B.

```
CL /FoB:\OBJECT\ THIS.C
```

## <a name="see-also"></a>Siehe auch

[Ausgabedatei (/F) Optionen](../../build/reference/output-file-f-options.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)