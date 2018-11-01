---
title: 'Gewusst wie: Laden einer Menübandressource aus einer MFC-Anwendung'
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
ms.openlocfilehash: 14ba37952d6f8849c51b36901a6bc17404f938e2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515153"
---
# <a name="how-to-load-a-ribbon-resource-from-an-mfc-application"></a>Gewusst wie: Laden einer Menübandressource aus einer MFC-Anwendung

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

