---
title: Arbeiten mit dem Toolbar-Steuerelement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- GetToolBarCtrl method [MFC]
- toolbars [MFC], accessing common control
- CToolBarCtrl class [MFC], accessing toolbar
- toolbar controls [MFC], accessing
ms.assetid: b19409d5-3831-42c7-80ae-195c49dc9085
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 32d3cc6244bc2f928c8d1d0c6e46d1bc5a57aa3b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385936"
---
# <a name="working-with-the-toolbar-control"></a>Arbeiten mit dem ToolBar-Steuerelement
In diesem Artikel wird erläutert, wie Sie zugreifen können die [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) Objekt zugrunde liegenden eine [CToolBar](../mfc/reference/ctoolbar-class.md) für größere Kontrolle über Ihre Symbolleisten. Dies ist ein-Thema für fortgeschrittene.  
  
## <a name="procedures"></a>Verfahren  
  
#### <a name="to-access-the-toolbar-common-control-underlying-your-ctoolbar-object"></a>Auf die zugrunde liegenden Objekts CToolBar allgemeine Symbolleisten-Steuerelement  
  
1.  Rufen Sie [GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl).  
  
 `GetToolBarCtrl` Gibt einen Verweis auf eine [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) Objekt. Sie können den Verweis zum Aufrufen von Memberfunktionen der Steuerelementklasse Symbolleiste verwenden.  
  
> [!CAUTION]
>  Beim Aufrufen `CToolBarCtrl` **abrufen** Funktionen sicher ist, seien Sie beim Aufrufen der **festgelegt** Funktionen. Dies ist ein-Thema für fortgeschrittene. Normalerweise müssen Sie darf nicht das zugrunde liegende Symbolleisten-Steuerelement zugreifen.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Steuerelemente (Allgemeine Windows-Steuerelemente)](../mfc/controls-mfc.md)  
  
-   [Grundlagen zu Symbolleisten](../mfc/toolbar-fundamentals.md)  
  
-   [Andockbare und unverankerte Symbolleisten](../mfc/docking-and-floating-toolbars.md)  
  
-   [Dynamisches Ändern der Größe der Symbolleiste](../mfc/docking-and-floating-toolbars.md)  
  
-   [QuickInfo in Symbolleisten](../mfc/toolbar-tool-tips.md)  
  
-   [Statusleistenupdates](../mfc/toolbar-tool-tips.md)  
  
-   [Behandeln von QuickInfo-Benachrichtigungen](../mfc/handling-tool-tip-notifications.md)  
  
-   Die [CToolBar](../mfc/reference/ctoolbar-class.md) und [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) Klassen  
  
-   [Behandeln von anpassungsbenachrichtigungen](../mfc/handling-customization-notifications.md)  
  
-   [Mehrere Symbolleisten](../mfc/toolbar-fundamentals.md)  
  
-   [Verwenden der bisherigen Symbolleisten](../mfc/using-your-old-toolbars.md)  
  
-   [Steuerleisten](../mfc/control-bars.md)  
  
 Allgemeine Informationen zu allgemeinen Windows-Steuerelemente verwenden, finden Sie unter [Standardsteuerelementen](http://msdn.microsoft.com/library/windows/desktop/bb775493).  
  
## <a name="see-also"></a>Siehe auch  
 [Implementieren der MFC-Symbolleiste](../mfc/mfc-toolbar-implementation.md)

