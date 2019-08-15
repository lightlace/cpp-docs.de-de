---
title: /GA (Für Windows-Anwendung optimieren)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.OptimizeForWindowsApplication
- /ga
helpviewer_keywords:
- /GA compiler option [C++]
- GA compiler option [C++]
- -GA compiler option [C++]
- Optimize for Windows compiler options
ms.assetid: be97323e-15a0-4836-862c-95980b51926a
ms.openlocfilehash: 85efa03a3f3d267580cbb0442839afb18ac6c313
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492866"
---
# <a name="ga-optimize-for-windows-application"></a>/GA (Für Windows-Anwendung optimieren)

Führt zu effizienterem Code für eine exe-Datei für den Zugriff auf Thread lokale Speicher (TLS)-Variablen.

## <a name="syntax"></a>Syntax

```
/GA
```

## <a name="remarks"></a>Hinweise

**/GA** beschleunigt den Zugriff auf Daten, die in einem Windows-basierten Programm mit [__declspec (Thread)](../../cpp/declspec.md) deklariert wurden. Wenn diese Option festgelegt ist, wird angenommen, dass das [__tls_index](/windows/win32/ProcThread/thread-local-storage) -Makro 0 ist.

Die Verwendung von **/GA** für eine DLL kann zu einer ungültigen Codegenerierung führen.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
