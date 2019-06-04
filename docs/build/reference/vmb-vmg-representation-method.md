---
title: /vmb, /vmg (Darstellungsmethode)
ms.date: 11/04/2016
f1_keywords:
- /vmb
- /vmg
helpviewer_keywords:
- vmb compiler option [C++]
- -vmg compiler option [C++]
- vmg compiler option [C++]
- -vmb compiler option [C++]
- /vmb compiler option [C++]
- representation method compiler options [C++]
- /vmg compiler option [C++]
ms.assetid: ecdb391c-7dab-40b1-916b-673d10889fd4
ms.openlocfilehash: 25d24d7f92537f16e36213b8a8fd7b945fda7f5a
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504299"
---
# <a name="vmb-vmg-representation-method"></a>/vmb, /vmg (Darstellungsmethode)

Wählen Sie die Methode, die der Compiler verwendet, die Zeiger auf Klassenmember darstellt.

Verwendung **/vmb** , wenn Sie immer eine Klasse definieren, bevor Sie einen Zeiger auf einen Member der Klasse deklarieren.

Verwendung **/vmg** auf einen Zeiger auf einen Member einer Klasse zu deklarieren, bevor Sie die Klasse definieren. Diese Anforderung kann auftreten, wenn Sie Elemente in zwei verschiedenen Klassen zu definieren, die aufeinander verweisen. Für solche Klassen mit gegenseitigem verweisen muss eine Klasse verwiesen werden, bevor sie definiert ist.

## <a name="syntax"></a>Syntax

```
/vmb
/vmg
```

## <a name="remarks"></a>Hinweise

Sie können auch [Pointers_to_members](../../preprocessor/pointers-to-members.md) oder [Vererbungsschlüsselwörter](../../cpp/inheritance-keywords.md) im Code, um eine Darstellung als Zeiger angeben.

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
