---
title: -Utf-8 (Quelle festlegen und ausführbare Datei legt in UTF-8-Zeichen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /utf-8
dev_langs:
- C++
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 218ea7986e37ce9cfa98aeeb1da3c209bef73f8f
ms.sourcegitcommit: 92c568e9466ffd7346a4120c478c9bdea61c8756
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2018
ms.locfileid: "47029683"
---
# <a name="utf-8-set-source-and-executable-character-sets-to-utf-8"></a>/UTF-8 (Quelle festlegen und ausführbare Zeichensätze auf UTF-8)

Gibt an, sowohl der quellzeichensatz der ausführungszeichensatz als UTF-8.

## <a name="syntax"></a>Syntax

```
/utf-8
```

## <a name="remarks"></a>Hinweise

Sie können die **/utf-8** verwenden, um anzugeben, sowohl die Quell-und legt fest, wie mithilfe von UTF-8 codiert. Dies ist äquivalent zum Angeben von **/source-Charset:utf-8 /execution-Charset:utf-8** in der Befehlszeile. Diese Optionen auch ermöglicht die **/Validate-CharSet** standardmäßig die Option. Eine Liste der unterstützten Codepage-IDs und Namen der Zeichensatz, finden Sie unter [Codepage-IDs](/windows/desktop/Intl/code-page-identifiers).

Standardmäßig erkennt Visual Studio eine Bytereihenfolge-Marke, um festzustellen, ob die Quelldatei in eine codierte Unicode-Format, z. B. UTF-16 oder UTF-8 ist. Wenn keine Bytereihenfolge-Marke befindet, es geht davon aus die Quelldatei codiert mithilfe der aktuellen Codepage für Benutzer, es sei denn, Sie mithilfe eine Codepage angegeben haben **/utf-8** oder **/Source-CharSet** Option. Visual Studio können Sie C++-Quellcode mithilfe der verschiedenen zeichencodierungen zu speichern. Weitere Informationen zu Quell- und ausführungszeichensätze, finden Sie unter [Zeichensätze](../../cpp/character-sets.md) in der Dokumentation zur Sprache.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Erweitern Sie die **Konfigurationseigenschaften**, **C/C++-**, **Befehlszeile** Ordner.

1. In **erweiterte Optionen**, Hinzufügen der **/utf-8** aus, und geben Sie Ihre bevorzugten Codierung.

1. Wählen Sie **OK** zum Speichern der Änderungen.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[/ Execution-CharSet (Ausführungszeichensatz festlegen)](../../build/reference/execution-charset-set-execution-character-set.md)<br/>
[/source-charset (Quellzeichensatz festlegen)](../../build/reference/source-charset-set-source-character-set.md)<br/>
[/validate-charset (Auf kompatible Zeichen überprüfen)](../../build/reference/validate-charset-validate-for-compatible-characters.md)