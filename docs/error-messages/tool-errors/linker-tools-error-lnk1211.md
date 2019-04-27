---
title: Linkertoolfehler LNK1211
ms.date: 12/05/2017
f1_keywords:
- LNK1211
helpviewer_keywords:
- LNK1211
ms.assetid: 607400eb-4180-4892-817f-eedfa628af61
ms.openlocfilehash: 7c918cacb87460c2aad30285b750d9b170425534
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242668"
---
# <a name="linker-tools-error-lnk1211"></a>Linkertoolfehler LNK1211

> Vorkompilierte Typinformationen nicht gefunden. "*Filename*' nicht verknüpft oder überschrieben

Die *Filename* kompilierte Objektdatei wird, mithilfe von ["/ Yc"](../../build/reference/yc-create-precompiled-header-file.md), wurde im LINK-Befehl nicht angegeben oder überschrieben.

Wenn Sie eine Debugbibliothek erstellen, die vorkompilierten Header verwendet und bei Angabe **"/ Yc"** und ["/ Z7"](../../build/reference/z7-zi-zi-debug-information-format.md), Visual C++ generiert eine vorkompilierte Objektdatei, die Debuginformationen enthält. Der Fehler tritt auf, nur wenn Sie die Datei Vorkompiliertes Objekt in einer Bibliothek speichern, verwenden Sie die Bibliothek, um ein ausführbares Image zu erstellen und die Objektdateien, auf die verwiesen werden, haben keine transitive Verweise auf eine der Funktionen, die die Datei Vorkompiliertes Objekt definiert.

Es gibt zwei Methoden, um zu dieser Situation umgehen:

- Geben Sie die [/Yd ablegen](../../build/reference/yd-place-debug-information-in-object-file.md) -Compileroption verwenden, um die Debuginformationen aus dem vorkompilierten Header jedes Objektmodul hinzufügen. Diese Methode ist nicht das bevorzugte Tag, da es im Allgemeinen LOB-Modulen erzeugt, die die erforderliche Zeit zum Verknüpfen der Anwendungs erhöhen kann.

- Geben Sie [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) und übergeben Sie den Namen einer beliebigen Zeichenfolge, aus, wenn Sie eine vorkompilierte Headerdatei erstellen, die keine Funktionsdefinitionen enthält. Dies weist den Compiler an, um ein Symbol in der Datei Vorkompiliertes Objekt zu erstellen und einen Verweis auf das Symbol im einzelnen Objektdateien auszugeben, die die vorkompilierte Headerdatei verwendet werden, die die Datei Vorkompiliertes Objekt zugeordnet ist.

Beim Kompilieren eines Moduls mit **"/ Yc"** und **/Yl**, erstellt der Compiler ein Symbol ähnelt `__@@_PchSym_@00@...@symbol_name`, wobei die Auslassungspunkte (...) stellt eine vom Compiler generierte Zeichenfolge und speichert ihn in das Objektmodul. Jeder Quelldatei, die Sie mit diesem vorkompilierten Header kompilieren bezieht sich auf das angegebene Symbol aus, wodurch den Linker an, die Objekt-Modul und die Debuginformationen aus der Bibliothek enthalten.
