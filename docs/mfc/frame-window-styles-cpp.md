---
title: Rahmenfensterstile (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window styles [MFC]
- PreCreateWindow method, setting window styles
- windows [MFC], MFC
- frame windows [MFC], styles
- MFC, frame windows
- styles [MFC], windows
ms.assetid: fc5058c1-eec8-48d8-9f76-3fc01cfa53f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 102b3a4c8372a53aada23ad448ce5dc1cf323a97
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="frame-window-styles-c"></a>Rahmenfensterstile (C++)
Das Rahmenfenster, Sie mit dem Framework erhalten, eignen sich für die meisten Programme erhalten Sie zusätzliche Flexibilität, mit den erweiterten Funktionen jedoch [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) und der globalen MFC-Funktion [AfxRegisterWndClass ](../mfc/reference/application-information-and-management.md#afxregisterwndclass). `PreCreateWindow` ist eine Memberfunktion der `CWnd`.  
  
 Wenden Sie die **WS_HSCROLL** und **WS_VSCROLL** Stile an das Hauptrahmenfenster, werden sie stattdessen angewendet die **MDICLIENT** -Fenster, sodass Benutzer die gescrolltwerdenkönnen**MDICLIENT** Bereich.  
  
 Wenn des Fensters **FWS_ADDTOTITLE** Formatbit (die sie in der Standardeinstellung) festgelegt ist, wird die Sicht weist dem Rahmenfenster Titel, der in der Titelleiste des Fensters, die basierend auf den Namen der Sicht Dokument anzuzeigen.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Verwalten von untergeordneten MDI-Fenster (MDICLIENT)](../mfc/managing-mdi-child-windows.md), das Fenster innerhalb einer MDI-Frame, untergeordnete MDI-Fenster enthält,  
  
-   [Ändern der Stile eines mit MFC erstellten Fensters](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
-   [Fensterstile](../mfc/reference/styles-used-by-mfc.md#window-styles)  
  
## <a name="see-also"></a>Siehe auch  
 [Rahmenfenster](../mfc/frame-windows.md)

