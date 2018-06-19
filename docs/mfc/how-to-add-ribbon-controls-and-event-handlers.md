---
title: 'Vorgehensweise: Hinzufügen von Menübandsteuerelementen und Ereignishandlern | Microsoft Docs'
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
ms.openlocfilehash: 176323137b2ace0d27d9de162da7fa022441aa88
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344418"
---
# <a name="how-to-add-ribbon-controls-and-event-handlers"></a>Gewusst wie: Hinzufügen von Menüband-Steuerelementen und Ereignishandlern
Menübandsteuerelemente sind Elemente, z. B. Schaltflächen und Kombinationsfelder, die Bereiche hinzugefügt. Bereiche sind Bereiche der menübandleiste, in denen eine Gruppe von verwandten Steuerelementen angezeigt.  
  
 In diesem Thema die Menüband-Designer zu öffnen, eine Schaltfläche "hinzufügen" und verknüpfen Sie ein Ereignis, das "Hello World" angezeigt.  
  
### <a name="to-open-the-ribbon-designer"></a>Zum Öffnen des Menüband-Designers  
  
1.  In Visual Studio auf die **Ansicht** Menü klicken Sie auf **Ressourcenansicht**.  
  
2.  In **Ressourcenansicht**, doppelklicken Sie auf die menübandressource für die Anzeige auf der Entwurfsoberfläche angezeigt.  
  
### <a name="to-add-a-button-and-an-event-handler"></a>So fügen Sie eine Schaltfläche und ein Ereignishandler hinzu.  
  
1.  Aus der **Symbolleiste**, klicken Sie auf **Schaltfläche** und ziehen Sie es an ein Panel in der Entwurfsoberfläche angezeigt.  
  
2.  Der rechten Maustaste, und klicken Sie auf **Ereignishandler hinzufügen**.  
  
3.  In der **Ereignishandler-Assistent**, bestätigen Sie die Standardeinstellungen, und klicken Sie auf **hinzufügen und Bearbeiten von**. Weitere Informationen finden Sie unter [Ereignishandler-Assistent](../ide/event-handler-wizard.md).  
  
4.  Fügen Sie im Code-Editor den folgenden Code in die Handlerfunktion:  
  
 ```  
    MessageBox((LPCTSTR)L"Hello World");

 ```  
  
## <a name="see-also"></a>Siehe auch  
 [RibbonGadgets-Beispiel: Gadgets Menübandanwendung](../visual-cpp-samples.md)   
 [Menüband-Designer (MFC)](../mfc/ribbon-designer-mfc.md)

