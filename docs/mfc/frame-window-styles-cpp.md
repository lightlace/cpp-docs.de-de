---
title: Rahmenfensterstile (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- window styles [MFC]
- PreCreateWindow method, setting window styles
- windows [MFC], MFC
- frame windows [MFC], styles
- MFC, frame windows
- styles [MFC], windows
ms.assetid: fc5058c1-eec8-48d8-9f76-3fc01cfa53f7
ms.openlocfilehash: cade8e7e50779437feb73a94058dc62118c03c10
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57274647"
---
# <a name="frame-window-styles-c"></a>Rahmenfensterstile (C++)

Das Rahmenfenster, Sie mit dem Framework erhalten, eignen sich für die meisten Programme, aber Sie können zusätzliche Flexibilität erzielen, indem Sie mithilfe der erweiterten Funktionen [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) und der globalen MFC-Funktion [AfxRegisterWndClass ](../mfc/reference/application-information-and-management.md#afxregisterwndclass). `PreCreateWindow` ist eine Memberfunktion der `CWnd`.

Wenn Sie anwenden, die **WS_HSCROLL** und **WS_VSCROLL** an das Hauptrahmenfenster, sie stattdessen auf angewendet werden die **MDICLIENT** -Fenster, sodass Benutzer, die scrollenkönnen**MDICLIENT** Bereich.

Wenn des Fensters des **FWS_ADDTOTITLE** Formatbit (die sie in der Standardeinstellung) festgelegt ist, wird die Sicht weist dem Rahmenfenster Titel, der in der Titelleiste des Fensters die, die basierend auf den Namen der Ansicht Dokument anzuzeigen.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Verwalten von untergeordneten MDI-Fenster (MDICLIENT)](../mfc/managing-mdi-child-windows.md), das Fenster in einer MDI-Frame, die die untergeordneten MDI-Fenster enthält.

- [Ändern der Stile eines mit MFC erstellten Fensters](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)

- [Window-Stile](../mfc/reference/styles-used-by-mfc.md#window-styles)

## <a name="see-also"></a>Siehe auch

[Rahmenfenster](../mfc/frame-windows.md)
