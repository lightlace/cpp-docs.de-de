---
title: Struktur einer Bibliothek | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- libraries, structure
ms.assetid: a5fda8e8-4a1b-4499-9095-0df935262ce4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6eff0000aef01790106b44b49b4855218fcf9332
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="structure-of-a-library"></a>Struktur einer Bibliothek
Eine Bibliothek enthält COFF-Objekte. Objekte in einer Bibliothek enthalten Funktionen und Daten, die von anderen Objekten in einem Programm extern verwiesen werden können. Ein Objekt in einer Bibliothek wird manchmal als eines Bibliothekmembers bezeichnet.  
  
 Sie können zusätzliche Informationen zum Inhalt einer Bibliothek abrufen, indem Sie das Tool DUMPBIN mit der Option/LINKERMEMBER ausführen. Weitere Informationen zu dieser Option finden Sie unter [DUMPBIN-Referenz](../../build/reference/dumpbin-reference.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über LIB](../../build/reference/overview-of-lib.md)