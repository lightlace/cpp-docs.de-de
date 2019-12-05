---
title: /NOPDB
description: Mit der/NOPDB-Option wird das Laden und Durchsuchen von PDB-Dateien für Symbol Informationen durch DUMPBIN verhindert.
ms.date: 12/04/2019
f1_keywords:
- /NOPDB
helpviewer_keywords:
- /NOPDB dumpbin option
- /NOPDB
ms.openlocfilehash: 7b0c01e59b52bcec6ddf09416dd6aac9999527a6
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856968"
---
# <a name="nopdb"></a>/NOPDB

Weist DUMPBIN an, Programm Datenbankdateien (PDB-Dateien) für Symbol Informationen zu laden und zu durchsuchen.

## <a name="syntax"></a>Syntax

> **/NOPDB**

## <a name="remarks"></a>Hinweise

Standardmäßig versucht DUMPBIN, PDB-Dateien für die ausführbaren Zieldateien zu laden. DUMPBIN verwendet diese Informationen, um Adressen mit Symbolnamen abzugleichen. Der Prozess kann zeitaufwändig sein, wenn die PDB-Dateien groß sind oder von einem Remote Server geladen werden müssen. Die Option **/NOPDB** weist DUMPBIN an, diesen Schritt zu überspringen. Es werden nur die in der ausführbaren Datei verfügbaren Adressen und Symbol Informationen ausgegeben.

### <a name="to-set-the-nopdb-linker-option-in-visual-studio"></a>So legen Sie die Option "/NOPDB Linker" in Visual Studio fest

1. Öffnen Sie das Dialogfeld **Eigenschaften Seiten** für das Projekt. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Klicken Sie auf der Eigenschaftenseite auf **Konfigurationseigenschaften** > **Linker** > **Befehlszeile**.

1. Fügen Sie im Feld **zusätzliche Optionen** die Option **/NOPDB** hinzu. Wählen Sie **OK** oder **anwenden** aus, um die Änderungen zu speichern.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Diese Option hat keine programmgesteuerte Entsprechung.

## <a name="see-also"></a>Siehe auch

[DUMPBIN-Befehlszeilen](dumpbin-command-line.md)\
[DUMPBIN-Optionen](dumpbin-options.md)\
[DUMPBIN-Referenz](dumpbin-reference.md)
