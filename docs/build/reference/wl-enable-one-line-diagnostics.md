---
title: -WL (einzeilige-Diagnostik aktivieren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /wl
dev_langs:
- C++
helpviewer_keywords:
- -WL compiler option [C++]
- /WL compiler option [C++]
- WL compiler option [C++]
ms.assetid: 332cadb4-8ea6-45fe-b67d-33ddec1f2c2e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e82a3273673d45d1abf3ac201d7a0f63334cecbb
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718667"
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