---
title: "Schließen von Dateien | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 27b1c59c952b022c7382db7d6b2dcb660cca2e9a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="closing-files"></a>Schließen von Dateien
Wie gewohnt in e/a-Vorgängen, müssen wenn Sie fertig, mit einer Datei sind, Sie es schließen.  
  
#### <a name="to-close-a-file"></a>Um eine Datei zu schließen.  
  
1.  Verwenden der **schließen** Memberfunktion. Diese Funktion schließt die Dateisystem Datei und leert Puffer bei Bedarf.  
  
 Wenn Sie zugeordnet der [CFile](../mfc/reference/cfile-class.md) die Frame-Objekt (wie im Beispiel gezeigt [Öffnen von Dateien](../mfc/opening-files.md)), das Objekt wird automatisch geschlossen und dann zerstört, wenn sie den Gültigkeitsbereich verlässt. Beachten Sie, dass beim Löschen der `CFile` Objekt der physischen Datei im Dateisystem wird nicht gelöscht werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Dateien](../mfc/files-in-mfc.md)

