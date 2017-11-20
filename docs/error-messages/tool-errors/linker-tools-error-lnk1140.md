---
title: Linkertoolfehler Lnk1140 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1140
dev_langs: C++
helpviewer_keywords: LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f19c69fad3ac9cc25863bfe8cd4de8100dbf372e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1140"></a>Linkertoolfehler LNK1140
zu viele Module für Programmdatenbank; Verknüpfung mit der/PDB: NONE  
  
 Das Projekt enthält mehr als 4096 Module.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)  
  
1.  Verknüpfen mit [/PDB: NONE](../../build/reference/pdb-use-program-database.md).  
  
2.  Einige Module ohne Debuginformationen kompiliert.  
  
3.  Reduzieren Sie die Anzahl der Module.