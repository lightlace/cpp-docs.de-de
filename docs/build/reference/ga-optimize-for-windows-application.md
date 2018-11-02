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
ms.openlocfilehash: 04f8e9e19e5224c1a03ab1c7679d37b7bb8d1389
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50503320"
---
# <a name="ga-optimize-for-windows-application"></a>/GA (Für Windows-Anwendung optimieren)

Die Ergebnisse in eine effizientere Code für eine .exe-Datei für den Zugriff auf lokalen Threadspeicher (TLS) Variablen.

## <a name="syntax"></a>Syntax

```
/GA
```

## <a name="remarks"></a>Hinweise

**/ GA** beschleunigt den Zugriff auf Daten, die mit deklariert [__declspec(thread)](../../cpp/declspec.md) in einem Windows-Programm. Wenn diese Option festgelegt ist, die [__tls_index](/windows/desktop/ProcThread/thread-local-storage) Makro wird davon ausgegangen, dass 0 sein.

Mithilfe von **/GA** für eine DLL-Datei in die Generierung von fehlerhaftem Code führen kann.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)