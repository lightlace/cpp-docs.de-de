---
title: Testen der Eigenschaften und Ereignisse mit Testcontainer | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- testing, test containers
- tstcon32.exe
- debugging ActiveX controls
- test container
- ActiveX Control Test Container
- ActiveX controls [MFC], testing
- properties [MFC], testing
ms.assetid: 626867cf-fe53-4c30-8973-55bb93ef3917
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 381f4e421b63b2ba48fe649a30e5bf7648b50d27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="testing-properties-and-events-with-test-container"></a>Testen der Eigenschaften und Ereignisse mit Test Container
Die Testcontainer-Anwendung, die im Lieferumfang von Visual C++ ist ein ActiveX-Steuerelementcontainer zum Testen und Debuggen von ActiveX-Steuerelemente. Testcontainer kann Entwickler von Steuerelementen So testen Sie die Funktionalität des Steuerelements durch Ändern der Eigenschaften, Methoden aufruft und seine Ereignisse auslöst. Testcontainer können die Protokolle der Datenbindung Benachrichtigungen angezeigt und auch bietet Funktionen zum Testen der Funktionalität für ein ActiveX-Steuerelement Persistenz: können Sie Eigenschaften in einen Stream oder Substorage speichern, laden Sie sie erneut, und überprüfen Sie die gespeicherten Daten. Dieser Abschnitt beschreibt, wie die grundlegenden Funktionen des Testcontainers. Wählen Sie zusätzliche Informationen, die **Hilfe** Menü während der Ausführung der Testcontainer.  
  
### <a name="to-access-the-activex-control-test-container"></a>Auf den Testcontainer für ActiveX-Steuerelemente  
  
1.  Erstellen der [TSTCON-Beispiel: Testcontainer für ActiveX-Steuerelement](../visual-cpp-samples.md).  
  
### <a name="to-test-your-activex-control"></a>So testen Sie das ActiveX-Steuerelement  
  
1.  Auf der **bearbeiten** klicken Sie im Menü des Testcontainers auf **neues Steuerelement einfügen**.  
  
2.  In der **Steuerelement einfügen** Feld, wählen Sie das gewünschte Steuerelement aus, und klicken Sie auf **OK**. Das Steuerelement wird in dem Steuerelementcontainer angezeigt.  
  
    > [!NOTE]
    >  Wenn das Steuerelement nicht, in aufgeführt ist der **Steuerelement einfügen** Dialogfeld stellen Sie sicher, dass Sie ihn mit registriert haben die **Steuerelemente registrieren** Befehl die **Datei** Menü des Tests Container.  
  
 An diesem Punkt können Sie Eigenschaften oder Ereignisse des Steuerelements testen.  
  
#### <a name="to-test-properties"></a>So testen Sie die Eigenschaften  
  
1.  Auf der **Steuerelement** Menü klicken Sie auf **Methoden aufrufen**.  
  
2.  In der **Methodennamen** Dropdown-Liste, wählen Sie die PropPut-Methode für die Eigenschaft, die Sie testen möchten.  
  
3.  Ändern der **Parameterwert** oder **Parametertyp** , und klicken Sie auf die **Wert festlegen** Schaltfläche.  
  
4.  Klicken Sie auf **Invoke** auf den neuen Wert für das Objekt gelten.  
  
     Die Eigenschaft enthält jetzt den neuen Wert.  
  
#### <a name="to-test-events-and-specify-the-destination-of-event-information"></a>Um Ereignisse zu testen, und geben Sie das Ziel der Ereignisinformationen.  
  
1.  Auf der **Optionen** Menü klicken Sie auf **Protokollierung**.  
  
2.  Geben Sie das Ziel der Ereignisinformationen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [Gewusst wie: Debuggen von ActiveX-Steuerelementen](/visualstudio/debugger/how-to-debug-an-activex-control)

