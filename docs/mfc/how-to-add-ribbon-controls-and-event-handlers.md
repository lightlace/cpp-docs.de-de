---
title: 'Vorgehensweise: Hinzufügen von Menübandsteuerelementen und Ereignishandlern'
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [MFC], adding
- ribbon controls [MFC], adding
ms.assetid: b31f25bc-ede7-49c3-9e3c-dffe4e174a69
ms.openlocfilehash: c21e8b86962ebf37ca1a06bae056d09b9a9dbb2f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389514"
---
# <a name="how-to-add-ribbon-controls-and-event-handlers"></a>Vorgehensweise: Hinzufügen von Menübandsteuerelementen und Ereignishandlern

Menübandsteuerelemente sind Elemente, z. B. Schaltflächen und Kombinationsfelder, die Panels hinzugefügt. Bereiche werden Bereiche der menübandleiste, die eine Gruppe von verwandten Steuerelementen angezeigt werden.

In diesem Thema werden Sie der Menüband-Designer zu öffnen, eine Schaltfläche "hinzufügen" und verknüpfen Sie dann ein Ereignis, das "Hello World" angezeigt.

### <a name="to-open-the-ribbon-designer"></a>Um dem Menüband-Designer zu öffnen.

1. In Visual Studio auf die **Ansicht** Menü klicken Sie auf **Ressourcenansicht**.

1. In **Ressourcenansicht**, doppelklicken Sie auf die menübandressource, um sie auf der Entwurfsoberfläche anzuzeigen.

### <a name="to-add-a-button-and-an-event-handler"></a>Eine Schaltfläche und einen Ereignishandler hinzufügen

1. Von der **Symbolleiste**, klicken Sie auf **Schaltfläche** und ziehen Sie sie in einen Bereich in der Entwurfsoberfläche.

1. Der rechten Maustaste, und klicken Sie auf **Ereignishandler hinzufügen**.

1. In der **Ereignishandler-Assistent**, bestätigen Sie die Standardeinstellungen, und klicken Sie auf **hinzufügen und Bearbeiten von**. Weitere Informationen finden Sie unter [Ereignishandler-Assistent](../ide/event-handler-wizard.md).

1. Fügen Sie im Code-Editor den folgenden Code in die Handler-Funktion:

```
    MessageBox((LPCTSTR)L"Hello World");
```

## <a name="see-also"></a>Siehe auch

[RibbonGadgets-Beispiel: Gadgets Menübandanwendung](../overview/visual-cpp-samples.md)<br/>
[Menüband-Designer (MFC)](../mfc/ribbon-designer-mfc.md)
