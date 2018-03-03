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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ecea42172ed285f24a22cba004fb156784483643
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="underflow-of-floating-point-values"></a>Unterlauf von Gleitkommawerten
**ANSI 4.5.1** Ob die mathematischen Funktionen den ganzzahligen Ausdruck `errno` bei Unterlaufbereichsfehlern auf den Wert des `ERANGE`-Makros festlegen  
  
 Ein Gleitkommaunterlauf legt den Ausdruck `errno` nicht auf `ERANGE` fest. Wenn ein Wert nahe 0 (Null) ist und schließlich ein Unterlauf stattfindet, wird der Wert auf 0 (Null) festgelegt.  
  
## <a name="see-also"></a>Siehe auch  
 [Bibliotheksfunktionen](../c-language/library-functions.md)