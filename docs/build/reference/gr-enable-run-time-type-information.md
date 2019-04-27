---
title: /GR (Laufzeit-Typeninformation aktivieren)
ms.date: 11/04/2016
f1_keywords:
- /gr
- VC.Project.VCCLWCECompilerTool.RuntimeTypeInfo
- VC.Project.VCCLCompilerTool.RuntimeTypeInfo
helpviewer_keywords:
- -Gr compiler option [C++]
- Gr compiler option [C++]
- RTTI compiler option
- /Gr compiler option [C++]
- enable run-time type information compiler option [C++]
ms.assetid: d1f9f850-dcec-49fd-96ef-e72d01148906
ms.openlocfilehash: 15ad453b10fd31de97bbc25f8062e628129076f5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292119"
---
# <a name="gr-enable-run-time-type-information"></a>/GR (Laufzeit-Typeninformation aktivieren)

Fügt Code aus, um die Objekttypen zur Laufzeit zu überprüfen.

## <a name="syntax"></a>Syntax

```
/GR[-]
```

## <a name="remarks"></a>Hinweise

Wenn **/Gr** aktiviert ist, definiert der Compiler die `_CPPRTTI` Präprozessor-Makro. In der Standardeinstellung **/Gr** ist. **/ Gr-verwendet** deaktiviert die Laufzeit Typinformationen.

Verwendung **/Gr** Wenn der Compiler einen Objekttyp in Ihrem Code nicht statisch beheben kann. Sie müssen in der Regel die **/Gr** option, wenn der Code verwendet [Dynamic_cast-Operator](../../cpp/dynamic-cast-operator.md) oder [Typeid](../../cpp/typeid-operator.md). Allerdings **/Gr** vergrößert sich die .rdata-Abschnitte des Bilds. Wenn Ihr Code keine verwendet **Dynamic_cast** oder **Typeid**, **/GR-verwendet** ein kleineres Image erzielt werden kann.

Weitere Informationen zum Laufzeittyp zu überprüfen, finden Sie unter [Laufzeit-Typeninformation](../../cpp/run-time-type-information.md) in die *C++-Sprachreferenz*.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **Sprache** Eigenschaftenseite.

1. Ändern der **Laufzeit-Typeninformation aktivieren** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeTypeInfo%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
