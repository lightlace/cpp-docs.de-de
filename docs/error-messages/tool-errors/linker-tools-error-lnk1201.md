---
title: Linkertoolfehler Lnk1201 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1201
dev_langs: C++
helpviewer_keywords: LNK1201
ms.assetid: 64c3f496-a428-4b54-981e-faa82ef9c8a1
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 344f56eb3097bad447d9a0b12a0c5aac6f68b119
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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