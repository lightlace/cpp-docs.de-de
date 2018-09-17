---
title: -GH (_pexit-Hookfunktion aktivieren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _pexit
dev_langs:
- C++
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _pexit function
- -Gh compiler option [C++]
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 489ff00571c79d89c9e807f0d8796989e7a0f84f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714987"
---
# <a name="gh-enable-pexit-hook-function"></a>/GH (_pexit-Hookfunktion aktivieren)

Ruft die `_pexit` Funktion am Ende jeder Methode oder Funktion.

## <a name="syntax"></a>Syntax

```
/GH
```

## <a name="remarks"></a>Hinweise

Die `_pexit` Funktion ist nicht Teil einer Bibliothek, und es ist Ihre Aufgabe, geben Sie eine Definition für `_pexit`.

Es sei denn, Sie planen, die explizit aufrufen `_pexit`, Sie müssen sich nicht um einen Prototyp bereitzustellen. Die Funktion muss angezeigt werden, als ob es den folgenden Prototyp hatte und Fördern Sie den Inhalt aller Register auf den Eintrag und pop die unveränderten Inhalt beim Beenden müssen:

```
void __declspec(naked) _cdecl _pexit( void );
```

`_pexit` ist vergleichbar mit `_penter`; finden Sie unter [/GH (aktivieren _penter-Hookfunktion)](../../build/reference/gh-enable-penter-hook-function.md) verdeutlicht, wie Sie schreiben eine `_pexit` Funktion.

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