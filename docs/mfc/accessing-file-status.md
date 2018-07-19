---
title: Zugreifen auf den Dateistatus | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- files [MFC], status information
- examples [MFC], file status
- files [MFC], accessing
- file status [MFC]
- status of files [MFC]
ms.assetid: 1b8891d6-eb0f-4037-a837-4928fe595222
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d424502e991ea355a6e31bba8fedccb6d5ad2fcf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33334294"
---
# <a name="accessing-file-status"></a>Zugreifen auf den Dateistatus
`CFile` unterstützt Sie auch das erste Dateistatus, z. B. ob die Datei vorhanden ist, Erstellung und Änderung von Datumsangaben und Uhrzeiten, logische Größe und Pfad.  
  
### <a name="to-get-file-status"></a>Dateistatus abrufen  
  
1.  Verwenden der [CFile](../mfc/reference/cfile-class.md) Klasse zum Abrufen und Festlegen von Informationen zu einer Datei. Eine nützliche Anwendung ist die Verwendung der `CFile` statische Memberfunktion **GetStatus** zu bestimmen, ob eine Datei vorhanden ist. **GetStatus** gibt 0 zurück, wenn die angegebene Datei nicht vorhanden ist.  
  
 Daher können Sie das Ergebnis des **GetStatus** bestimmt, ob verwenden die **modeCreate** flag beim Öffnen einer Datei, wie im folgenden Beispiel gezeigt:  
  
 [!code-cpp[NVC_MFCFiles#3](../atl-mfc-shared/reference/codesnippet/cpp/accessing-file-status_1.cpp)]  
  
 Weitere Informationen finden Sie unter [Serialisierung](../mfc/serialization-in-mfc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Dateien](../mfc/files-in-mfc.md)

