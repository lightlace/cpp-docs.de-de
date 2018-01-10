---
title: Linkertoolfehler Lnk1211 | Microsoft Docs
ms.date: 12/05/2017
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1211
dev_langs: C++
helpviewer_keywords: LNK1211
ms.assetid: 607400eb-4180-4892-817f-eedfa628af61
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 51150fb2a57f48f04cca97e5f16fe1a28ead2c50
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1211"></a>Linkertoolfehler LNK1211

> Vorkompilierte Typinformationen nicht gefunden; "*Filename*' nicht verknüpft oder überschrieben

Die *Filename* kompilierte Objektdatei wird, mithilfe von ["/ Yc"](../../build/reference/yc-create-precompiled-header-file.md), in die LINK-Befehl wurde nicht angegeben oder überschrieben wurde.

Wenn Sie eine Debugbibliothek erstellen, die vorkompilierte Header verwendet und wenn Sie **"/ Yc"** und ["/ Z7"](../../build/reference/z7-zi-zi-debug-information-format.md), Visual C++ generiert eine vorkompilierte Objektdatei, die Debuginformationen enthält. Der Fehler tritt auf, nur wenn Sie die vorkompilierte Objektdatei in einer Bibliothek speichern, verwenden Sie die Bibliothek, um ein ausführbares Image zu erstellen und die Objektdateien, die referenziert wurden haben keine transitive Verweise auf eine der Funktionen, die vorkompilierte Objektdatei definiert.

Es gibt zwei Methoden, um dieses Problem zu umgehen:

- Geben Sie die [/Yd ablegen](../../build/reference/yd-place-debug-information-in-object-file.md) Compileroption, um die Debuginformationen aus den vorkompilierten Header jeder Objektmodul hinzufügen. Diese Methode ist weniger wünschenswert, da es im Allgemeinen LOB-Modulen erzeugt, die die erforderliche Zeit zum Verknüpfen der Anwendung erhöhen können.

- Geben Sie [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) und übergeben Sie den Namen einer beliebigen Zeichenfolge, aus, wenn Sie eine vorkompilierte Headerdatei erstellen, die keine Funktionsdefinitionen enthält. Dies weist den Compiler ein Symbol in der vorkompilierten Objektdatei erstellen und einen Verweis auf das Symbol in jeder Objektdatei auszugeben, die die vorkompilierte Headerdatei verwendet, die der vorkompilierten Objektdatei zugeordnet ist.

Beim Kompilieren eines Moduls mit **"/ Yc"** und **/Yl**, erstellt der Compiler ein Symbol, das ähnlich wie `__@@_PchSym_@00@...@symbol_name`, wobei die Auslassungspunkte (...) stellt eine vom Compiler generierte Zeichenfolge und speichert ihn in der Objektmodul. Quelldatei, die Sie mit diesem vorkompilierten Header kompilieren bezieht sich auf das angegebene Symbol aus, wodurch den Linker Objektmodul und seine Debuginformationen aus der Bibliothek aufgenommen werden sollen.
