---
title: Linkertoolwarnung Lnk4001 | Microsoft Docs
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
ms.openlocfilehash: acf65c00c5c039769a05e009dcfe46ea42633ac4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4001"></a>Linkertoolwarnung LNK4001
keine Objektdateien angegeben; Bibliotheken, verwendet werden  
  
 Der Linker wurde mindestens eine LIB-Dateien, aber keine OBJ-Dateien übergeben.  
  
 Da der Linker nicht auf Informationen in einer LIB-Datei zugreifen, die in einer OBJ-Datei zugreifen kann, gibt diese Warnung an, dass Sie andere Optionen des Linkers explizit angeben müssen. Angenommen, Sie geben möglicherweise die [/Computer](../../build/reference/machine-specify-target-platform.md), [/OUT](../../build/reference/out-output-file-name.md), oder [/Entry](../../build/reference/entry-entry-point-symbol.md) Optionen.