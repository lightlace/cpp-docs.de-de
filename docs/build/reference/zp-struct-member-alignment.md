---
title: /Zp (Ausrichten des Strukturmembers)
ms.date: 12/17/2018
f1_keywords:
- /zp
- VC.Project.VCCLCompilerTool.StructMemberAlignment
- VC.Project.VCCLWCECompilerTool.StructMemberAlignment
helpviewer_keywords:
- Struct Member Alignment compiler option
- Zp compiler option
- /Zp compiler option [C++]
- -Zp compiler option [C++]
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
ms.openlocfilehash: d30e61137fc5ff8f6a5501ac7815edafc18f7680
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807688"
---
# <a name="zp-struct-member-alignment"></a>/Zp (Ausrichten des Strukturmembers)

Steuert, wie die Member einer Struktur im Speicher abgelegt werden, und gibt die gleichen Packen von Metriken für alle Strukturen in einem Modul.

## <a name="syntax"></a>Syntax

> **/Zp**[**1**|**2**|**4**|**8**|**16**]

## <a name="remarks"></a>Hinweise

Bei Angabe der **/Zp**_n_ option, die einzelnen Strukturmember nach dem ersten entweder die Größe des Elementtyps gespeichert oder *n*-Byte-Grenzen (, in denen *n* ist 1, 2, 4, 8 oder 16), je nachdem, was kleiner ist.

Die verfügbaren Packen-Werte werden in der folgenden Tabelle beschrieben:

|/ Zp-argument|Effekt|
|-|-|
|1|Komprimiert Strukturen auf 1-Byte-Begrenzungen. Identisch mit **/Zp**.|
|2|Komprimiert Strukturen auf 2-Byte-Begrenzungen.|
|4|Komprimiert Strukturen auf 4-Byte-Begrenzungen.|
|8|Komprimiert Strukturen auf 8-Byte-Begrenzungen (Standard).|
|16| Komprimiert Strukturen auf 16-Byte-Begrenzungen.|

Sie sollten diese Option nicht verwenden, es sei denn, Sie bestimmte ausrichtungsanforderungen haben.

> [!WARNING]
> C++-Header im Windows SDK wird davon ausgegangen **"/ zp8"** packen. Arbeitsspeicher, die eine Beschädigung kann auftreten, wenn die **/Zp** Einstellung geändert, wenn Sie mithilfe von Windows SDK-Header.

Sie können auch [Pack](../../preprocessor/pack.md) Ausrichten von Strukturen. Weitere Informationen zur Ausrichtung finden Sie unter:

- [align](../../cpp/align-cpp.md)

- [__alignof-Operator](../../cpp/alignof-operator.md)

- [__unaligned](../../cpp/unaligned.md)

- [/ALIGN (Abschnittsausrichtung)](align-section-alignment.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **C/C++-** > **Codegenerierung** Eigenschaftenseite.

1. Ändern der **Ausrichtung der Strukturmember an** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>.

## <a name="see-also"></a>Siehe auch

- [MSVC-Compiler-Optionen](compiler-options.md)
- [MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)
