---
title: /GH (_pexit-Hookfunktion aktivieren)
ms.date: 11/04/2016
f1_keywords:
- _pexit
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _pexit function
- -Gh compiler option [C++]
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
ms.openlocfilehash: 077096cc296f2aa2128127493a84a91da9a067c5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62270912"
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
void __declspec(naked) __cdecl _pexit( void );
```

`_pexit` ist vergleichbar mit `_penter`; finden Sie unter [/GH (aktivieren _penter-Hookfunktion)](gh-enable-penter-hook-function.md) verdeutlicht, wie Sie schreiben eine `_pexit` Funktion.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
