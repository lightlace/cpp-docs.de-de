---
title: /Zs (Nur Syntaxüberprüfung)
ms.date: 11/04/2016
f1_keywords:
- /zs
helpviewer_keywords:
- -Zs compiler option [C++]
- Syntax Check Only compiler option
- Zs compiler option
- /Zs compiler option [C++]
ms.assetid: b4b41e6a-3f41-4d09-9cb6-fde5aa2cfecf
ms.openlocfilehash: c7c8993ba9589b2a5fbc59d67e8603c141511695
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413315"
---
# <a name="zs-syntax-check-only"></a>/Zs (Nur Syntaxüberprüfung)

Weist den Compiler an, um nur die Syntax der Quelldateien in der Befehlszeile zu überprüfen.

## <a name="syntax"></a>Syntax

```
/Zs
```

## <a name="remarks"></a>Hinweise

Wenn Sie diese Option verwenden zu können, werden keine Ausgabedateien erstellt, und Fehlermeldungen werden an die Standardausgabe geschrieben.

Die **/ZS** Option bietet eine schnelle Möglichkeit zum Suchen und Syntaxfehler zu beheben, bevor Sie kompilieren und verknüpfen eine Quelldatei.

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
