---
title: Linkertoolwarnung LNK4001 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4001
dev_langs:
- C++
helpviewer_keywords:
- LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f684e85233c4df777a53f03f07936137c425946e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070418"
---
# <a name="linker-tools-warning-lnk4001"></a>Linkertoolwarnung LNK4001

keine Objektdateien angegeben; Bibliotheken, verwendet werden

Der Linker wurde mindestens eine LIB-Dateien, aber keine OBJ-Dateien übergeben.

Da der Linker nicht auf Informationen in einer LIB-Datei zugreifen, die sie in einer OBJ-Datei zugreifen kann, gibt diese Warnung an, dass Sie andere Optionen des Linkers explizit angeben müssen. Angenommen, Sie geben möglicherweise den [/MACHINE](../../build/reference/machine-specify-target-platform.md), [/OUT](../../build/reference/out-output-file-name.md), oder [/Entry](../../build/reference/entry-entry-point-symbol.md) Optionen.