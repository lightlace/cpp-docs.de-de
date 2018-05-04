---
title: -Zp (Strukturmembers) | Microsoft Docs
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
ms.openlocfilehash: 1666da40f748d18c762eae19595692addcdbf78a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="zp-struct-member-alignment"></a>/Zp (Ausrichten des Strukturmembers)

Steuert, wie die Member einer Struktur in den Speicher gepackt werden, und gibt an, die dieselbe Anordnung für alle Strukturen in einem Modul.

## <a name="syntax"></a>Syntax

> **/ Zp**[**1**|**2**|**4**|**8** | **16**]

## <a name="remarks"></a>Hinweise

Geben Sie bei der **/Zp**_n_ option einzelnen Strukturmember nach dem ersten entweder die Größe des Membertyps gespeichert oder *n*-Byte-Grenzen (, in denen *n* ist 1, 2, 4, 8 oder 16), welcher Wert kleiner ist.

Die verfügbaren Verpackung Werte werden in der folgenden Tabelle beschrieben:

|/ Zp-argument|Effekt|
|-|-|
|1|Packs Strukturen auf 1-Byte-Grenzen. Identisch mit **/Zp**.|
|2|Packs Strukturen auf 2-Byte-Grenzen.|
|4|Packs Strukturen an 4-Byte-Grenzen.|
|8|Packs Strukturen an 8-Byte-Grenzen (Standard).|
|16| Packs Strukturen an 16-Byte-Grenzen.|

Sie sollten diese Option nicht verwenden, es sei denn, Sie über bestimmte ausrichtungsanforderungen verfügen.

> [!WARNING]  
> C++-Header im Windows SDK angenommen **"/ zp8"** packen. Arbeitsspeicher, die eine Beschädigung kann auftreten, wenn die **/Zp** Einstellung wird geändert, wenn mithilfe des Windows SDK-Header.

Sie können auch [Pack](../../preprocessor/pack.md) Ausrichten von Strukturen. Weitere Informationen zur Ausrichtung finden Sie unter:

- [align](../../cpp/align-cpp.md)

- [__alignof-Operator](../../cpp/alignof-operator.md)

- [__unaligned](../../cpp/unaligned.md)

- [Beispiele für die Strukturausrichtung](../../build/examples-of-structure-alignment.md) (X64 bestimmte)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **C/C++-** > **Codegenerierung** Eigenschaftenseite.

1. Ändern der **Ausrichten des Strukturmembers** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>.

## <a name="see-also"></a>Siehe auch

- [Compileroptionen](../../build/reference/compiler-options.md)   
- [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
