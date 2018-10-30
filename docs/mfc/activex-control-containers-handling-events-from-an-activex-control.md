---
title: 'ActiveX-Steuerelementcontainer: Behandeln von Ereignissen eines ActiveX-Steuerelements | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2b7e01fec89ffa625f785cc72aff4d94a9c1b489
ms.sourcegitcommit: a3c9e7888b8f437a170327c4c175733ad9eb0454
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "50204378"
---
# <a name="activex-control-containers-handling-events-from-an-activex-control"></a>ActiveX-Steuerelementcontainer: Behandeln von Ereignissen eines ActiveX-Steuerelements

In diesem Artikel wird erläutert, mithilfe des Eigenschaftenfensters-Ereignishandlern für ActiveX-Steuerelemente in einem ActiveX-Steuerelementcontainer zu installieren. Die Ereignishandler dienen zum Empfang von Benachrichtigungen (aus dem Steuerelement), der bestimmte Ereignisse, und führen Sie eine Aktion als Antwort. Diese Benachrichtigung wird "Auslösen" des Ereignisses aufgerufen.

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen zu moderne Technologien, die ActiveX-ablösen, finden Sie unter [ActiveX-Steuerelemente](activex-controls.md).

> [!NOTE]
>  Diesem Artikel wird ein Dialogfeld-basierte ActiveX-Steuerelementcontainer-Projekt namens "Container" und ein eingebettetes Steuerelement mit dem Namen Circ als Beispiele in den Prozeduren und den Code.

Verwenden die Schaltfläche "Ereignisse" im Eigenschaftenfenster angezeigt, können Sie eine Übersicht über Ereignisse, die auftreten können, erstellen, in Ihrem ActiveX-Steuerelementcontainer-Anwendung. Diese Zuordnung, die eine "Event-Senke-Zuordnung", aufgerufen wird erstellt und vom Visual C++ verwaltet werden, wenn Sie die Control-Container-Klasse-Ereignishandler hinzufügen. Jeder Ereignishandler, die mit einer Ereignis-Zuordnungseintrag implementiert wird ein bestimmtes Ereignis ein Ereignishandler-containermemberfunktion zugeordnet. Diese Ereignis-Handler-Funktion wird aufgerufen, wenn das angegebene Ereignis vom Objekt ActiveX-Steuerelement ausgelöst wird.

Weitere Informationen zu ereignissenkenzuordnungen, finden Sie unter [Ereigniszuordnungen Senke](../mfc/reference/event-sink-maps.md) in die *Klassenbibliotheksreferenz*.

##  <a name="_core_event_handler_modifications_to_the_project"></a> Ereignis-Handler Änderungen am Projekt

Wenn Sie das Fenster "Eigenschaften" verwenden, um Ereignishandler hinzuzufügen, ist eine Senke ereigniszuordnung deklariert und in Ihrem Projekt definiert. Die folgenden Anweisungen werden an das Steuerelement hinzugefügt. CPP-Datei beim ersten ein Ereignishandler hinzugefügt wird. Dieser Code deklariert eine Event-Senke-Zuordnung für die Dialogfeldklasse (in diesem Fall `CContainerDlg`):

[!code-cpp[NVC_MFC_AxCont#8](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_1.cpp)]
[!code-cpp[NVC_MFC_AxCont#9](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_2.cpp)]

Wie Sie das Fenster "Eigenschaften" verwenden, um Ereignisse hinzuzufügen, wird ein Ereignis Eintrag zuordnen (`ON_EVENT`) wurde für die Senke ereigniszuordnung und ein Ereignishandler Funktion hinzugefügt wird, auf den Container-Implementierung (. CPP)-Datei.

Das folgende Beispiel deklariert einen Ereignishandler namens `OnClickInCircCtrl`, für des Steuerelements des Circ `ClickIn` Ereignis:

[!code-cpp[NVC_MFC_AxCont#10](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_3.cpp)]

Darüber hinaus wird die folgende Vorlage hinzugefügt, um die `CContainerDlg` -klassenimplementierung (. CPP)-Datei für die Ereignis-Handler-Member-Funktion:

[!code-cpp[NVC_MFC_AxCont#11](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_4.cpp)]

Weitere Informationen zum Ereignissenke Makros, finden Sie unter [Ereignissenkenzuordnungen](../mfc/reference/event-sink-maps.md) in die *Klassenbibliotheksreferenz*.

#### <a name="to-create-an-event-handler-function"></a>Erstellen Sie eine Ereignishandlerfunktion

1. Wählen Sie aus der Klassenansicht die Dialogfeldklasse, die das ActiveX-Steuerelement enthält. In diesem Beispiel verwenden `CContainerDlg`.

1. Klicken Sie im Eigenschaftenfenster auf die **Ereignisse** Schaltfläche.

1. Wählen Sie im Fenster Eigenschaften die Steuerelement-ID des eingebetteten ActiveX-Steuerelements. In diesem Beispiel verwenden `IDC_CIRCCTRL1`.

   Das Fenster "Eigenschaften" zeigt eine Liste der Ereignisse, die durch das eingebettete ActiveX-Steuerelement ausgelöst werden kann. Eine Memberfunktion leiten, die bereits fett formatiert dargestellte hat Handlerfunktionen zugewiesen ist.

1. Wählen Sie das Ereignis, das die Dialogfeldklasse, behandeln soll. Wählen Sie für dieses Beispiel **klicken Sie auf**.

1. Wählen Sie aus dem Dropdown-Listenfeld auf der rechten Seite,  **\<hinzufügen > ClickCircctrl1 aus**.

1. Doppelklicken Sie auf die neue Handlerfunktion aus der Klassenansicht springen zu den Ereignishandlercode in der Implementierung (. CPP)-Datei des `CContainerDlg`.

## <a name="see-also"></a>Siehe auch

[ActiveX-Steuerelementcontainer](../mfc/activex-control-containers.md)

