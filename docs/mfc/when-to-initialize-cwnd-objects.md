---
title: Wann müssen CWnd-Objekte initialisiert werden? | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window objects [MFC], when to initialize CWnd
- initializing CWnd objects [MFC]
- initializing objects [MFC], CWnd
- CWnd objects [MFC], when HWND is attached
- HWND, when attached to CWnd object
- CWnd objects [MFC], when to initialize
ms.assetid: 4d31bcb1-73db-4f2f-b71c-89b087569a10
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ee10a4632809a224028bfa482f80ed9e8a9334a5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="when-to-initialize-cwnd-objects"></a>Wann müssen CWnd-Objekte initialisiert werden?
Erstellen Sie eigene untergeordnete Windows oder rufen Sie alle-API-Windows­API­Funktionen in den Konstruktor der kann keiner `CWnd`-abgeleitetes Objekt. Grund hierfür ist die `HWND` für die `CWnd` Objekt wurde noch nicht erstellt. Die meisten Windows-spezifischen Initialisierung, z. B. das Hinzufügen von untergeordneten Fenster muss erfolgen, eine [OnCreate](../mfc/reference/cwnd-class.md#oncreate) Message-Handler.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Erstellen von Dokument Rahmenfenster](../mfc/creating-document-frame-windows.md)  
  
-   [Erstellen von Dokument/Ansicht](../mfc/document-view-creation.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)

