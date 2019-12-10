---
title: /WL (Einzeilige Diagnostik aktivieren)
ms.date: 11/04/2016
f1_keywords:
- /wl
helpviewer_keywords:
- -WL compiler option [C++]
- /WL compiler option [C++]
- WL compiler option [C++]
ms.assetid: 332cadb4-8ea6-45fe-b67d-33ddec1f2c2e
ms.openlocfilehash: b1ded1cd18eb75ed47b76c1353ad82a7fa497ba9
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988568"
---
# <a name="wl-enable-one-line-diagnostics"></a>/WL (Einzeilige Diagnostik aktivieren)

Fügt zusätzliche Informationen an einen Fehler oder eine Warnmeldung an.

## <a name="syntax"></a>Syntax

```
/WL
```

## <a name="remarks"></a>Hinweise

Auf Fehler-und Warnmeldungen C++ des Compilers können zusätzliche Informationen folgen, die standardmäßig in einer neuen Zeile angezeigt werden. Wenn Sie über die Befehlszeile kompilieren, kann die zusätzliche Zeile der Informationen an die Fehler-oder Warnmeldung angehängt werden. Dies ist möglicherweise wünschenswert, wenn Sie die Buildausgabe in einer Protokolldatei erfassen und dieses Protokoll dann verarbeiten, um alle Fehler und Warnungen zu ermitteln. Mit einem Semikolon wird die Fehler-oder Warnmeldung von der zusätzlichen Zeile getrennt.

Nicht alle Fehler-und Warnmeldungen verfügen über eine zusätzliche Informations Zeile. Der folgende Code generiert einen Fehler, der über eine zusätzliche Zeile von Informationen verfügt. Dadurch können Sie die Auswirkung bei der Verwendung von **/WL**testen.

```cpp
// compiler_option_WL.cpp
// compile with: /WL
#include <queue>
int main() {
   std::queue<int> q;
   q.fromthecontinuum();   // C2039
}
```

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
