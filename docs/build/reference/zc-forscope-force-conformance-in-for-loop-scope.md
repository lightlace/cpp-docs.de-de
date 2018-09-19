---
title: '/ Zc: forScope (Übereinstimmung in for-Schleifenbereich erzwingen) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.ForceConformanceInForLoopScope
- VC.Project.VCCLWCECompilerTool.ForceConformanceInForLoopScope
- /zc:forScope
dev_langs:
- C++
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: 3031f02d-3b14-4ad0-869e-22b0110c3aed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bef68f47fe8fdc430138a6961078139b48030b3d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723592"
---
# <a name="zcforscope-force-conformance-in-for-loop-scope"></a>/Zc:forScope (Übereinstimmung in for-Schleifenbereich erzwingen)

Verwendet zum Implementieren von Standard-C++-Verhalten für [for](../../cpp/for-statement-cpp.md) -Schleifen mit Microsoft-Erweiterungen([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).

## <a name="syntax"></a>Syntax

> **/Zc:forScope**[**-**]

## <a name="remarks"></a>Hinweise

Standardverhalten bedeutet, den Initialisierer einer **for** -Schleife nach der **for** -Schleife den Gültigkeitsbereich verlassen zu lassen. Unter **/Zc:forScope-** und [/Ze](../../build/reference/za-ze-disable-language-extensions.md)bleibt der Initialisierer der **for** -Schleife im Gültigkeitsbereich, bis der lokale Gültigkeitsbereich endet.

Die **/Zc: forScope** Option ist standardmäßig aktiviert. **/ Zc: forScope** hat keine Auswirkungen, wenn die [/ PERMISSIVE--](permissive-standards-conformance.md) angegeben wird.

Die Option **/Zc:forScope-** ist veraltet und wird in einer der nächsten Versionen entfernt. Eine Verwendung von **/Zc:forScope-** generiert die Veraltungswarnung D9035.

Der folgende Code wird unter **/Ze** , aber nicht unter **/Za**kompiliert:

```cpp
// zc_forScope.cpp
// compile by using: cl /Zc:forScope- /Za zc_forScope.cpp
// C2065, D9035 expected
int main() {
    // Compile by using cl /Zc:forScope- zc_forScope.cpp
    // to compile this non-standard code as-is.
    // Uncomment the following line to resolve C2065 for /Za.
    // int i;
    for (int i = 0; i < 1; i++)
        ;
    i = 20;   // i has already gone out of scope under /Za
}
```

Wenn Sie **/Zc:forScope-** verwenden, wird die Warnmeldung C4288 (standardmäßig deaktiviert) generiert, wenn sich eine Variable aufgrund einer Deklaration, die in einem früheren Gültigkeitsbereich erfolgt ist, im Gültigkeitsbereich befindet. Um dies zu veranschaulichen, entfernen Sie die Zeichen `//` im Beispiel, um `int i`zu deklarieren.

Sie können das Laufzeitverhalten von **/Zc:forScope** ändern, indem Sie das [conform](../../preprocessor/conform.md) -Pragma verwenden.

Wenn Sie **/Zc:forScope-** in einem Projekt verwenden, für das es eine vorhandene PCH-Datei gibt, wird eine Warnung generiert, wird **/Zc:forScope-** ignoriert, und wird die Kompilierung mit der vorhandenen PCH-Dateien fortgesetzt. Wenn Sie eine neue PCH-Datei erstellen möchten, verwenden Sie ["/ Yc" (Erstellen vorkompilierter Headerdatei)](../../build/reference/yc-create-precompiled-header-file.md).

Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Sprache** Eigenschaftenseite.

1. Ändern Sie die Eigenschaft **Übereinstimmung in einem For-Schleifenbereich erzwingen** .

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForceConformanceInForLoopScope%2A>.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)<br/>
[/Za, /Ze (Spracherweiterungen deaktivieren)](../../build/reference/za-ze-disable-language-extensions.md)<br/>
