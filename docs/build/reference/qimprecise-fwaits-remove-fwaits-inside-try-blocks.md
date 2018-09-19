---
title: -Qimprecise_fwaits (Entfernen von Fwaits in Try-Blöcken) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Qimprecise_fwaits
dev_langs:
- C++
helpviewer_keywords:
- -Qimprecise_fwaits compiler option (C++)
- /Qimprecise_fwaits compiler option (C++)
ms.assetid: b1501f21-7e08-4fea-95e8-176ec03a635b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98dc9416ecee69bca285ff54d6321144c4a3fd02
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45724424"
---
# <a name="qimprecisefwaits-remove-fwaits-inside-try-blocks"></a>/Qimprecise_fwaits (Entfernen von fwaits in Try-Blöcken)

Entfernt die `fwait` -Befehle in `try` blockiert, wenn Sie nutzen die [/fp: mit Ausnahme von](../../build/reference/fp-specify-floating-point-behavior.md) -Compileroption.

## <a name="syntax"></a>Syntax

```
/Qimprecise_fwaits
```

## <a name="remarks"></a>Hinweise

Diese Option hat keine Auswirkung, wenn **/fp: mit Ausnahme von** nicht ebenfalls angegeben. Bei Angabe der **/fp: mit Ausnahme von** -Option der Compiler Fügt eine `fwait` Befehl, um jede Zeile des Codes in eine `try` Block. Auf diese Weise kann der Compiler die bestimmte Zeile des Codes identifizieren, die eine Ausnahme erzeugt. **/ Qimprecise_fwaits** entfernt interne `fwait` Anweisungen, lassen nur die wartet, um die `try` Block. Dies verbessert die Leistung, aber der Compiler wird nur in der Lage, die sagen `try` Block löst eine Ausnahme, die nicht in der Zeile.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[/ Q-Optionen (Operationen auf niedriger Ebene)](../../build/reference/q-options-low-level-operations.md)
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)