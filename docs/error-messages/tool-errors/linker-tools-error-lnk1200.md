---
title: Linkertoolfehler Lnk1200 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1200
dev_langs: C++
helpviewer_keywords: LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 792c81e36b99bbac6c0417f0230bb1ea2bb1787c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1200"></a>Linkertoolfehler LNK1200
Fehler beim Lesen der Programmdatenbank 'Dateiname'  
  
 Die Programmdatenbank (PDB) konnte nicht gelesen werden.  
  
 Dieser Fehler kann durch eine beschädigte Datei verursacht werden.  
  
 Wenn `filename` ist die PDB-Datei für eine Objektdatei neu kompilieren, das Objekt mit [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md).  
  
 Wenn `filename` ist die PDB-Datei für die main-Ausgabedatei, und dieser Fehler ist aufgetreten, während der inkrementellen verknüpfen, die PDB-Datei und anschließend löschen.