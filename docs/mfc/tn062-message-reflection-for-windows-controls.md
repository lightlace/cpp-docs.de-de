---
title: 'TN062: Meldungsreflektion für Windows-Steuerelemente'
ms.date: 06/28/2018
f1_keywords:
- vc.controls.messages
helpviewer_keywords:
- ON_WM_VKEYTOITEM_REFLECT macro [MFC]
- ON_WM_DRAWITEM_REFLECT macro [MFC]
- ON_WM_VSCROLL_REFLECT macro [MFC]
- ON_NOTIFY_REFLECT message [MFC]
- ON_CONTROL_REFLECT_EX macro [MFC]
- ON_UPDATE_COMMAND_UI_REFLECT macro [MFC]
- ON_NOTIFY_REFLECT_EX message [MFC]
- ON_WM_HSCROLL_REFLECT macro [MFC]
- message reflection [MFC]
- ON_WM_COMPAREITEM_REFLECT macro [MFC]
- ON_WM_MEASUREITEM_REFLECT macro [MFC]
- ON_NOTIFY message [MFC]
- WM_COMMAND [MFC]
- WM_CTLCOLOR message [MFC]
- TN062 [MFC]
- ON_WM_CHARTOITEM_REFLECT macro [MFC]
- ON_WM_CTLCOLOR_REFLECT macro [MFC]
- ON_WM_DELETEITEM_REFLECT macro [MFC]
- notification messages [MFC]
- ON_WM_PARENTNOTIFY_REFLECT macro [MFC]
- WM_NOTIFY message [MFC]
- ON_CONTROL_REFLECT macro
ms.assetid: 53efb0ba-fcda-4fa0-a3c7-14e0b78fb494
ms.openlocfilehash: aa189eec430d72bef753fef7ebbe9ad929d76c87
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677499"
---
# <a name="tn062-message-reflection-for-windows-controls"></a>TN062: Meldungsreflektion für Windows-Steuerelemente

> [!NOTE]
> Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

Diese technische Hinweis beschreibt Meldungsreflektion, ein neues Feature in MFC 4.0. Sie enthält auch Anweisungen zum Erstellen eines einfachen wiederverwendbaren Steuerelements, das Nachricht Reflektionen verwendet.

Diese technische Hinweis umfasst keine Meldungsreflektion, angewendet auf ActiveX-Steuerelementen (früher OLE-Steuerelemente). Finden Sie im Artikel [ActiveX-Steuerelemente: Erstellen von Unterklassen für ein Windows-Steuerelement](../mfc/mfc-activex-controls-subclassing-a-windows-control.md).

**Was ist Meldungsreflektion**

Windows-Steuerelemente werden häufig benachrichtigungsmeldungen an übergeordneten Fenster senden. Z. B. viele Steuerelemente eine Steuerelement Farbe Benachrichtigung gesendet wird (WM_CTLCOLOR oder eine ihrer Varianten) auf das übergeordnete Objekt das übergeordnete Element, geben Sie einen Pinsel zum Zeichnen des Hintergrunds des Steuerelements zu ermöglichen.

In Windows und in MFC vor Version 4.0 ist das übergeordnete Fenster, häufig ein Dialogfeld für die Verarbeitung dieser Nachrichten verantwortlich. Dies bedeutet, dass der Code zum Verarbeiten der Nachricht in des übergeordneten Fensters Klasse sein muss und dass in jeder Klasse dupliziert werden, die die Nachricht zu bewältigen ist. Im obigen Fall müssten jedem Dialogfeld an, die Steuerelemente mit benutzerdefinierten Hintergrund verwenden wollten, behandeln die Benachrichtigung des Steuerelement-Farbe. Es wäre wesentlich einfacher, Code wiederzuverwenden, wenn eine Steuerelement-Klasse, dass, die ihre eigene Hintergrundfarbe hashbasiertes geschrieben werden kann.

In MFC 4.0, funktioniert der alte Mechanismus weiterhin – übergeordnete Fenster können Nachrichten verarbeiten. Darüber hinaus jedoch MFC 4.0 ermöglicht die Wiederverwendung durch die Bereitstellung eines Features namens "Reflection message", mit der diese Benachrichtigungen in das Fenster des untergeordneten Steuerelements oder das übergeordnete Fenster oder in beiden behandelt werden können. Im Steuerelement Hintergrund Farbe Beispiel können Sie jetzt eine Steuerelement-Klasse, die ihre eigene Hintergrundfarbe festlegt, durch das Behandeln von reflektierten WM_CTLCOLOR-Meldung schreiben – alles ohne sich an das übergeordnete Element. (Beachten Sie, dass da Meldungsreflektion von MFC implementiert wird, nicht von Windows, die übergeordnete Fenster-Klasse abgeleitet werden muss `CWnd` für Meldungsreflektion funktioniert.)

Ältere Versionen von MFC hat etwa Meldungsreflektion durch die Bereitstellung von virtueller Funktionen für einige Meldungen, z. B. Nachrichten für die Ownerdrawn-Listenfelder (WM_DRAWITEM und So weiter). Der neue Nachricht Reflektion Mechanismus ist generalisierten und konsistent.

Meldungsreflektion ist abwärtskompatibel mit dem Code für MFC-Versionen vor 4.0.

Sie haben einen Handler für eine bestimmte Nachricht angegeben neu, für einen Bereich von Nachrichten, die in Ihrer übergeordneten Fensters Klasse überschreibt es Message-Handler für die gleiche Nachricht, sofern Sie nicht die Funktion der Basisklasse-Handler in Ihren eigenen Handler aufrufen. Wenn Sie Ihre Dialogfeldklasse WM_CTLCOLOR behandeln, werden Ihre Behandlung z. B. reflektierte Meldungshandler überschrieben.

Wenn in Ihrer übergeordneten Fenster-Klasse, Sie einen Handler für eine bestimmte WM_NOTIFY-Meldung oder einen Bereich der WM_NOTIFY-Meldungen angeben, wird der Handler nur, wenn das untergeordnete Steuerelement senden dieser Nachrichten keinen reflektierte Meldungshandler über aufgerufen werden `ON_NOTIFY_REFLECT()`. Bei Verwendung von `ON_NOTIFY_REFLECT_EX()` in Ihre meldungszuordnung, Ihr Nachrichtenhandler kann, oder können sich nicht auf das übergeordnete Fenster, die Meldung zu behandeln. Wenn der Handler zurückgibt **"false"**, die Nachricht wird vom übergeordneten Element ebenfalls verarbeitet werden, während ein Aufruf, der zurückgegeben **"true"** lässt sich nicht auf das übergeordnete Element, um es zu verarbeiten. Beachten Sie, dass die reflektierte Meldung vor der benachrichtigungsmeldung verarbeitet wird.

Wenn eine WM_NOTIFY-Meldung gesendet wird, wird das Steuerelement zuerst die Möglichkeit für seine Handhabung angeboten. Wenn alle anderen reflektierte Meldung gesendet wird, das übergeordnete Fenster hat der ersten Gelegenheit verlassen, sie zu behandeln, und das Steuerelement wird die reflektierte Meldung. Zu diesem Zweck benötigen sie eine Handlerfunktion und einen entsprechenden Eintrag in der meldungszuordnung für des Steuerelements-Klasse.

Das Makro meldungszuordnung für reflektierter Meldungen ist etwas anders als für reguläre Benachrichtigungen: Es hat *_REFLECT* an den üblichen Namen angefügt. Um eine WM_NOTIFY-Meldung in das übergeordnete Element zu behandeln, verwenden Sie z. B. das ON_NOTIFY-Makro in die nachrichtenzuordnung des übergeordneten Elements. Um die reflektierte Meldung im untergeordneten Steuerelement zu behandeln, verwenden Sie das ON_NOTIFY_REFLECT-Makro in die nachrichtenzuordnung des untergeordneten Steuerelements. In einigen Fällen sind die Parameter auch unterschiedlich. Beachten Sie, dass Klassen-Assistent kann in der Regel fügen die Meldungszuordnungseinträge für Sie und Implementierungen der Skeleton-Funktion mit den richtigen Parametern stellen.

Finden Sie unter [TN061: ON_NOTIFY- und WM_NOTIFY-Meldungen](../mfc/tn061-on-notify-and-wm-notify-messages.md) Informationen für die neue WM_NOTIFY-Nachricht.

**Meldungszuordnungseinträge und Handler Funktionsprototypen für reflektierte Meldungen**

Um eine reflektierte Steuerelement Meldung zu behandeln, verwenden Sie Meldungszuordnungsmakros und Funktionsprototypen, die in der folgenden Tabelle aufgeführt.

Klassen-Assistent kann in der Regel fügen diese Meldungszuordnungseinträge für Sie und Skeleton-Funktion-Implementierungen bereitstellen. Finden Sie unter [Definieren eines Meldungshandlers für eine Nachricht wiedergegeben](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md) für Informationen zur Verwendung von Ereignishandlern für reflektierter Meldungen zu definieren.

Stellen Sie zum Konvertieren von Namen der in der reflektierten Makroname *ON_* , und fügen Sie *_REFLECT*. So wird z. B. WM_CTLCOLOR ON_WM_CTLCOLOR_REFLECT. (Um anzuzeigen, welche Nachrichten berücksichtigt werden können, werden Sie die umgekehrte Konvertierung für die Makroeinträge in der Tabelle unten).

Die drei Ausnahmen von der oben genannten Regel lauten folgendermaßen:

- Das Makro für WM_COMMAND-Benachrichtigungen ist ON_CONTROL_REFLECT.

- Das Makro für WM_NOTIFY Reflexionen ist ON_NOTIFY_REFLECT.

- Das Makro für ON_UPDATE_COMMAND_UI Reflexionen ist ON_UPDATE_COMMAND_UI_REFLECT.

In den einzelnen oben aufgeführten Sonderfälle müssen Sie den Namen der Memberfunktion Handler angeben. In anderen Fällen müssen Sie den Standardnamen für die Handlerfunktion verwenden.

Die Bedeutung der Parameter und Rückgabewerte von Funktionen sind unter den Namen der Funktion oder den Funktionsnamen mit dokumentiert *auf* vorangestellt. Z. B. `CtlColor` finden Sie unter `OnCtlColor`. Mehrere reflektierte Meldungshandler benötigen weniger Parameter als die ähnliche Handler in ein übergeordnetes Fenster. Die Namen in der folgenden Tabelle mit den Namen der formalen Parameter in der Dokumentation übereinstimmt.

|Zuordnungseintrag|Funktionsprototyp|
|---------------|------------------------|
|**ON_CONTROL_REFLECT (** `wNotifyCode` **,** `memberFxn` **)**|**die "void" Afx_msg** `memberFxn` **();**|
|**ON_NOTIFY_REFLECT (** `wNotifyCode` **,** `memberFxn` **)**|**die "void" Afx_msg** `memberFxn` **(NMHDR** <strong>\*</strong> `pNotifyStruct` **, LRESULT** <strong>\*</strong> *Ergebnis* **);**|
|**ON_UPDATE_COMMAND_UI_REFLECT (** `memberFxn` **)**|**die "void" Afx_msg** `memberFxn` **(CCmdUI** <strong>\*</strong> `pCmdUI` **);**|
|**ON_WM_CTLCOLOR_REFLECT)**|**Afx_msg HBRUSH CtlColor vor (CDC** <strong>\*</strong> `pDC` **, "uint"** `nCtlColor` **);**|
|**ON_WM_DRAWITEM_REFLECT)**|**Afx_msg "void" DrawItem (LPDRAWITEMSTRUCT** `lpDrawItemStruct` **);**|
|**ON_WM_MEASUREITEM_REFLECT)**|**Afx_msg "void" MeasureItem (LPMEASUREITEMSTRUCT** `lpMeasureItemStruct` **);**|
|**ON_WM_DELETEITEM_REFLECT)**|**Afx_msg "void" DeleteItem (LPDELETEITEMSTRUCT** `lpDeleteItemStruct` **);**|
|**("ON_WM_COMPAREITEM_REFLECT)**|**Afx_msg Int CompareItem (LPCOMPAREITEMSTRUCT** `lpCompareItemStruct` **);**|
|**ON_WM_CHARTOITEM_REFLECT)**|**Afx_msg Int CharToItem (UINT** `nKey` **, "uint"** `nIndex` **);**|
|**ON_WM_VKEYTOITEM_REFLECT)**|**Afx_msg Int VKeyToItem (UINT** `nKey` **, "uint"** `nIndex` **);**|
|**ON_WM_HSCROLL_REFLECT)**|**Afx_msg "void" HScroll (UINT** `nSBCode` **, "uint"** `nPos` **);**|
|**ON_WM_VSCROLL_REFLECT)**|**Afx_msg "void" VScroll (UINT** `nSBCode` **, "uint"** `nPos` **);**|
|**ON_WM_PARENTNOTIFY_REFLECT)**|**Afx_msg "void" ParentNotify (UINT** `message` **, LPARAM** `lParam` **);**|

Die Makros ON_NOTIFY_REFLECT und ON_CONTROL_REFLECT haben Varianten, die mehr als ein Objekt (z. B. das Steuerelement und seinem übergeordneten Element) zu ermöglichen, um eine bestimmte Nachricht zu verarbeiten.

|Zuordnungseintrag|Funktionsprototyp|
|---------------|------------------------|
|**ON_NOTIFY_REFLECT_EX (** `wNotifyCode` **,** `memberFxn` **)**|**Afx_msg "bool"** `memberFxn` **(NMHDR** <strong>\*</strong> `pNotifyStruct` **, LRESULT** <strong>\*</strong> *Ergebnis* **);**|
|**ON_CONTROL_REFLECT_EX (** `wNotifyCode` **,** `memberFxn` **)**|**Afx_msg "bool"** `memberFxn` **();**|

## <a name="handling-reflected-messages-an-example-of-a-reusable-control"></a>Umgang mit Nachrichten reflektiert: Ein Beispiel für ein Wiederverwendbares Steuerelement

In diesem einfache Beispiel erstellt ein wiederverwendbares Steuerelement namens `CYellowEdit`. Das Steuerelement funktioniert identisch mit einem regulären Edit-Steuerelement, mit dem Unterschied, dass schwarzen Text auf einen gelben Hintergrund angezeigt. Es wäre einfach, Member-Funktionen hinzuzufügen, die ermöglichen die `CYellowEdit` -Steuerelement zum Anzeigen von verschiedenen Farben.

### <a name="to-try-the-example-that-creates-a-reusable-control"></a>Zum Testen dieses Beispiels erstellt, die ein wiederverwendbares Steuerelement

1. Erstellen Sie ein neues Dialogfeld, in einer vorhandenen Anwendung. Weitere Informationen finden Sie unter den [Dialog-Editor](../windows/dialog-editor.md) Thema.

   Sie benötigen eine Anwendung, in dem das wiederverwendbare Steuerelement zu entwickeln. Wenn Sie eine vorhandene Anwendung verwendet haben, erstellen Sie eine Dialogfeldern basierende Anwendung mithilfe von AppWizard.

2. Verwenden Sie die Klassen-Assistent mit Ihrem Projekt in Visual C++ geladen wird, erstellen Sie eine neue Klasse namens `CYellowEdit` basierend auf `CEdit`.

3. Fügen Sie drei Membervariablen auf Ihre `CYellowEdit` Klasse. Die ersten beiden werden *COLORREF* Variablen, um die Textfarbe und die Farbe des Hintergrunds aufzunehmen. Die dritte werden eine `CBrush` -Objekt, das den Pinsel für das Zeichnen des Hintergrunds enthalten soll. Die `CBrush` Objekt können Sie die Erstellung den Pinsel, lediglich auf Sie verwiesen wird, und den Pinsel automatisch beim Zerstören der `CYellowEdit` Steuerelement zerstört wird.

4. Initialisieren Sie die Membervariablen, durch den Konstruktor wie folgt schreiben:

    ```cpp
    CYellowEdit::CYellowEdit()
    {
        m_clrText = RGB(0, 0, 0);
        m_clrBkgnd = RGB(255, 255, 0);
        m_brBkgnd.CreateSolidBrush(m_clrBkgnd);
    }
    ```

5. Mithilfe der Klassen-Assistent, Hinzufügen eines ereignishandlers für die reflektierte WM_CTLCOLOR-Meldung zu Ihrer `CYellowEdit` Klasse. Beachten Sie, dass das Gleichheitszeichen vor der Nachrichtenname, in der Liste der Nachrichten, die Sie behandeln können, gibt an, dass die Meldung reflektiert wird. Finden Sie im [Definieren eines Meldungshandlers für eine Nachricht wiedergegeben](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md).

   Klassen-Assistent fügt die folgende meldungszuordnung Makro und Skeleton-Funktion für Sie hinzu:

    ```cpp
    ON_WM_CTLCOLOR_REFLECT()
    // Note: other code will be in between....

    HBRUSH CYellowEdit::CtlColor(CDC* pDC, UINT nCtlColor)
    {
        // TODO: Change any attributes of the DC here
        // TODO: Return a non-NULL brush if the
        //       parent's handler should not be called
        return NULL;
    }
    ```

6. Ersetzen Sie den Text der Funktion, mit dem folgenden Code. Dieser Code legt die Textfarbe, die Farbe des Texthintergrunds und die Hintergrundfarbe für den Rest des Steuerelements.

    ```cpp
    pDC->SetTextColor(m_clrText);   // text
    pDC->SetBkColor(m_clrBkgnd);    // text bkgnd
    return m_brBkgnd;               // ctl bkgnd
    ```

7. Erstellen Sie ein Edit-Steuerelement in einem Dialogfeld aus, und fügen Sie es mit einer Membervariablen durch Doppelklicken auf das Steuerelement zum Bearbeiten bei gedrückter STRG-Taste. Klicken Sie im Dialogfeld Hinzufügen von Membervariablen beenden Sie den Namen den Variablen, und wählen Sie "Control" für die Kategorie, klicken Sie dann "CYellowEdit" für den Variablentyp. Vergessen Sie nicht die Aktivierreihenfolge im Dialogfeld festlegen. Darüber hinaus werden Sie sicher, dass die Headerdatei für die `CYellowEdit` -Steuerelement in einem Dialogfeld-Headerdatei.

8. Erstellen Sie Ihre Anwendung, und führen Sie sie aus. Das Steuerelement zum Bearbeiten haben einen gelben Hintergrund.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
