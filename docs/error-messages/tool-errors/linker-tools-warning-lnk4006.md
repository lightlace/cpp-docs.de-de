---
title: Linkertoolwarnung Lnk4006 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4006
dev_langs:
- C++
helpviewer_keywords:
- LNK4006
ms.assetid: 3a637d17-1676-4ea6-bd8b-290137d28d3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 261d5dcc27c44291ddc6de4a6440cde040a84ed7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302554"
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