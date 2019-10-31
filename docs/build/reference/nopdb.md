---
title: /NOPDB
description: Mit der/NOPDB-Option wird das Laden und Durchsuchen von PDB-Dateien für Symbol Informationen durch DUMPBIN verhindert.
ms.date: 10/29/2019
f1_keywords:
- /NOPDB
helpviewer_keywords:
- /NOPDB dumpbin option
- /NOPDB
ms.openlocfilehash: 3b745049517888d13de245d4e29be3985c122ada
ms.sourcegitcommit: 6ed1bc5b26dc60a780c1fc5f2f19d57ba1dc47d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73145746"
---
# <a name="nopdb"></a>/NOPDB

Weist DUMPBIN an, Programm Datenbankdateien (PDB-Dateien) für Symbol Informationen zu laden und zu durchsuchen.

## <a name="syntax"></a>Syntax

> **/NOPDB**

## <a name="remarks"></a>Hinweise

Standardmäßig versucht DUMPBIN, PDB-Dateien für die Zielobjekt Dateien, Bibliotheken oder ausführbaren Dateien zu laden. DUMPBIN verwendet diese Informationen, um Adressen mit Symbolnamen abzugleichen. Der Prozess kann zeitaufwändig sein, wenn die PDB-Dateien groß sind oder von einem Remote Server geladen werden müssen. Die Option **/NOPDB** weist DUMPBIN an, diesen Schritt zu überspringen. Sie druckt nur die Adressen und Symbol Informationen, die in der Objektdatei, der Bibliothek oder der ausführbaren Datei verfügbar sind.

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
