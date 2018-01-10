---
title: Zugreifen auf den Dateistatus | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- files [MFC], status information
- examples [MFC], file status
- files [MFC], accessing
- file status [MFC]
- status of files [MFC]
ms.assetid: 1b8891d6-eb0f-4037-a837-4928fe595222
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9ff93028c192a735ec75721d3dfdb9929a35edad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="accessing-file-status"></a>Zugreifen auf den Dateistatus
`CFile`unterstützt Sie auch das erste Dateistatus, z. B. ob die Datei vorhanden ist, Erstellung und Änderung von Datumsangaben und Uhrzeiten, logische Größe und Pfad.  
  
### <a name="to-get-file-status"></a>Dateistatus abrufen  
  
1.  Verwenden der [CFile](../mfc/reference/cfile-class.md) Klasse zum Abrufen und Festlegen von Informationen zu einer Datei. Eine nützliche Anwendung ist die Verwendung der `CFile` statische Memberfunktion **GetStatus** zu bestimmen, ob eine Datei vorhanden ist. **GetStatus** gibt 0 zurück, wenn die angegebene Datei nicht vorhanden ist.  
  
 Daher können Sie das Ergebnis des **GetStatus** bestimmt, ob verwenden die **modeCreate** flag beim Öffnen einer Datei, wie im folgenden Beispiel gezeigt:  
  
 [!code-cpp[NVC_MFCFiles#3](../atl-mfc-shared/reference/codesnippet/cpp/accessing-file-status_1.cpp)]  
  
 Weitere Informationen finden Sie unter [Serialisierung](../mfc/serialization-in-mfc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Dateien](../mfc/files-in-mfc.md)

