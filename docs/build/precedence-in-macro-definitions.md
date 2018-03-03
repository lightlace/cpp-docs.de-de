---
title: Rangfolge bei Makrodefinitionen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7421ef51c37e3724bdb986321581e6736a62e18b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="precedence-in-macro-definitions"></a>Vorrang bei Makrodefinitionen
Wenn ein Makro mehrere Definitionen verfügt, verwendet NMAKE die Definition die höchsten Rangfolge. Die folgende Liste zeigt die Rangfolge, vom höchsten zum niedrigsten:  
  
1.  Ein Makro definiert, in der Befehlszeile  
  
2.  Ein Makro in einem Makefile definiert oder Includedatei  
  
3.  Eine geerbte Umgebungsvariable Makro  
  
4.  Ein Makro, das in der Datei Tools.ini definiert  
  
5.  Ein vordefiniertes Makro, z. B. [CC](../build/command-macros-and-options-macros.md) und [AS](../build/command-macros-and-options-macros.md)  
  
 Mit der Makros von Umgebungsvariablen Makefilemakros mit demselben Namen überschreiben geerbte dazu führen, dass/e. Verwendung **! UNDEF** über die Befehlszeile zu überschreiben.  
  
## <a name="see-also"></a>Siehe auch  
 [Definieren eines NMAKE-Makros](../build/defining-an-nmake-macro.md)