---
title: /cgthreads (Codegenerierungsthreads)
ms.date: 11/04/2016
f1_keywords:
- /cgthreads
helpviewer_keywords:
- /cgthreads compiler option (C++)
- -cgthreads compiler option (C++)
- cgthreads compiler option (C++)
- cgthreads
ms.assetid: 64bc768c-6caa-4baf-9dea-7cfa1ffb01c2
ms.openlocfilehash: df353eb255c731478863ed6088cafa1cc38053fb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294687"
---
# <a name="cgthreads-code-generation-threads"></a>/cgthreads (Codegenerierungsthreads)

Legt die Anzahl der cl.exe-Threads fest, die für Optimierung und Codegenerierung verwendet werden.

## <a name="syntax"></a>Syntax

```
/cgthreads[1-8]
```

## <a name="arguments"></a>Argumente

*Anzahl*<br/>
Die maximale Anzahl von Threads zur Verwendung für cl.exe, im Bereich von 1 bis 8.

## <a name="remarks"></a>Hinweise

Die **/cgthreads** Option gibt an, die maximale Anzahl von Threads von cl.exe verwendet parallel für die Optimierungs- und codegenerierungsphasen der Kompilierung. Beachten Sie, dass es kann kein Leerzeichen zwischen **/cgthreads** und `number` Argument. Standardmäßig verwendet cl.exe vier Threads, als ob **/cgthreads4** wurden angegeben. Wenn mehr Prozessorkerne verfügbar sind, kann ein höherer `number`-Wert die Builderstellung beschleunigen. Diese Option ist besonders nützlich, wenn es sich bei Kombination mit [/GL (Whole Program Optimization)](gl-whole-program-optimization.md).

Für einen Build können mehrere Stufen der Parallelität angegeben werden. Der msbuild.exe-Switch **maxcpucount** gibt die Anzahl der MSBuild-Prozesse, die parallel ausgeführt werden können. Die [/MP (erstellen mit mehreren Prozessen)](mp-build-with-multiple-processes.md) -Compilerflag gibt die Anzahl der cl.exe-Prozesse, die die Quelldateien gleichzeitig zu kompilieren. Die **/cgthreads** Option gibt an, die Anzahl der Threads, die von jedem cl.exe-Prozess verwendet. Da der Prozessor nur so viele Threads gleichzeitig ausführen kann, wie Prozessorkerne vorhanden sind, ist es nicht sinnvoll, größere Werte für all diese Optionen gleichzeitig anzugeben. Das kann sogar kontraproduktiv sein. Weitere Informationen zum Erstellen von Projekten parallel, finden Sie unter [Erstellen von mehreren Projekten gleichzeitig](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften**, **C/C++-** Ordner.

1. Wählen Sie die **Befehlszeile** Eigenschaftenseite.

1. Ändern der **zusätzliche Optionen** Eigenschaft sollen **/cgthreads**`N`, wobei `N` ist ein Wert von 1 bis 8, und wählen Sie dann **OK**.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
