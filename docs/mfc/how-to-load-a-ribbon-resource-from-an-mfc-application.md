---
title: 'Vorgehensweise: Laden einer Menübandressource aus einer MFC-Anwendung'
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
ms.openlocfilehash: b7691d4168101209b0e2d2500012a2b4a8e47788
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160327"
---
# <a name="how-to-load-a-ribbon-resource-from-an-mfc-application"></a>Vorgehensweise: Laden einer Menübandressource aus einer MFC-Anwendung

Um die menübandressource in Ihrer Anwendung verwenden möchten, ändern Sie die Anwendung die menübandressource laden.

### <a name="to-load-a-ribbon-resource"></a>Beim Laden einer menübandressource

1. Deklarieren Sie die `Ribbon Control` -Objekt in der `CMainFrame` Klasse.

```
    CMFCRibbonBar m_wndRibbonBar;
```

1. In `CMainFrame::OnCreate`, erstellen und Initialisieren des Menüband-Steuerelements.

```
    if (!m_wndRibbonBar.Create (this))
{
    return -1;
}

    if (!m_wndRibbonBar.LoadFromResource(IDR_RIBBON))
{
    return -1;
}
```

## <a name="see-also"></a>Siehe auch

[Menüband-Designer (MFC)](../mfc/ribbon-designer-mfc.md)
