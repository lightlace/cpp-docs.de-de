---
title: Rangfolge bei Makrodefinitionen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ce6f0acc898dc719d2252d5cc59dff92bda4a98
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368612"
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