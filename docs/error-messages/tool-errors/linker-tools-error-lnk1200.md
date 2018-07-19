---
title: Linkertoolfehler Lnk1200 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1200
dev_langs:
- C++
helpviewer_keywords:
- LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab32939c55dce5e27f907f3d23e639b24741cdc3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298823"
---
# <a name="linker-tools-error-lnk1200"></a>Linkertoolfehler LNK1200
Fehler beim Lesen der Programmdatenbank 'Dateiname'  
  
 Die Programmdatenbank (PDB) konnte nicht gelesen werden.  
  
 Dieser Fehler kann durch eine beschädigte Datei verursacht werden.  
  
 Wenn `filename` ist die PDB-Datei für eine Objektdatei neu kompilieren, das Objekt mit [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md).  
  
 Wenn `filename` ist die PDB-Datei für die main-Ausgabedatei, und dieser Fehler ist aufgetreten, während der inkrementellen verknüpfen, die PDB-Datei und anschließend löschen.