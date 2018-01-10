---
title: Sonderzeichen in Makros | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: special characters, in NMAKE macros
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4d954abc593fcba3887da4f7ee4bd5ce1e443e18
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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