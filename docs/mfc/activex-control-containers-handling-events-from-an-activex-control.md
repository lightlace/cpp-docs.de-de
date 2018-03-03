---
title: 'ActiveX-Steuerelementcontainer: Behandeln von Ereignissen eines ActiveX-Steuerelements | Microsoft Docs'
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
- event handlers [MFC], ActiveX controls
- ActiveX control containers [MFC], event sinks
- event handling [MFC], ActiveX controls
- ON_EVENT macro [MFC]
- ActiveX controls [MFC], events [MFC]
- END_EVENTSINK_MAP macro, using
- events [MFC], ActiveX controls
- BEGIN_EVENTSINK_MAP macro
ms.assetid: f9c106db-052f-4e32-82ad-750646aa760b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 84e1571f400297584e12a40dfd2bfcc3c0b525d2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="activex-control-containers-handling-events-from-an-activex-control"></a>ActiveX-Steuerelementcontainer: Behandeln von Ereignissen eines ActiveX-Steuerelements
In diesem Artikel wird erläutert, mithilfe des Eigenschaftenfensters Ereignishandlern für ActiveX-Steuerelemente in einem ActiveX-Steuerelementcontainer installieren. Die Ereignishandler dienen zum Empfang von Benachrichtigungen (aus dem Steuerelement) über bestimmte Ereignisse und Ausführen einer Aktion als Antwort. Diese Benachrichtigung wird das Ereignis "Auslösen" aufgerufen.  
  
> [!NOTE]
>  In diesem Artikel verwendet eine Dialogfeldern basierende ActiveX-Steuerelementcontainer-Projekt mit dem Namen Container und ein eingebettetes Steuerelement mit dem Namen Circ als Beispiele in den Prozeduren und den Code.  
  
 Verwenden die Schaltfläche "Ereignisse" im Eigenschaftenfenster angezeigt, können Sie eine Übersicht der Ereignisse, die auftreten können erstellen, in der ActiveX-Steuerelementcontainer-Anwendung. Dieser Zuordnung wird aufgerufen, eine "Senke ereigniszuordnung," wird erstellt und von Visual C++ verwaltet werden, wenn Sie Ereignishandler der Control-Container-Klasse hinzufügen. Jeder Ereignishandler mit einem Ereigniszuordnungseintrag implementiert wird ein bestimmtes Ereignis ein Ereignishandler-containermemberfunktion zugeordnet. Diese Ereignishandlerfunktion wird aufgerufen, wenn das angegebene Ereignis durch das ActiveX-Steuerelementobjekt ausgelöst wird.  
  
 Weitere Informationen zu ereignissenkenzuordnungen, finden Sie unter [Ereigniszuordnungen Senke](../mfc/reference/event-sink-maps.md) in der *Klassenbibliotheksreferenz*.  
  
##  <a name="_core_event_handler_modifications_to_the_project"></a>Ereignis-Handler Änderungen am Projekt  
 Wenn Sie das Eigenschaftenfenster verwenden, um Ereignishandler hinzuzufügen, wird eine Senke ereigniszuordnung deklariert und in Ihrem Projekt definiert. Die folgenden Anweisungen werden an das Steuerelement hinzugefügt. Ein Ereignishandler hinzugefügt wird zum ersten Mal CPP-Datei. Dieser Code deklariert eine Ereignis Sink-Zuordnung für die Dialogfeldklasse (in diesem Fall `CContainerDlg`):  
  
 [!code-cpp[NVC_MFC_AxCont#8](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_1.cpp)]  
[!code-cpp[NVC_MFC_AxCont#9](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_2.cpp)]  
  
 Wie Sie das Eigenschaftenfenster verwenden, um Ereignisse hinzuzufügen, zuordnen ein Ereignisses Eintrag (`ON_EVENT`) hinzugefügt wird, die Senke ereigniszuordnung und ein Ereignishandler Funktion des Containers Implementierung hinzugefügt (. CPP)-Datei.  
  
 Das folgende Beispiel deklariert einen Ereignishandler namens `OnClickInCircCtrl`, für des Circ Steuerelements **ClickIn** Ereignis:  
  
 [!code-cpp[NVC_MFC_AxCont#10](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_3.cpp)]  
  
 Darüber hinaus wird die folgende Vorlage hinzugefügt, um die `CContainerDlg` klassenimplementierung (. CPP)-Datei für die Ereignishandler-Memberfunktion:  
  
 [!code-cpp[NVC_MFC_AxCont#11](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_4.cpp)]  
  
 Weitere Informationen zu Ereignissenke Makros finden Sie unter [Ereignissenkenzuordnungen](../mfc/reference/event-sink-maps.md) in der *Klassenbibliotheksreferenz*.  
  
#### <a name="to-create-an-event-handler-function"></a>So erstellen eine Ereignishandlerfunktion  
  
1.  Wählen Sie in der Klassenansicht die Dialogfeldklasse, die das ActiveX-Steuerelement enthält. In diesem Beispiel verwenden `CContainerDlg`.  
  
2.  Klicken Sie im Eigenschaftenfenster auf die **Ereignisse** Schaltfläche.  
  
3.  Wählen Sie im Fenster Eigenschaften die Steuerelement-ID des eingebetteten ActiveX-Steuerelements. In diesem Beispiel verwenden `IDC_CIRCCTRL1`.  
  
     Das Eigenschaftenfenster zeigt eine Liste der Ereignisse, die vom eingebetteten ActiveX-Steuerelement ausgelöst werden können. Eine Memberfunktion leiten, die bereits in fetter Schrift hat Handlerfunktionen zugewiesen.  
  
4.  Wählen Sie das Ereignis, das die Dialogfeldklasse behandelt werden soll. Wählen Sie für dieses Beispiel **klicken Sie auf**.  
  
5.  Wählen Sie aus dem Dropdown-Listenfeld auf der rechten Seite  **\<hinzufügen > ClickCircctrl1 aus**.  
  
6.  Doppelklicken Sie auf die neue Handlerfunktion springen zu der Ereignishandlercode in der Implementierung der Klassenansicht (. CPP)-Datei des `CContainerDlg`.  
  
## <a name="see-also"></a>Siehe auch  
 [ActiveX-Steuerelementcontainer](../mfc/activex-control-containers.md)

