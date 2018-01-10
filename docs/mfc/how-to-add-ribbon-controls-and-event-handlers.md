---
title: "Vorgehensweise: Hinzufügen von Menübandsteuerelementen und Ereignishandlern | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- event handlers [MFC], adding
- ribbon controls [MFC], adding
ms.assetid: b31f25bc-ede7-49c3-9e3c-dffe4e174a69
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f5d5015fdf5fd2a97b6b8a9b9ee9cf5ccc755ce5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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

