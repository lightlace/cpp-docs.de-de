---
title: Linkertoolwarnung Lnk4001 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4001
dev_langs:
- C++
helpviewer_keywords:
- LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2ecc78fe50fd34a0c6f583bf103d368e23f19f2e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4001"></a>Linkertoolwarnung LNK4001
keine Objektdateien angegeben; Bibliotheken, verwendet werden  
  
 Der Linker wurde mindestens eine LIB-Dateien, aber keine OBJ-Dateien übergeben.  
  
 Da der Linker nicht auf Informationen in einer LIB-Datei zugreifen, die in einer OBJ-Datei zugreifen kann, gibt diese Warnung an, dass Sie andere Optionen des Linkers explizit angeben müssen. Angenommen, Sie geben möglicherweise die [/Computer](../../build/reference/machine-specify-target-platform.md), [/OUT](../../build/reference/out-output-file-name.md), oder [/Entry](../../build/reference/entry-entry-point-symbol.md) Optionen.