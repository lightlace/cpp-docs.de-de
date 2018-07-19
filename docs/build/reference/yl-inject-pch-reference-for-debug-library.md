---
title: -Yl (PCH-Verweis für Debugbibliothek einfügen) | Microsoft Docs
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /yl
dev_langs:
- C++
helpviewer_keywords:
- -Yl compiler option [C++]
- Yl compiler option [C++]
- /Yl compiler option [C++]
ms.assetid: 8e4a396a-6790-4a9f-8387-df015a3220e7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a73e79cd50343292ae63dfa831a7638d6444fc64
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378469"
---
# <a name="yl-inject-pch-reference-for-debug-library"></a>/Yl (PCH-Verweis für Debugbibliothek einfügen)

Die **/Yl** Option generiert ein eindeutige Symbol in einer vorkompilierten Headerdatei und ein Verweis auf dieses Symbol wird in allen Objektdateien, die Verwendung des vorkompilierten Headers eingefügt.

## <a name="syntax"></a>Syntax

>**/ Yl**  
>**/ Yl**_Name_  
>**/Yl-**  

### <a name="arguments"></a>Argumente

*name*  
Ein optionaler Name, der als Teil der das eindeutige Symbol verwendet.

*\-*  
Deaktiviert ein Bindestrich (-) explizit die **/Yl** -Compileroption.

## <a name="remarks"></a>Hinweise

Die **/Yl** -Compileroption erstellt eine eindeutige Symboldefinition in eine vorkompilierte Headerdatei erstellt mithilfe der ["/ Yc"](../../build/reference/yc-create-precompiled-header-file.md) Option. Verweise auf dieses Symbol werden automatisch eingefügt, in allen Dateien, die durch die Verwendung des vorkompilierten Headers einbeziehen der ["/ Yu"](../../build/reference/yu-use-precompiled-header-file.md) -Compileroption. Die **/Yl** Option ist standardmäßig aktiviert, wenn **"/ Yc"** wird verwendet, um eine vorkompilierte Headerdatei zu erstellen.

Die **/Yl**_Namen_ Option wird verwendet, um einen identifizierbaren Symbol in der vorkompilierten Headerdatei erstellen. Der Compiler verwendet den *Namen* Argument als Teil des ergänzten Symbolnamens erstellt, ähnlich wie \_ \_ @@ \_PchSym\_@00@... @ *Namen*, wobei die Auslassungszeichen (...) dar, die eine eindeutige vom Compiler generiertes Zeichenfolge Zeichen. Wenn die *Namen* Argument nicht angegeben wird, generiert der Compiler automatisch einen Symbolnamen. Normalerweise müssen Sie nicht den Namen des Symbols kennen. Wenn Ihr Projekt verwendet jedoch mehr als eine vorkompilierte Headerdatei der **/Yl**_Namen_ Option ist möglicherweise nützlich, um zu ermitteln, welches Objekt verwenden sollen die vorkompilierten Header. Sie können *Namen* als eine Suchzeichenfolge Deklarationstyp in einer Dumpdatei gefunden.

**/Yl-** deaktiviert das Standardverhalten und fügen ein identifizierende Symbol nicht in die vorkompilierte Headerdatei. Kompilierte Dateien, die diesen vorkompilierte Header enthalten ist eine allgemeine Deklarationstyp nicht abgerufen werden.

Wenn **"/ Yc"** nicht angegeben ist, alle **/Yl** Option hat keine Auswirkung, aber wenn angegeben, muss er entspricht jedem **/Yl** Option übergeben, wenn **"/ Yc"** ist angegeben.

Bei Verwendung von **/Yl-**, **"/ Yc"** und ["/ Z7"](../../build/reference/z7-zi-zi-debug-information-format.md) Optionen zum Erstellen der vorkompilierten Headerdatei, die Debuginformationen befindet sich in der Objektdatei die Quelldatei, die zum Erstellen der vorkompilierte Header, anstatt eine separate PDB-Datei. Wenn diese Objektdatei Teil einer Bibliothek, dann erfolgt [LNK1211](../../error-messages/tool-errors/linker-tools-error-lnk1211.md) Fehler oder [LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md) Warnungen können in Builds, die die Bibliothek und die vorkompilierte Headerdatei verwenden auftreten, wenn die Quelldatei, die zum Erstellen verwendet die vorkompilierte Headerdatei werden keine Symbole selbst definiert. Der Linker kann die Objektdatei über den Link, zusammen mit den zugehörigen Debuginformationen ausschließen, wenn "nothing" in der Objektdatei in der bibliothekclient verwiesen wird. Geben Sie zum Lösen dieses Problems **/Yl** (oder entfernen Sie die **/Yl-** Option) bei Verwendung von **"/ Yc"** zum Erstellen der vorkompilierten Header-Datei. Dadurch wird sichergestellt, dass die Objektdatei aus der Bibliothek, die die Debuginformationen enthält, die in Ihrem Build verknüpft ruft.

Weitere Informationen zu vorkompilierten Headern finden Sie unter:

- [/Y (Vorkompilierte Header)](../../build/reference/y-precompiled-headers.md)

- [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Hinzufügen der **/Yl**_Namen_ -Compileroption in der **Zusatzoptionen** Feld. Wählen Sie **OK** zum Speichern der Änderungen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)  
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)  
