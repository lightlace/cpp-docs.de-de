---
title: "-Yl (PCH-Verweis für Debugbibliothek einfügen) | Microsoft Docs"
ms.custom: 
ms.date: 12/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /yl
dev_langs: C++
helpviewer_keywords:
- -Yl compiler option [C++]
- Yl compiler option [C++]
- /Yl compiler option [C++]
ms.assetid: 8e4a396a-6790-4a9f-8387-df015a3220e7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6e777977f6d869d2bbc28d980f6445851e54396b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="yl-inject-pch-reference-for-debug-library"></a>/Yl (PCH-Verweis für Debugbibliothek einfügen)

Die **/Yl** Option erstellt eine allgemeine Symbol für eine vorkompilierte Headerdatei und fügt Verweise auf dieses Symbol in allen Dateien, die Verwendung des vorkompilierten Headers. Dadurch wird die vollständige Typinformationen für vorkompilierte headersymbole an dem Debugger in allen Dateien, die Verwendung des vorkompilierten Headers verfügbar. Diese Option ist standardmäßig aktiviert. Verwendung dieser Option kann verhindern, dass Linkerfehler aufgrund fehlender Debuginformationen in verknüpfte Bibliotheken, die vorkompilierte Header verwenden.

## <a name="syntax"></a>Syntax

>**/ Yl**  
>**/ Yl**_Name_  
>**/Yl-**  

### <a name="arguments"></a>Argumente

*name*  
Ein optionaler Name verwendet, um ein Symbol, um gespeicherte und verwiesen wird, in Objektdateien sein, die definieren, oder den vorkompilierten Header verwenden definieren.

*\-*  
Deaktiviert ein Bindestrich (-) explizit die **/Yl** -Compileroption.

## <a name="remarks"></a>Hinweise

Die **/Yl** Option ermöglicht dem Debugger, um vollständige Informationen zu Typen in eine vorkompilierte Headerdatei in jeder Datei abzurufen, die den vorkompilierten Header enthält. Diese Option erstellt eine interne Symbolnamen, fügt die Symboldefinition in der Objektdatei, die zum Erstellen des vorkompilierten Headers durch die ["/ Yc"](../../build/reference/yc-create-precompiled-header-file.md) aus, und fügt einen Verweis auf das Symbol in allen Dateien, die der vorkompilierte enthalten Header mit dem ["/ Yu"](../../build/reference/yu-use-precompiled-header-file.md) -Compileroption. Da alle Quelldateien, die Verwendung des vorkompilierten Headers in der benannten Symbol verweisen, verknüpft der Linker immer die Objektdatei, die das Symbol und der zugehörigen vorkompilierte Header Debuginformationen definiert. Diese Option ist standardmäßig aktiviert.

Die **/Yl**_Namen_ Option wird verwendet, um explizit das identifizierende Symbol für die vorkompilierte Headerdatei erstellen. Der Compiler verwendet den *Namen* Argument zum Erstellen eines Symbols ähnlich \_ \_ @@ \_PchSym\_@00@... @*Name* , wobei die Auslassungszeichen (...) stellt einen vom Linker generierte Zeichenfolge. Das Argument nicht angegeben ist, generiert der Compiler automatisch einen Symbolnamen an.

**/Yl-** deaktiviert das Standardverhalten und fügen eine identifizierende Deklarationstyp nicht in den Objektdateien, die den vorkompilierten Header enthalten. Diese Option möglicherweise erforderlich, damit Dateien, die kompiliert, ohne die vorkompilierte Headerdatei vorhanden sein.

Bei Verwendung von **/Yl-**, **"/ Yc"** und ["/ Z7"](../../build/reference/z7-zi-zi-debug-information-format.md) Optionen zum Erstellen einer Bibliothek, die der Compiler erstellt eine vorkompilierte Headerdatei, die Debuginformationen enthält, die in gespeichert ist ein Objektdatei eher als eine PDB-Datei. [LNK1211](../../error-messages/tool-errors/linker-tools-error-lnk1211.md) Fehler oder [LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md) Warnungen können auftreten, in Builds, die diese Bibliothek verwenden, und der vorkompilierte Header, wenn die Quelldatei, die zum Erstellen des vorkompilierten Headers verwendet keine Symbole nicht definiert. Der Linker kann diese Bibliotheksdatei für das Objekt über den Link, zusammen mit der zugeordneten vorkompilierte Header Debuginformationen ausschließen, wenn es sich bei "nothing" in der Objektdatei in der bibliothekclient verwiesen wird. Um das Problem zu beheben, geben Sie **/Yl** bei Verwendung von **"/ Yc"** eine vorkompilierte Headerdatei erstellen und **"/ Yu"** , ihn zu verwenden. Dadurch wird sichergestellt, dass die Objektdatei, die die Debuginformationen enthält, die in Ihrem Build enthalten ist.

Weitere Informationen zu vorkompilierten Headern finden Sie unter:

- [/ Y (Vorkompilierte Header)](../../build/reference/y-precompiled-headers.md)

- [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Befehlszeile** Eigenschaftenseite in der **C/C++-** Ordner.

1. Hinzufügen der **/Yl**_Namen_ -Compileroption in der **Zusatzoptionen** Feld. Wählen Sie **OK** zum Speichern der Änderungen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)  
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)  
