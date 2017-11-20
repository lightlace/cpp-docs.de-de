---
title: Struktur einer Bibliothek | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: libraries, structure
ms.assetid: a5fda8e8-4a1b-4499-9095-0df935262ce4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 875dddb961b18378029de08582e728ad626be948
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="structure-of-a-library"></a>Struktur einer Bibliothek
Eine Bibliothek enthält COFF-Objekte. Objekte in einer Bibliothek enthalten Funktionen und Daten, die von anderen Objekten in einem Programm extern verwiesen werden können. Ein Objekt in einer Bibliothek wird manchmal als eines Bibliothekmembers bezeichnet.  
  
 Sie können zusätzliche Informationen zum Inhalt einer Bibliothek abrufen, indem Sie das Tool DUMPBIN mit der Option/LINKERMEMBER ausführen. Weitere Informationen zu dieser Option finden Sie unter [DUMPBIN-Referenz](../../build/reference/dumpbin-reference.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über LIB](../../build/reference/overview-of-lib.md)