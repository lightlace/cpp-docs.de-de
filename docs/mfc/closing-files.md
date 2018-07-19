---
title: Schließen von Dateien | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 97bd910ae4cb514cda07dd319f37a05a32712909
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341025"
---
# <a name="closing-files"></a>Schließen von Dateien
Wie gewohnt in e/a-Vorgängen, müssen wenn Sie fertig, mit einer Datei sind, Sie es schließen.  
  
#### <a name="to-close-a-file"></a>Um eine Datei zu schließen.  
  
1.  Verwenden der **schließen** Memberfunktion. Diese Funktion schließt die Dateisystem Datei und leert Puffer bei Bedarf.  
  
 Wenn Sie zugeordnet der [CFile](../mfc/reference/cfile-class.md) die Frame-Objekt (wie im Beispiel gezeigt [Öffnen von Dateien](../mfc/opening-files.md)), das Objekt wird automatisch geschlossen und dann zerstört, wenn sie den Gültigkeitsbereich verlässt. Beachten Sie, dass beim Löschen der `CFile` Objekt der physischen Datei im Dateisystem wird nicht gelöscht werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Dateien](../mfc/files-in-mfc.md)

