---
title: Arbeiten mit dem ToolBar-Steuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- GetToolBarCtrl method [MFC]
- toolbars [MFC], accessing common control
- CToolBarCtrl class [MFC], accessing toolbar
- toolbar controls [MFC], accessing
ms.assetid: b19409d5-3831-42c7-80ae-195c49dc9085
ms.openlocfilehash: 88c00bf60f2ce1fccecd757d13b2f814e3a18be4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399498"
---
# <a name="working-with-the-toolbar-control"></a>Arbeiten mit dem ToolBar-Steuerelement

In diesem Artikel wird erläutert, wie Sie zugreifen können die [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) Objekt zugrunde liegenden eine [CToolBar](../mfc/reference/ctoolbar-class.md) um mehr Kontrolle über der Symbolleisten. Dies ist ein Thema für fortgeschrittene.

## <a name="procedures"></a>Verfahren

#### <a name="to-access-the-toolbar-common-control-underlying-your-ctoolbar-object"></a>Auf der zugrunde liegenden Objekts CToolBar allgemeine Symbolleisten-Steuerelement

1. Rufen Sie [GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl).

`GetToolBarCtrl` Gibt einen Verweis auf eine [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) Objekt. Sie können den Verweis verwenden, zum Aufrufen von Memberfunktionen der Symbolleisten-Steuerelement-Klasse.

> [!CAUTION]
>  Beim Aufrufen `CToolBarCtrl` **erhalten** Funktionen sicher ist, rufen Sie mit Bedacht vor der **festgelegt** Funktionen. Dies ist ein Thema für fortgeschrittene. Normalerweise müssen Sie sollte nicht das zugrunde liegende Symbolleisten-Steuerelement zugreifen.

### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Steuerelemente (Windows-Standardsteuerelemente)](../mfc/controls-mfc.md)

- [Grundlegendes über Symbolleisten](../mfc/toolbar-fundamentals.md)

- [Andockbare und unverankerte Symbolleisten](../mfc/docking-and-floating-toolbars.md)

- [Dynamisches Ändern der Größe der Symbolleiste](../mfc/docking-and-floating-toolbars.md)

- [QuickInfo in Symbolleisten](../mfc/toolbar-tool-tips.md)

- [Statusleistenupdates](../mfc/toolbar-tool-tips.md)

- [Behandeln von QuickInfo-Benachrichtigungen](../mfc/handling-tool-tip-notifications.md)

- Die [CToolBar](../mfc/reference/ctoolbar-class.md) und [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) Klassen

- [Behandeln von anpassungsbenachrichtigungen](../mfc/handling-customization-notifications.md)

- [Mehrere Symbolleisten](../mfc/toolbar-fundamentals.md)

- [Verwenden der bisherigen Symbolleisten](../mfc/using-your-old-toolbars.md)

- [Steuerleisten](../mfc/control-bars.md)

Allgemeine Informationen zur Verwendung von Windows-Standardsteuerelemente, finden Sie unter [Standardsteuerelementen](/windows/desktop/Controls/common-controls-intro).

## <a name="see-also"></a>Siehe auch

[Implementieren der MFC-Symbolleiste](../mfc/mfc-toolbar-implementation.md)
