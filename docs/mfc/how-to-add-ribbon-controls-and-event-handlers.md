---
title: 'Vorgehensweise: Hinzufügen von Menübandsteuerelementen und Ereignishandlern | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- event handlers [MFC], adding
- ribbon controls [MFC], adding
ms.assetid: b31f25bc-ede7-49c3-9e3c-dffe4e174a69
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3c4af695553bc97815915454bda2aae481543e9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427952"
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

