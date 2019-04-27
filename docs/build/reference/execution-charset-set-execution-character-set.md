---
title: / Execution-CharSet (Ausführungszeichensatz festlegen)
ms.date: 02/06/2019
f1_keywords:
- execution-charset
- /execution-charset
helpviewer_keywords:
- /execution-charset compiler option
- -execution-charset compiler option
ms.assetid: 0e02f487-2236-45bc-95f3-5760933a8f96
ms.openlocfilehash: 0a140bf438a44df152b1578f4569a087a604061c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62271436"
---
# <a name="execution-charset-set-execution-character-set"></a>/ Execution-CharSet (Ausführungszeichensatz festlegen)

Können Sie die ausführungszeichensatzes für die ausführbare Datei angeben.

## <a name="syntax"></a>Syntax

```
/execution-charset:[IANA_name|.CPID]
```

## <a name="arguments"></a>Argumente

*IANA_name*<br/>
Der IANA-definierten Zeichensatzname.

*CPID*<br/>
Der Codepagebezeichner.

## <a name="remarks"></a>Hinweise

Sie können die **/Execution-CharSet** verwenden, um eine ausführungszeichensatzes anzugeben. Die ausführungszeichengruppe ist die Codierung für den Text des Programms, die in der Kompilierungsphase vorverarbeitung nachdem alle Schritte eingegeben wird. Dieser Zeichensatz wird für die interne Darstellung jeder Zeichenfolgen- oder Zeichenliteralen im kompilierten Code verwendet. Legen Sie diese Option aus, geben Sie die erweiterten ausführungszeichensatzes verwenden, wenn Ihre Quelldateien Zeichen enthalten, die nicht im grundlegenden ausführungszeichensatz dargestellt werden kann. Können Sie entweder die IANA Name des Zeichensatzes ISO oder ein Punkt (.) gefolgt von einer 3 bis 5 Ziffern decimal-Codepagebezeichner der zu verwendenden Zeichensatz angeben. Eine Liste der unterstützten Codepage-IDs und Namen der Zeichensatz, finden Sie unter [Codepage-IDs](/windows/desktop/Intl/code-page-identifiers).

Standardmäßig erkennt Visual Studio eine Bytereihenfolge-Marke, um festzustellen, ob die Quelldatei in eine codierte Unicode-Format, z. B. UTF-16 oder UTF-8 ist. Wenn keine Bytereihenfolge-Marke befindet, es geht davon aus die Quelldatei mit der aktuellen Codepage für Benutzer, es sei denn, die Sie angegeben haben, einen Character set, Name oder die Codepage mit ist codiert die **/Source-CharSet** Option oder die **/utf-8** Option. Visual Studio können Sie C++-Quellcode mithilfe der verschiedenen zeichencodierungen zu speichern. Weitere Informationen zu Quell- und ausführungszeichensätze, finden Sie unter [Zeichensätze](../../cpp/character-sets.md) in der Dokumentation zur Sprache.

Wenn Sie sowohl die Quell- und ausführungszeichensatz in UTF-8 festlegen möchten, können Sie mithilfe der **/utf-8** Compileroption als Kurzform. Dies ist äquivalent zum Angeben von **/source-Charset:utf-8 /execution-Charset:utf-8** in der Befehlszeile. Diese Optionen auch ermöglicht die **/Validate-CharSet** standardmäßig die Option.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Erweitern Sie die **Konfigurationseigenschaften**, **C/C++-**, **Befehlszeile** Ordner.

1. In **zusätzliche Optionen**, Hinzufügen der **/Execution-CharSet** aus, und geben Sie Ihre bevorzugten Codierung.

1. Klicken Sie auf **OK**, um die Änderungen zu speichern.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)<br/>
[/source-charset (Quellzeichensatz festlegen)](source-charset-set-source-character-set.md)<br/>
[/utf-8 (Quelle und ausführbare Zeichensätze auf UTF-8 festlegen)](utf-8-set-source-and-executable-character-sets-to-utf-8.md)<br/>
[/validate-charset (Auf kompatible Zeichen überprüfen)](validate-charset-validate-for-compatible-characters.md)
