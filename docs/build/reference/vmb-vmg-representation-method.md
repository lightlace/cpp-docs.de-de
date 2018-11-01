---
title: / vmb, - Vmg (Darstellungsmethode)
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
ms.openlocfilehash: 30d15105b9fe502e89f77b19e530d6cc762975a8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505494"
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

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)