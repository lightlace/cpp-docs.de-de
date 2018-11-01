---
title: Linkertoolwarnung LNK4001
ms.date: 11/04/2016
f1_keywords:
- LNK4001
helpviewer_keywords:
- LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
ms.openlocfilehash: 75ca9ec92bbba1c15efc11a731b3894ea03e33dd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651424"
---
# <a name="linker-tools-warning-lnk4001"></a>Linkertoolwarnung LNK4001

keine Objektdateien angegeben; Bibliotheken, verwendet werden

Der Linker wurde mindestens eine LIB-Dateien, aber keine OBJ-Dateien übergeben.

Da der Linker nicht auf Informationen in einer LIB-Datei zugreifen, die sie in einer OBJ-Datei zugreifen kann, gibt diese Warnung an, dass Sie andere Optionen des Linkers explizit angeben müssen. Angenommen, Sie geben möglicherweise den [/MACHINE](../../build/reference/machine-specify-target-platform.md), [/OUT](../../build/reference/out-output-file-name.md), oder [/Entry](../../build/reference/entry-entry-point-symbol.md) Optionen.