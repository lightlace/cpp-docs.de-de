---
title: Linkertoolfehler Lnk1201 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1201
dev_langs:
- C++
helpviewer_keywords:
- LNK1201
ms.assetid: 64c3f496-a428-4b54-981e-faa82ef9c8a1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 44e2ad811645889cd655bf297f6f8b9492574def
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1201"></a>Linkertoolfehler LNK1201
Fehler beim Schreiben in die Programmdatenbank 'Dateiname'; Suchen nach nicht genügend Speicherplatz verfügbar, Ungültiger Pfad oder unzureichend  
  
 LINK konnte in die Programmdatenbank (PDB) für die Ausgabedatei nicht geschrieben werden.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Die Datei ist beschädigt. Löschen Sie PDB-Datei und anschließend.  
  
2.  Nicht genügend Speicherplatz zum Schreiben der Datei.  
  
3.  Laufwerk ist nicht verfügbar, möglicherweise aufgrund eines Netzwerkproblems.  
  
4.  Der Debugger ist aktiv, auf die Anwendung, die Sie verknüpfen möchten.  
  
5.  Nicht genügend Speicherplatz auf dem Heap.  Finden Sie unter [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) für Weitere Informationen.