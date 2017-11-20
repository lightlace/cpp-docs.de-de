---
title: Linkertoolwarnung Lnk4006 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4006
dev_langs: C++
helpviewer_keywords: LNK4006
ms.assetid: 3a637d17-1676-4ea6-bd8b-290137d28d3b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c39482dbf53e5a919e8af1927697ef06ba7972b3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-warning-lnk4006"></a>Linkertoolwarnung LNK4006
bereits im Objekt definiertes Symbol zweite Definition wird ignoriert  
  
 Das gegebene `symbol`, angezeigt in seiner ergänzten Form, wurde mehrfach definiert. Wenn diese Warnung erkannt wird, `symbol` wird zweimal hinzugefügt werden, aber nur die erste Form verwendet werden.  
  
 Sie können diese Warnung erhalten, wenn Sie versuchen, zwei Importbibliotheken in einer Zelle zusammenzuführen.  
  
 Wenn Sie die C-Laufzeitbibliothek neu sind, können Sie diese Meldung ignorieren.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)  
  
1.  Der angegebene `symbol` möglicherweise eine Paketfunktion, erstellt durch Kompilierung mit [/Gy](../../build/reference/gy-enable-function-level-linking.md). Dieses Symbol wurde in mehr als eine Datei enthalten, aber zwischen Kompilationen geändert. Kompilieren Sie alle Dateien, einschließlich der `symbol`.  
  
2.  Der angegebene `symbol` möglicherweise unterschiedlich definiert sein in zwei Memberobjekten in verschiedenen Bibliotheken.  
  
3.  Ein absoluter möglicherweise zweimal, mit einem anderen Wert in jeder Definition definiert wurden.  
  
4.  Wenn die Fehlermeldung erhalten, beim Kombinieren von Bibliotheken haben, `symbol` bereits in der Bibliothek hinzugefügt wird.