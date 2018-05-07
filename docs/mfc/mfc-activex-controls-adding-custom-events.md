---
title: 'MFC-ActiveX-Steuerelemente: Hinzufügen von benutzerdefinierten Ereignissen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], events [MFC]
- EVENT_CUSTOM prefix [MFC]
- custom events [MFC], adding to ActiveX controls
- EVENT_CUSTOM macro [MFC]
- InCircle method [MFC]
- ClickIn event
- FireClickIn event
- COleControl class [MFC], custom events [MFC]
- Click event, custom events [MFC]
- events [MFC], ActiveX controls
- custom events [MFC]
- FireEvent method, adding custom events
ms.assetid: c584d053-1e34-47aa-958e-37d3e9b85892
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b82232b8f2ad7a5e3bc1ff8fed0e8a38b1a7d66
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-activex-controls-adding-custom-events"></a>MFC-ActiveX-Steuerelemente: Hinzufügen von benutzerdefinierten Ereignissen
Benutzerdefinierte Ereignisse unterscheiden sich von vordefinierten Ereignissen, da sie nicht automatisch von-Klasse ausgelöst wurden `COleControl`. Ein benutzerdefiniertes Ereignis erkennt eine bestimmte Aktion vom Entwickler Steuerelements als Ereignis bestimmt. Der Ereignis-Zuordnungseinträge für benutzerdefinierte Ereignisse werden durch dargestellt die `EVENT_CUSTOM` Makro. Im folgende Abschnitt implementiert ein benutzerdefiniertes Ereignis für ein ActiveX-Steuerelement-Projekt, das mit dem ActiveX-Steuerelement-Assistenten erstellt wurde.  
  
##  <a name="_core_adding_a_custom_event_with_classwizard"></a> Hinzufügen eines benutzerdefinierten Ereignisses mit der Ereignis-Assistent zum Hinzufügen von  
 Das folgende Verfahren wird ein bestimmtes benutzerdefiniertes Ereignis ClickIn hinzugefügt. Sie können dieses Verfahren verwenden, andere benutzerdefinierte Ereignisse hinzufügen. Ersetzen Sie den Ereignisnamen Ihres benutzerdefinierten und seine Parameter für die ClickIn Ereignisnamen und Parameter an.  
  
#### <a name="to-add-the-clickin-custom-event-using-the-add-event-wizard"></a>So fügen Sie das benutzerdefinierte ClickIn-Ereignis mithilfe des Assistenten zum Hinzufügen von Ereignis hinzu  
  
1.  Laden Sie das Steuerelementprojekt.  
  
2.  In der Klassenansicht mit der rechten Maustaste der ActiveX-Steuerelementklasse, um das Kontextmenü zu öffnen.  
  
3.  Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Add Event**.  
  
     Dies öffnet den Assistenten zum Hinzufügen eines Ereignisses.  
  
4.  In der **Ereignisname** Feld Sie zunächst alle vorhandenes Ereignis auswählen, und klicken Sie auf die **benutzerdefinierte** Radio Schaltfläche aus, und geben Sie dann `ClickIn`.  
  
5.  In der **internen Namen** geben den Namen der Funktion für das Ereignis ausgelöst. In diesem Beispiel verwenden Sie den Standardwert, der durch den Assistenten zum Hinzufügen von Ereignis bereitgestellt (`FireClickIn`).  
  
6.  Fügen Sie einen Parameter namens `xCoord` (Typ `OLE_XPOS_PIXELS`) unter Verwendung der **Parametername** und **Parametertyp** Steuerelemente.  
  
7.  Fügen Sie einen zweiten Parameter namens `yCoord` (Typ `OLE_YPOS_PIXELS`).  
  
8.  Klicken Sie auf **Fertig stellen** das Ereignis erstellt.  
  
##  <a name="_core_classwizard_changes_for_custom_events"></a> Änderungen der Ereignis-Assistenten für benutzerdefinierte Ereignisse hinzufügen  
 Wenn Sie ein benutzerdefiniertes Ereignis hinzufügen, werden mit dem Assistenten zum Hinzufügen von Ereignis Änderungen an der Control-Klasse. H. CPP und. IDL-Dateien. Die folgenden Codebeispiele sind speziell für die ClickIn-Ereignis.  
  
 Die folgenden Zeilen, die dem Header hinzugefügt werden (. H)-Datei der Steuerelementklasse:  
  
 [!code-cpp[NVC_MFC_AxUI#7](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_1.h)]  
  
 Dieser Code deklariert eine Inlinefunktion aufgerufen `FireClickIn` damaligen [COleControl::](../mfc/reference/colecontrol-class.md#fireevent) mit dem ClickIn-Ereignis und die Parameter Sie mithilfe des Assistenten zum Hinzufügen von Ereignis definiert.  
  
 Darüber hinaus wird die folgende Zeile auf der ereigniszuordnung für das Steuerelement, in der Implementierung hinzugefügt (. Der Steuerelementklasse CPP)-Datei:  
  
 [!code-cpp[NVC_MFC_AxUI#8](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_2.cpp)]  
  
 Dieser Code ordnet das ClickIn Inlinefunktion `FireClickIn`, die Sie mithilfe des Assistenten zum Hinzufügen von Ereignis definierten Parametern übergeben.  
  
 Schließlich wird die folgende Zeile des Steuerelements hinzugefügt. IDL-Datei:  
  
 [!code-cpp[NVC_MFC_AxUI#9](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_3.idl)]  
  
 Diese Zeile weist dem ClickIn-Ereignis eine bestimmte ID-Nummer der Position des Ereignisses in der Ereignisliste des Assistenten zum Hinzufügen von Ereignis entnommen. Der Eintrag in der Ereignisliste kann Container für das Ereignis zu erwarten. Es kann z. B. Handlercode ausgeführt werden, wenn das Ereignis ausgelöst wird bereitstellen.  
  
##  <a name="_core_calling_fireclickin"></a> FireClickIn aufrufen  
 Nun, dass Sie das benutzerdefinierte ClickIn-Ereignis mithilfe des Assistenten zum Hinzufügen von Ereignis hinzugefügt haben, müssen Sie entscheiden, wenn dieses Ereignis wird ausgelöst werden. Dazu rufen `FireClickIn` Wenn die entsprechende Aktion ausgeführt wird. Bei dieser Erläuterung verwendet das Steuerelement die `InCircle` Funktion innerhalb einer `WM_LBUTTONDOWN` Message-Handler für das Auslösen der ClickIn-Ereignis, wenn ein Benutzer in einer kreisförmigen oder elliptischen Bereich klickt. Die folgende Prozedur fügt der `WM_LBUTTONDOWN` Handler.  
  
#### <a name="to-add-a-message-handler-with-the-add-event-wizard"></a>Message-Handler mit den Assistenten zum Hinzufügen von Ereignis hinzugefügt werden.  
  
1.  Laden Sie das Steuerelementprojekt.  
  
2.  Wählen Sie in der Klassenansicht die ActiveX-Steuerelement-Klasse.  
  
3.  Klicken Sie im Eigenschaftenfenster auf die **Nachrichten** Schaltfläche.  
  
     Das Eigenschaftenfenster zeigt eine Liste der Nachrichten, die von der ActiveX-Steuerelement behandelt werden können. Jede Nachricht, die bereits in fetter Schrift hat eine Handlerfunktion zugewiesen.  
  
4.  Wählen Sie im Fenster Eigenschaften die Nachricht, die Sie behandeln möchten. Wählen Sie für dieses Beispiel `WM_LBUTTONDOWN`.  
  
5.  Wählen Sie aus dem Dropdown-Listenfeld auf der rechten Seite  **\<hinzufügen > OnLButtonDown**.  
  
6.  Doppelklicken Sie auf die neue Handlerfunktion in der Klassenansicht springen zu Code in der Implementierung des Nachricht (. CPP)-Datei des ActiveX-Steuerelements.  
  
 Der folgende code Beispiel ruft die **InCircle** Funktion jedes Mal, wenn die linke Maustaste in das Fenster des Steuerelements geklickt wird. In diesem Beispiel finden Sie in der `WM_LBUTTONDOWN` Handlerfunktion, `OnLButtonDown`in der [für CIRC](../visual-cpp-samples.md) abstrakte.  
  
 [!code-cpp[NVC_MFC_AxUI#10](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_4.cpp)]  
  
> [!NOTE]
>  Wenn der Assistent zum Hinzufügen von Ereignis Meldungshandler für Schaltfläche Mausaktionen erstellt, ist ein Aufruf an den gleichen Meldungshandler der Basisklasse automatisch hinzugefügt. Entfernen Sie diesen Aufruf nicht. Wenn das Steuerelement eine der vordefinierten Maus Nachrichten verwendet wird, müssen die Message-Handler in der Basisklasse aufgerufen werden, um sicherzustellen, dass die mausaufzeichnung ordnungsgemäß verarbeitet wird.  
  
 Im folgenden Beispiel wird das Ereignis ausgelöst, nur bei der auf in einer kreisförmigen oder elliptischen Bereich innerhalb des Steuerelements ausgelöst. Um dieses Verhalten zu erreichen, setzen Sie die `InCircle` -Funktion in der Implementierung des Steuerelements (. CPP)-Datei:  
  
 [!code-cpp[NVC_MFC_AxUI#11](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_5.cpp)]  
  
 Sie müssen auch die folgende Deklaration hinzufügen der `InCircle` Funktion, um die Control-Header (. H)-Datei:  
  
 [!code-cpp[NVC_MFC_AxUI#12](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_6.h)]  
  
##  <a name="_core_custom_events_with_stock_names"></a> Benutzerdefinierte Ereignisse mit vordefinierten Namen  
 Sie können benutzerdefinierte Ereignisse mit dem gleichen Namen wie die vordefinierten Ereignissen erstellen, jedoch beide im gleichen Steuerelement nicht implementieren kann. Sie möchten z. B. erstellen ein benutzerdefiniertes Ereignisses aufgerufen, klicken Sie auf, die nicht ausgelöst wird, wenn die vordefinierten Ereignisses auf normalerweise auslösen würde. Sie konnte das Click-Ereignis dann zu einem beliebigen Zeitpunkt auslösen, durch Aufrufen der Funktion ausgelöst.  
  
 Das folgende Verfahren fügt eine benutzerdefinierte auf Ereignis.  
  
#### <a name="to-add-a-custom-event-that-uses-a-stock-event-name"></a>Ein benutzerdefiniertes Ereignis hinzufügen verwendet, eine vordefinierte Ereignisname  
  
1.  Laden Sie das Steuerelementprojekt.  
  
2.  In der Klassenansicht mit der rechten Maustaste der ActiveX-Steuerelementklasse, um das Kontextmenü zu öffnen.  
  
3.  Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Add Event**.  
  
     Dies öffnet den Assistenten zum Hinzufügen eines Ereignisses.  
  
4.  In der **Ereignisname** Dropdown-Liste, wählen Sie einen vordefinierten Ereignisnamen. Wählen Sie für dieses Beispiel **klicken Sie auf**.  
  
5.  Für **Ereignistyp**Option **benutzerdefinierte**.  
  
6.  Klicken Sie auf **Fertig stellen** das Ereignis erstellt.  
  
7.  Rufen Sie `FireClick` an den entsprechenden Stellen im Code.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [MFC-ActiveX-Steuerelemente: Methoden](../mfc/mfc-activex-controls-methods.md)   
 [COleControl-Klasse](../mfc/reference/colecontrol-class.md)
