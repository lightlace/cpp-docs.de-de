---
title: -Zp (Strukturmemberausrichtung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/30/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /zp
- VC.Project.VCCLCompilerTool.StructMemberAlignment
- VC.Project.VCCLWCECompilerTool.StructMemberAlignment
dev_langs:
- C++
helpviewer_keywords:
- Struct Member Alignment compiler option
- Zp compiler option
- /Zp compiler option [C++]
- -Zp compiler option [C++]
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0268f5c5d5d34d8fa244dc6260889bea6b1e837a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715909"
---
# <a name="zp-struct-member-alignment"></a>/Zp (Ausrichten des Strukturmembers)

Steuert, wie die Member einer Struktur im Speicher abgelegt werden, und gibt die gleichen Packen von Metriken für alle Strukturen in einem Modul.

## <a name="syntax"></a>Syntax

> **/ Zp**[**1**|**2**|**4**|**8** | **16**]

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

- [Beispiele für die Strukturausrichtung](../../build/examples-of-structure-alignment.md) (X64 bestimmte)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **C/C++-** > **Codegenerierung** Eigenschaftenseite.

1. Ändern der **Ausrichtung der Strukturmember an** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>.

## <a name="see-also"></a>Siehe auch

- [Compileroptionen](../../build/reference/compiler-options.md)
- [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
