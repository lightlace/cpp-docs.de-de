---
title: 'Gewusst wie: Hinzufügen von Menüband-Steuerelementen und Ereignishandlern'
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [MFC], adding
- ribbon controls [MFC], adding
ms.assetid: b31f25bc-ede7-49c3-9e3c-dffe4e174a69
ms.openlocfilehash: 356358e5fd5ac4f3f7511f178ca304e9ab7eff86
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518397"
---
# <a name="how-to-add-ribbon-controls-and-event-handlers"></a>Gewusst wie: Hinzufügen von Menüband-Steuerelementen und Ereignishandlern

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

[RibbonGadgets-Beispiel: Gadgets Menübandanwendung](../visual-cpp-samples.md)<br/>
[Menüband-Designer (MFC)](../mfc/ribbon-designer-mfc.md)

