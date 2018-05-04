---
title: Sonderzeichen in Makros | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- special characters, in NMAKE macros
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c271d2f39a4d81776c06a107616170192e82d40d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="special-characters-in-macros"></a>Sonderzeichen in Makros
Mit einem Nummernzeichen (#) nach eine Definition gibt einen Kommentar an. Verwenden Sie ein Caretzeichen (^), um ein literal Nummernzeichen in einem Makro angeben, wie in ^ #.  
  
 Ein Dollarzeichen ($) wird ein Makroaufruf. Verwenden Sie zum Angeben eines literalen $ $$.  
  
 Um eine Definition in eine neue Zeile zu erweitern, beenden Sie die Zeile mit einem umgekehrten Schrägstrich (\\). Wenn das Makro aufgerufen wird, wird das umgekehrten Schrägstrich sowie neue-Zeile-Zeichen durch ein Leerzeichen ersetzt. Um einen literalen umgekehrten Schrägstrich am Ende der Zeile anzugeben, ein Caretzeichen (^) voran, oder führen Sie es mit einem Kommentar-Spezifizierer (#).  
  
 Beenden Sie die Zeile mit der ein Caretzeichen (^), um ein literal Zeilenumbruchzeichen anzugeben, wie in:  
  
```  
CMDS = cls^  
dir  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Definieren eines NMAKE-Makros](../build/defining-an-nmake-macro.md)