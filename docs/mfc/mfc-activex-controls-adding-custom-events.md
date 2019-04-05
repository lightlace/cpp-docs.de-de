---
title: 'MFC-ActiveX-Steuerelemente: Hinzufügen von benutzerdefinierten Ereignissen'
ms.date: 11/04/2016
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
ms.openlocfilehash: 48c5ddbc8a3bcf6f74c251820e83cdebcef05bc9
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781002"
---
# <a name="mfc-activex-controls-adding-custom-events"></a>MFC-ActiveX-Steuerelemente: Hinzufügen von benutzerdefinierten Ereignissen

Benutzerdefinierte Ereignisse unterscheiden sich von vordefinierten Ereignissen, da sie nicht automatisch von-Klasse ausgelöst wurden `COleControl`. Ein benutzerdefiniertes Ereignis erkennt, eine bestimmte Aktion, der vom Entwickler Steuerelements als Ereignis bestimmt wird. Der Ereignis-Zuordnungseinträge für benutzerdefinierte Ereignisse werden durch das EVENT_CUSTOM-Makro dargestellt. Im folgende Abschnitt implementiert ein benutzerdefiniertes Ereignis für ein ActiveX-Steuerelement, das mit dem ActiveX-Steuerelement-Assistenten erstellt wurde.

##  <a name="_core_adding_a_custom_event_with_classwizard"></a> Hinzufügen eines benutzerdefinierten Ereignisses mit der Ereignis-Assistent zum Hinzufügen von

Das folgende Verfahren fügt ein bestimmtes benutzerdefiniertes Ereignis ClickIn hinzu. Sie können dieses Verfahren verwenden, andere benutzerdefinierte Ereignisse hinzufügen. Ersetzen Sie den Namen Ihres benutzerdefinierten Ereignis und seine Parameter für den Namen der ClickIn-Ereignis und Parameter.

#### <a name="to-add-the-clickin-custom-event-using-the-add-event-wizard"></a>Das benutzerdefinierte ClickIn-Ereignis mithilfe des Assistenten zum Hinzufügen von Ereignis hinzufügen

1. Laden Sie das Steuerelementprojekt.

1. In der Klassenansicht mit der rechten Maustaste der ActiveX-Steuerelementklasse, um das Kontextmenü zu öffnen.

1. Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Ereignis hinzufügen**.

   Daraufhin den Assistenten zum Hinzufügen eines Ereignisses.

1. In der **Ereignisnamen** , zunächst wählen Sie ein vorhandenes Ereignis, und klicken Sie dann auf die **benutzerdefinierte** Radio Schaltfläche, und geben Sie *ClickIn*.

1. In der **interner Name** geben den Namen des Ereignisses ausgelöst-Funktion. In diesem Beispiel verwenden Sie den Standardwert, der durch den Assistenten zum Hinzufügen eines Ereignisses angegeben (`FireClickIn`).

1. Fügen Sie einen Parameter namens *xCoord* (Typ *OLE_XPOS_PIXELS*) unter Verwendung der **Parametername** und **Parametertyp** Steuerelemente.

1. Hinzufügen einen zweiten Parameter mit *dem Namen yCoord* (Typ *OLE_YPOS_PIXELS*).

1. Klicken Sie auf **Fertig stellen** das Ereignis erstellt.

##  <a name="_core_classwizard_changes_for_custom_events"></a> Terminänderungen-Assistenten für benutzerdefinierte Ereignisse hinzufügen

Wenn Sie ein benutzerdefiniertes Ereignis hinzufügen, ändert den Assistenten zum Hinzufügen eines Ereignisses die Control-Klasse. H. CPP, und. IDL-Dateien. Die folgenden Codebeispiele gelten für das ClickIn-Ereignis zur Verfügung.

Die folgenden Zeilen werden hinzugefügt, auf den Header (. H)-Datei der Steuerelementklasse:

[!code-cpp[NVC_MFC_AxUI#7](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_1.h)]

Dieser Code deklariert eine Inlinefunktion aufgerufen `FireClickIn` aufruft, [COleControl::](../mfc/reference/colecontrol-class.md#fireevent) mit den ClickIn-Ereignis und den Parametern Sie definiert mithilfe des Assistenten zum Hinzufügen eines Ereignisses.

Darüber hinaus wird die folgende Zeile hinzugefügt, um die ereigniszuordnung für das Steuerelement befindet sich in der Implementierung (. Der Steuerelementklasse CPP)-Datei:

[!code-cpp[NVC_MFC_AxUI#8](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_2.cpp)]

Dieser Code ordnet das ClickIn Inlinefunktion `FireClickIn`, übergeben die Parameter, die Sie mit den Assistenten zum Hinzufügen von Ereignis definiert.

Schließlich wird die folgende Zeile des Steuerelements hinzugefügt. IDL-Datei:

[!code-cpp[NVC_MFC_AxUI#9](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_3.idl)]

Diese Zeile weist dem ClickIn-Ereignis eine bestimmte ID-Nummer, von der Position des Ereignisses in der Liste der Assistent zum Hinzufügen von Ereignis-Ereignis. Der Eintrag in der Ereignisliste können einen Container für das Ereignis zu erwarten. Beispielsweise kann es Handlercode bereitstellen, wird ausgeführt, wenn das Ereignis ausgelöst wird.

##  <a name="_core_calling_fireclickin"></a> FireClickIn aufrufen

Nun, da Sie das benutzerdefinierte ClickIn-Ereignis mithilfe des Assistenten zum Hinzufügen von Ereignis hinzugefügt haben, müssen Sie entscheiden, wenn dieses Ereignis wird ausgelöst. Rufen Sie dazu `FireClickIn` Wenn die entsprechende Aktion ausgeführt wird. Für den Rahmen dieser Erläuterung verwendet das Steuerelement die `InCircle` Funktion innerhalb eines WM_LBUTTONDOWN-meldungshandlers, klickt ein Benutzer in einer kreisförmigen oder elliptischen Bereich das ClickIn-Ereignis auszulösen. Das folgende Verfahren wird die WM_LBUTTONDOWN-Handler hinzugefügt.

#### <a name="to-add-a-message-handler-with-the-add-event-wizard"></a>Zum Hinzufügen einer Nachricht mit dem Assistenten zum Hinzufügen von Ereignis

1. Laden Sie das Steuerelementprojekt.

1. Wählen Sie in der Klassenansicht die ActiveX-Steuerelementklasse.

1. Klicken Sie im Eigenschaftenfenster auf die **Nachrichten** Schaltfläche.

   Das Fenster "Eigenschaften" zeigt eine Liste der Nachrichten, die von der ActiveX-Steuerelement behandelt werden können. Jede Nachricht, die bereits fett formatiert dargestellte hat es sich um eine Handlerfunktion zugewiesen.

1. Wählen Sie im Eigenschaftenfenster die Nachricht, die Sie behandeln möchten. Wählen Sie in diesem Beispiel WM_LBUTTONDOWN.

1. Wählen Sie aus dem Dropdown-Listenfeld auf der rechten Seite,  **\<hinzufügen > OnLButtonDown**.

1. Doppelklicken Sie auf die neue Handlerfunktion in der Klassenansicht springen zu den Meldungshandlercode in der Implementierung (. CPP)-Datei des ActiveX-Steuerelements.

Der folgende code Beispiel ruft die `InCircle` Funktion jedes Mal, wenn die linke Maustaste in das Fenster des Steuerelements geklickt wird. In diesem Beispiel finden Sie in der Handlerfunktion WM_LBUTTONDOWN, `OnLButtonDown`in die [für CIRC](../overview/visual-cpp-samples.md) abstrakt.

[!code-cpp[NVC_MFC_AxUI#10](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_4.cpp)]

> [!NOTE]
>  Wenn den Assistenten zum Hinzufügen einer Event Message-Handler für die Aktionen der Maus erstellt wird, wird ein Aufruf an den gleichen Meldungshandler der Basisklasse automatisch hinzugefügt. Entfernen Sie diesen Aufruf nicht. Wenn das Steuerelement eine der vordefinierten Maus Nachrichten verwendet, müssen die Message-Handler in der Basisklasse aufgerufen werden, um sicherzustellen, dass die Erfassung von Mauseingaben ordnungsgemäß verarbeitet wird.

Im folgenden Beispiel wird das Ereignis ausgelöst, nur bei der Klick innerhalb einer kreisförmigen oder elliptischen Region innerhalb des Steuerelements ausgelöst. Um dieses Verhalten zu erreichen, können Sie platzieren die `InCircle` Funktion des Steuerelements-Implementierung (. CPP)-Datei:

[!code-cpp[NVC_MFC_AxUI#11](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_5.cpp)]

Sie müssen auch die folgende Deklaration hinzufügen der `InCircle` Funktion des Steuerelements-Header (. H)-Datei:

[!code-cpp[NVC_MFC_AxUI#12](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_6.h)]

##  <a name="_core_custom_events_with_stock_names"></a> Benutzerdefinierter Ereignisse mit vordefinierten Namen

Sie können benutzerdefinierte Ereignisse mit dem gleichen Namen wie die vordefinierten Ereignissen erstellen, aber Sie nicht beide auf dasselbe Steuerelement implementieren können. Beispielsweise empfiehlt es sich zum Erstellen eines benutzerdefinierten Ereignisses aufgerufen, klicken Sie auf, die nicht ausgelöst wird, wenn das Ereignis auf normalerweise auslösen würde. Sie können das Click-Ereignis klicken Sie dann zu einem beliebigen Zeitpunkt auslösen, durch Aufrufen der Funktion auslösen.

Das folgende Verfahren fügt eine benutzerdefinierte auf Ereignis.

#### <a name="to-add-a-custom-event-that-uses-a-stock-event-name"></a>Zum Hinzufügen eines benutzerdefinierten Ereignisses verwendet, die den Namen einer vordefinierten Ereignisses

1. Laden Sie das Steuerelementprojekt.

1. In der Klassenansicht mit der rechten Maustaste der ActiveX-Steuerelementklasse, um das Kontextmenü zu öffnen.

1. Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Ereignis hinzufügen**.

   Daraufhin den Assistenten zum Hinzufügen eines Ereignisses.

1. In der **Ereignisnamen** Dropdown-Liste, wählen Sie einen Ereignis-Namen. Wählen Sie für dieses Beispiel **klicken Sie auf**.

1. Für **Ereignistyp**Option **benutzerdefinierte**.

1. Klicken Sie auf **Fertig stellen** das Ereignis erstellt.

1. Rufen Sie `FireClick` an geeigneten Stellen in Ihrem Code.

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)<br/>
[MFC-ActiveX-Steuerelemente: Methoden](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl-Klasse](../mfc/reference/colecontrol-class.md)
