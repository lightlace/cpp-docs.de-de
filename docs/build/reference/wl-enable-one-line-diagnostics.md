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
ms.openlocfilehash: 820143e1ff6feb718660fe8b297f2b96e26d2eb9
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413809"
---
# <a name="wl-enable-one-line-diagnostics"></a>/WL (Einzeilige Diagnostik aktivieren)

Fügt zusätzliche Informationen zu einer Warnung oder Fehlermeldung.

## <a name="syntax"></a>Syntax

```
/WL
```

## <a name="remarks"></a>Hinweise

Fehler- und Warnmeldungen aus der C++-Compiler können weitere Informationen folgen, die standardmäßig in einer neuen Zeile angezeigt wird. Wenn Sie über die Befehlszeile kompilieren, kann die zusätzliche Codezeile Informationen zu der Warnung oder Fehlermeldung angefügt werden. Dies kann sinnvoll sein, wenn Sie die Buildausgabe in eine Protokolldatei zu erfassen und Verarbeiten dieses Protokoll, um alle Fehler und Warnungen finden. Ein Semikolon wird die Warnung oder Fehlermeldung von der zusätzlichen Zeile trennen.

Nicht alle Fehler und Warnungen müssen eine zusätzliche Zeile Informationen. Der folgende Code wird ein Fehler generiert, der eine zusätzliche Zeile Informationen verfügt; können Sie die Auswirkungen zu testen, bei der Verwendung **/WL**.

```
// compiler_option_WL.cpp
// compile with: /WL
#include <queue>
int main() {
   std::queue<int> q;
   q.fromthecontinuum();   // C2039
}
```

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
