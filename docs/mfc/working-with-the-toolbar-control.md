---
title: Arbeiten mit dem ToolBar-Steuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- GetToolBarCtrl method [MFC]
- toolbars [MFC], accessing common control
- CToolBarCtrl class [MFC], accessing toolbar
- toolbar controls [MFC], accessing
ms.assetid: b19409d5-3831-42c7-80ae-195c49dc9085
ms.openlocfilehash: 60cc527493e2a68751c201b998ab171c564d6c1f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510577"
---
# <a name="working-with-the-toolbar-control"></a>Arbeiten mit dem ToolBar-Steuerelement

In diesem Artikel wird erläutert, wie Sie auf das [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) -Objekt, das einer [CToolBar](../mfc/reference/ctoolbar-class.md) zugrunde liegt, zugreifen können, um Ihre Symbolleisten besser zu steuern Dies ist ein erweitertes Thema.

## <a name="procedures"></a>Verfahren

#### <a name="to-access-the-toolbar-common-control-underlying-your-ctoolbar-object"></a>So greifen Sie auf das allgemeine Steuerelement der Symbolleiste zu

1. Aufrufen von [CToolBar:: GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl).

`GetToolBarCtrl`Gibt einen Verweis auf ein [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) -Objekt zurück. Sie können den Verweis verwenden, um Member-Funktionen der Symbolleisten-Steuerelement Klasse aufzurufen.

> [!CAUTION]
>  Wenn Sie `CToolBarCtrl` "Get Functions" sicher aufrufen, sollten Sie Vorsicht walten **lassen** , wenn Sie die **Set** -Funktionen aufrufen. Dies ist ein erweitertes Thema. Normalerweise müssen Sie nicht auf das zugrunde liegende Symbolleisten-Steuerelement zugreifen.

### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren?

- [Steuerelemente (allgemeine Windows-Steuerelemente)](../mfc/controls-mfc.md)

- [Grundlagen zu Toolbar](../mfc/toolbar-fundamentals.md)

- [Andockbare und Gleit Komma Symbolleisten](../mfc/docking-and-floating-toolbars.md)

- [Dynamisches Ändern der Größe der Symbolleiste](../mfc/docking-and-floating-toolbars.md)

- [Quick Infos für Symbolleisten](../mfc/toolbar-tool-tips.md)

- [Aktualisierungen der Statusleiste "Flyby"](../mfc/toolbar-tool-tips.md)

- [Behandeln von QuickInfo-Benachrichtigungen](../mfc/handling-tool-tip-notifications.md)

- Die Klassen [CToolBar](../mfc/reference/ctoolbar-class.md) und [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)

- [Behandeln von Anpassungs Benachrichtigungen](../mfc/handling-customization-notifications.md)

- [Mehrere Symbolleisten](../mfc/toolbar-fundamentals.md)

- [Verwenden der alten Symbolleisten](../mfc/using-your-old-toolbars.md)

- [Steuer leisten](../mfc/control-bars.md)

Allgemeine Informationen zur Verwendung von allgemeinen Windows-Steuerelementen finden Sie unter Allgemeine Steuer [Elemente](/windows/win32/Controls/common-controls-intro).

## <a name="see-also"></a>Siehe auch

[Implementieren der MFC-Symbolleiste](../mfc/mfc-toolbar-implementation.md)
