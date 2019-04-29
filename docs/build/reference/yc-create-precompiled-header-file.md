---
title: /Yc (Datei der vorkompilierten Header erstellen)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.UsePrecompiledHeader
- /yc
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderThrough
- VC.Project.VCCLWCECompilerTool.UsePrecompiledHeader
- VC.Project.VCCLCompilerTool.PrecompiledHeaderThrough
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- .pch files, creating
- -Yc compiler option [C++]
- /Yc compiler option [C++]
- Yc compiler option [C++]
ms.assetid: 47c2e555-b4f5-46e6-906e-ab5cf21f0678
ms.openlocfilehash: 0d902b9ebb35bc7f267cb67861b7be0763f378a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316703"
---
# <a name="yc-create-precompiled-header-file"></a>/Yc (Datei der vorkompilierten Header erstellen)

Weist den Compiler an, eine vorkompilierte Headerdatei (.pch) zu erstellen, die den Zustand der Kompilierung zu einem bestimmten Zeitpunkt darstellt.

## <a name="syntax"></a>Syntax

> __/Yc__<br/>
> __/Yc__*filename*

## <a name="arguments"></a>Argumente

*filename*<br/>
Gibt eine Headerdatei (. h). Wenn dieses Argument verwendet wird, kompiliert der Compiler den gesamten Code bis zur und einschließlich der h-Datei.

## <a name="remarks"></a>Hinweise

Wenn **"/ Yc"** wird ohne Argument angegeben, der Compiler kompiliert den gesamten Code bis zum Ende der Basis Quelldatei oder der Punkt in der Basisdatei, in denen eine [Hdrstop](../../preprocessor/hdrstop.md) -Direktive tritt auf. Die resultierende PCH-Datei hat den gleichen Basisnamen wie die Basis-Quelldatei, außer Sie geben eine andere Datei mit den **Hdrstop** Pragma oder **/fp** Option.

Der vorkompilierte Code wird in einer Datei gespeichert, mit einem Namen erstellen, die aus dem Basisnamen der Datei angegeben, mit der **"/ Yc"** Option und einer .pch-Erweiterung. Sie können auch die  [ /fp (Name. PCH-Datei)](fp-name-dot-pch-file.md) verwenden, um einen Namen für die vorkompilierte Headerdatei anzugeben.

Bei Verwendung von __"/ Yc"__*Filename*, kompiliert der Compiler alle Code bis zur und einschließlich der angegebenen Datei für die nachfolgende Verwendung mit der ["/ Yu" (verwenden Sie vorkompilierte Headerdatei)](yu-use-precompiled-header-file.md) Option.

Wenn die Optionen __"/ Yc"__*Filename* und __"/ Yu"__*Filename* auftreten, in der gleichen Befehlszeile, und verweisen oder impliziert wird, den gleichen Dateinamen __"/ Yc"__*Filename* hat Vorrang vor. Diese Funktion vereinfacht das Schreiben von Makefiles.

Weitere Informationen zu vorkompilierten Headern finden Sie unter:

- [/Y (Vorkompilierte Header)](y-precompiled-headers.md)

- [Vorkompilierte Headerdateien](../creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Wählen Sie eine CPP-Datei. Die CPP-Datei muss #include die h-Datei, die vorkompilierte Headerinformationen enthält. Des Projekts **"/ Yc"** Einstellung kann auf der Dateiebene überschrieben werden.

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Öffnen der **Konfigurationseigenschaften**, **C/C++-**, **vorkompilierte Header** Eigenschaftenseite.

1. Ändern der **vorkompilierter Header** Eigenschaft.

1. Ändern Sie zum Festlegen der Dateiname der **vorkompilierte Headerdatei** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Weitere Informationen finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>.

## <a name="example"></a>Beispiel

Betrachten Sie folgenden Code:

```cpp
// prog.cpp
// compile with: cl /c /Ycmyapp.h prog.cpp
#include <afxwin.h>   // Include header for class library
#include "resource.h" // Include resource definitions
#include "myapp.h"    // Include information specific to this app
// ...
```

Wenn dieser Code kompiliert wird, mit dem Befehl `CL /YcMYAPP.H PROG.CPP`, speichert der Compiler alle die vorverarbeitung für AFXWIN.h, "RESOURCE.h", und MYAPP.h in einer vorkompilierten Headerdatei namens MYAPP.pch.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)<br/>
[Vorkompilierte Headerdateien](../creating-precompiled-header-files.md)
