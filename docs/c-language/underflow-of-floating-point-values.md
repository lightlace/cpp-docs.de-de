---
title: Unterlauf von Gleitkommawerten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 78af8016-643c-47db-b4f1-7f06cb4b243e
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 6383f383221bb18c1dc58223e7183531bfd3c2d2
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="underflow-of-floating-point-values"></a>Unterlauf von Gleitkommawerten
**ANSI 4.5.1** Ob die mathematischen Funktionen den ganzzahligen Ausdruck `errno` bei Unterlaufbereichsfehlern auf den Wert des `ERANGE`-Makros festlegen  
  
 Ein Gleitkommaunterlauf legt den Ausdruck `errno` nicht auf `ERANGE` fest. Wenn ein Wert nahe 0 (Null) ist und schließlich ein Unterlauf stattfindet, wird der Wert auf 0 (Null) festgelegt.  
  
## <a name="see-also"></a>Siehe auch  
 [Bibliotheksfunktionen](../c-language/library-functions.md)
