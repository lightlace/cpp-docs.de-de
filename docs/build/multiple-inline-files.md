---
title: Mehrere Inlinedateien | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inline files, multiple NMAKE
- multiple inline files
- NMAKE program, inline files
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ee9be15f029c0aaab3ca4bc47fb183e1499c2e2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368212"
---
# <a name="multiple-inline-files"></a>Mehrere Inlinedateien
Ein Befehl kann mehr als eine Inlinedatei erstellen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      command << <<  
inlinetext  
<<[KEEP | NOKEEP]  
inlinetext  
<<[KEEP | NOKEEP]  
```  
  
## <a name="remarks"></a>Hinweise  
 Geben Sie für jede Datei eine oder mehrere Textzeilen Inline gefolgt von einer schließenden-Zeile, die als Trennzeichen enthält. Die zweite Datei Text in der Zeile nach der begrenzenden Zeile für die erste Datei zu beginnen.  
  
## <a name="see-also"></a>Siehe auch  
 [Inlinedateien in einem Makefile](../build/inline-files-in-a-makefile.md)