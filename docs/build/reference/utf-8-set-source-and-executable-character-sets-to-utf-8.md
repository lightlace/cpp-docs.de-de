---
title: /UTF-8 (Festlegen von Quell- und Ausführungszeichensätze auf UTF-8)
ms.date: 11/04/2016
f1_keywords:
- /utf-8
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
ms.openlocfilehash: 5ac15c63041e76b8bb0d292868bb982c21866078
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317288"
---
# <a name="utf-8-set-source-and-executable-character-sets-to-utf-8"></a>/UTF-8 (Festlegen von Quell- und Ausführungszeichensätze auf UTF-8)

Gibt sowohl den Quell- als auch den Ausführungszeichensatz als UTF-8 an.

## <a name="syntax"></a>Syntax

```
/utf-8
```

## <a name="remarks"></a>Hinweise

Sie können die **/utf-8** verwenden, um anzugeben, sowohl die Quell-und legt fest, wie mithilfe von UTF-8 codiert. Dies ist äquivalent zum Angeben von **/source-Charset:utf-8 /execution-Charset:utf-8** in der Befehlszeile. Diese Optionen auch ermöglicht die **/Validate-CharSet** standardmäßig die Option. Eine Liste der unterstützten Codepage-IDs und Namen der Zeichensatz, finden Sie unter [Codepage-IDs](/windows/desktop/Intl/code-page-identifiers).

Standardmäßig erkennt Visual Studio eine Bytereihenfolge-Marke, um festzustellen, ob die Quelldatei in eine codierte Unicode-Format, z. B. UTF-16 oder UTF-8 ist. Wenn keine Bytereihenfolge-Marke befindet, es geht davon aus die Quelldatei codiert mithilfe der aktuellen Codepage für Benutzer, es sei denn, Sie mithilfe eine Codepage angegeben haben **/utf-8** oder **/Source-CharSet** Option. Visual Studio können Sie C++-Quellcode mithilfe der verschiedenen zeichencodierungen zu speichern. Weitere Informationen zu Quell- und ausführungszeichensätze, finden Sie unter [Zeichensätze](../../cpp/character-sets.md) in der Dokumentation zur Sprache.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen des Compilers und der Buildeigenschaften](../working-with-project-properties.md).

1. Erweitern Sie die **Konfigurationseigenschaften**, **C/C++-** , **Befehlszeile** Ordner.

1. In **zusätzliche Optionen**, Hinzufügen der **/utf-8** verwenden, um die bevorzugte Codierung anzugeben.

1. Klicken Sie auf **OK**, um die Änderungen zu speichern.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)<br/>
[/ Execution-CharSet (Ausführungszeichensatz festlegen)](execution-charset-set-execution-character-set.md)<br/>
[/source-charset (Quellzeichensatz festlegen)](source-charset-set-source-character-set.md)<br/>
[/validate-charset (Auf kompatible Zeichen überprüfen)](validate-charset-validate-for-compatible-characters.md)
