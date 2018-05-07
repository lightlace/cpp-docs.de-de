---
title: 'TN062: Message Reflektion für Windows-Steuerelemente | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.controls.messages
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba8e9cac3b7f7997da8c620966234a630b9b9fbd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="tn062-message-reflection-for-windows-controls"></a>TN062: Meldungsreflektion für Windows-Steuerelemente
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 In diesem technischen Hinweis beschreibt Meldungsreflektion, ein neues Feature in MFC 4.0. Außerdem enthält es Anleitungen zum Erstellen eines einfachen wiederverwendbaren-Steuerelements, das Meldungsreflektion verwendet.  
  
 In diesem technischen Hinweis umfasst keine Meldungsreflektion für ActiveX-Steuerelemente (früher OLE-Steuerelemente bezeichnet) anwenden. Finden Sie im Artikel [ActiveX-Steuerelemente: einer Fenstersteuerelement](../mfc/mfc-activex-controls-subclassing-a-windows-control.md).  
  
 **Was ist Meldungsreflektion**  
  
 Windows-Steuerelemente senden häufig benachrichtigungsmeldungen an übergeordneten Fenster. Beispielsweise senden viele Steuerelemente, die eine Meldung Farbe Control (`WM_CTLCOLOR` oder einer dessen Varianten) auf das übergeordnete Objekt das übergeordnete Element ein Pinsels zum Zeichnen der Hintergrund des Steuerelements angeben können.  
  
 In Windows und MFC vor Version 4.0 ist das übergeordnete Fenster, häufig ein Dialogfeld für die Behandlung dieser Nachrichten verantwortlich. Dies bedeutet, dass der Code zum Verarbeiten der Nachricht in das übergeordnete Fenster Klasse sein muss und ob er hat in jeder Klasse dupliziert werden, die diese Nachricht verarbeiten muss. Im obigen Fall müsste jede (Dialogfeld), die Steuerelemente mit benutzerdefinierten Hintergrund verwenden wollten die Farbe Control-Nachricht zu verarbeiten. Es wäre es viel einfacher, Code wiederzuverwenden, wenn eine Steuerelement-Klasse, die eine eigenen Hintergrundfarbe behandelt würden geschrieben werden konnte.  
  
 In MFC 4.0 der alte Mechanismus funktioniert – übergeordnete Fenster benachrichtigungsmeldungen behandeln können. Darüber hinaus jedoch MFC 4.0 erleichtert die Wiederverwendung durch eine Funktion namens "message Reflektion" bereitstellen, mit dessen Hilfe diese benachrichtigungsmeldungen an das Fenster des untergeordneten Steuerelements oder das übergeordnete Fenster, oder in beiden behandelt werden. Im Beispiel Farbe Control Hintergrund können Sie jetzt eine Steuerelementklasse, die eine eigenen Hintergrundfarbe festgelegt, durch die Behandlung der reflektierte schreiben `WM_CTLCOLOR` Nachricht – alles ohne Rückgriff auf das übergeordnete Element. (Beachten Sie, dass da Meldungsreflektion von MFC implementiert wird, nicht von Windows, die übergeordnete Fenster-Klasse abgeleitet werden muss `CWnd` für Meldungsreflektion funktioniert.)  
  
 Ältere Versionen von MFC hat etwa Meldungsreflektion durch die Bereitstellung von virtueller Funktionen für einige Nachrichten, z. B. Nachrichten für die Ownerdrawn-Listenfelder (`WM_DRAWITEM`usw.). Die neue Nachricht Reflektion Mechanismus ist generalisierte und konsistent.  
  
 Meldungsreflexion ist abwärtskompatibel mit für MFC-Versionen vor 4.0 geschriebenen Codes.  
  
 Wenn Sie einen Handler für eine bestimmte Nachricht angegeben haben, oder für einen Bereich von Nachrichten in das übergeordnete Fenster-Klasse wird überschrieben widergespiegelt Meldungshandler für dieselbe Nachricht bereitgestellten in einen eigenen Handler keine Handler-Funktion der Basisklasse aufgerufen werden. Wenn Sie verarbeiten, z. B. `WM_CTLCOLOR` in Ihre Dialogfeldklasse Ihrer Behandlung werden alle reflektierte fenstermeldungs-Handler überschrieben.  
  
 Wenn in Ihrer übergeordneten Fensterklasse einen Handler für ein bestimmtes standardimages **WM_NOTIFY** Nachricht oder eine Reihe von **WM_NOTIFY** Nachrichten, der Handler wird aufgerufen werden, nur dann, wenn das untergeordnete Steuerelement diese Nachrichten gesendet werden nicht über die eine reflektierte Meldungshandler über **ON_NOTIFY_REFLECT()**. Bei Verwendung von **ON_NOTIFY_REFLECT_EX()** in Ihrer Zuordnung Nachricht Message-Handler kann oder der das übergeordnete Fenster für die Meldungsbehandlung möglicherweise nicht zugelassen. Wenn der Handler gibt **"false"**, die Nachricht wird durch das übergeordnete als auch behandelt werden, während ein Aufruf, der zurückgibt **"true"** lässt sich nicht auf das übergeordnete Element, um ihn zu beheben. Beachten Sie, dass die reflektierte Meldung vor der benachrichtigungsmeldung verarbeitet wird.  
  
 Wenn eine **WM_NOTIFY** Nachricht gesendet wird, wird das Steuerelement wird zuerst die Möglichkeit für seine Handhabung angeboten. Wenn eine andere reflektierte Meldung gesendet wird, wird das übergeordnete Fenster hat die erste Möglichkeit für seine Handhabung und das Steuerelement wird die reflektierte Meldung. Zu diesem Zweck benötigen sie eine Handlerfunktion und ein entsprechender Eintrag in der meldungszuordnung für das Steuerelement-Klasse.  
  
 Das meldungszuordnung Makro für reflektierte Meldungen ist etwas anders als reguläre Benachrichtigungen: Es wurde **_REFLECT** an den üblichen Namen angefügt. Beispielsweise behandeln eine **WM_NOTIFY** Nachricht in der übergeordneten Tabelle verwenden Sie das Makro `ON_NOTIFY` in meldungszuordnung des übergeordneten Elements. Um die reflektierte Meldung in das untergeordnete Steuerelement behandeln zu können, verwenden Sie die **ON_NOTIFY_REFLECT** Makro in das untergeordnete Steuerelement meldungszuordnung. In einigen Fällen unterscheiden sich die Parameter, ebenfalls. Beachten Sie, dass ClassWizard kann in der Regel fügen Sie der Meldungszuordnungseinträge für Sie und Implementierungen von Skeleton-Funktion mit den richtigen Parametern bereitstellen.  
  
 Finden Sie unter [TN061: ON_NOTIFY- und WM_NOTIFY-Meldungen](../mfc/tn061-on-notify-and-wm-notify-messages.md) Informationen auf dem neuen **WM_NOTIFY** Nachricht.  
  
 **Meldungszuordnungseinträge und Handler Funktionsprototypen für reflektierte Meldungen**  
  
 Behandeln Sie eine reflektierte Benachrichtigung Steuerungsnachricht verwenden Sie Meldungszuordnungsmakros und in der folgenden Tabelle aufgeführten Funktionsprototypen.  
  
 Klassen-Assistent kann in der Regel fügen diese Meldungszuordnungseinträge für Sie und Skeleton-funktionsimplementierungen bereitstellen. Finden Sie unter [Definieren eines Meldungshandlers für eine Nachricht reflektiert](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md) Informationen dazu, wie Handler für reflektierte Meldungen definiert.  
  
 Zum Konvertieren aus der Nachrichtenname, den reflektierten Makronamen voranstellen **ON_** und Anfügen **_REFLECT**. Beispielsweise `WM_CTLCOLOR` wird **ON_WM_CTLCOLOR_REFLECT**. (Um anzuzeigen, welche Nachrichten berücksichtigt werden können, müssen Sie die umgekehrte Konvertierung auf die Makroeinträge in der folgenden Tabelle).  
  
 Die drei Ausnahmen von der Regel, die oben genannten lauten folgendermaßen:  
  
-   Das Makro für **WM_COMMAND** Benachrichtigungen **ON_CONTROL_REFLECT**.  
  
-   Das Makro für **WM_NOTIFY** Reflektionen ist **ON_NOTIFY_REFLECT**.  
  
-   Das Makro für `ON_UPDATE_COMMAND_UI` Reflektionen ist **ON_UPDATE_COMMAND_UI_REFLECT**.  
  
 In jeder der oben genannten Sonderfälle müssen Sie den Namen der Memberfunktion Handler angeben. In anderen Fällen müssen Sie den Standardnamen für die Handlerfunktion verwenden.  
  
 Die Bedeutung der Parameter und Rückgabewerte von Funktionen werden unter den Namen der Funktion oder den Funktionsnamen mit dokumentiert **auf** vorangestellt wird. Z. B. **CtlColor vor** finden Sie im `OnCtlColor`. Mehrere reflektierte fenstermeldungs-Handler benötigen weniger Parameter als ähnliche Handler in ein übergeordnetes Fenster. Nur mit der passenden Namen in der folgenden Tabelle mit den Namen der formalen Parameter in der Dokumentation.  
  
|Eintrag für die Zuordnung|Funktionsprototyp|  
|---------------|------------------------|  
|**ON_CONTROL_REFLECT (** `wNotifyCode` **,** `memberFxn` **)**|**Afx_msg "void"** `memberFxn` **();**|  
|**ON_NOTIFY_REFLECT (** `wNotifyCode` **,** `memberFxn` **)**|**Afx_msg "void"** `memberFxn` **(NMHDR \***  `pNotifyStruct` **, LRESULT\***  *Ergebnis* **);**|  
|**ON_UPDATE_COMMAND_UI_REFLECT (** `memberFxn` **)**|**Afx_msg "void"** `memberFxn` **(CCmdUI\***  `pCmdUI` **);**|  
|**ON_WM_CTLCOLOR_REFLECT)**|**Afx_msg HBRUSH CtlColor vor (CDC\***  `pDC` **, "uint"** `nCtlColor` **);**|  
|**ON_WM_DRAWITEM_REFLECT)**|**Afx_msg "void" DrawItem (LPDRAWITEMSTRUCT** `lpDrawItemStruct` **);**|  
|**ON_WM_MEASUREITEM_REFLECT)**|**Afx_msg "void" MeasureItem (LPMEASUREITEMSTRUCT** `lpMeasureItemStruct` **);**|  
|**ON_WM_DELETEITEM_REFLECT)**|**Afx_msg "void" DeleteItem (LPDELETEITEMSTRUCT** `lpDeleteItemStruct` **);**|  
|**ON_WM_COMPAREITEM_REFLECT)**|**Afx_msg Int CompareItem (LPCOMPAREITEMSTRUCT** `lpCompareItemStruct` **);**|  
|**ON_WM_CHARTOITEM_REFLECT)**|**Afx_msg Int CharToItem ("uint"** `nKey` **, "uint"** `nIndex` **);**|  
|**ON_WM_VKEYTOITEM_REFLECT)**|**Afx_msg Int VKeyToItem ("uint"** `nKey` **, "uint"** `nIndex` **);**|  
|**ON_WM_HSCROLL_REFLECT)**|**Afx_msg "void" HScroll ("uint"** `nSBCode` **, "uint"** `nPos` **);**|  
|**ON_WM_VSCROLL_REFLECT)**|**Afx_msg "void" VScroll ("uint"** `nSBCode` **, "uint"** `nPos` **);**|  
|**ON_WM_PARENTNOTIFY_REFLECT)**|**Afx_msg "void" ParentNotify ("uint"** `message` **, LPARAM** `lParam` **);**|  
  
 Die **ON_NOTIFY_REFLECT** und **ON_CONTROL_REFLECT** Makros sind Variationen, die mehr als ein Objekt (z. B. das Steuerelement und seinem übergeordneten Element) auf eine bestimmte Nachricht verarbeiten können.  
  
|Eintrag für die Zuordnung|Funktionsprototyp|  
|---------------|------------------------|  
|**ON_NOTIFY_REFLECT_EX (** `wNotifyCode` **,** `memberFxn` **)**|**Afx_msg BOOL** `memberFxn` **(NMHDR \***  `pNotifyStruct` **, LRESULT\***  *Ergebnis* **);**|  
|**ON_CONTROL_REFLECT_EX (** `wNotifyCode` **,** `memberFxn` **)**|**Afx_msg BOOL** `memberFxn` **();**|  
  
## <a name="handling-reflected-messages-an-example-of-a-reusable-control"></a>Behandeln von reflektiert Nachrichten: Ein Beispiel eines wieder verwendbaren-Steuerelements  
 Dieses einfache Beispiel erstellt ein wiederverwendbares Steuerelement namens `CYellowEdit`. Das Steuerelement funktioniert genauso wie eine reguläre Edit-Steuerelement, mit dem Unterschied, dass er auf einen gelben Hintergrund werden als schwarzer Text angezeigt. Es kann leicht fehlschlagen, Memberfunktionen hinzu, die die Möglichkeit bietet, die `CYellowEdit` Steuerelement unterschiedliche Farben angezeigt.  
  
#### <a name="to-try-the-example-that-creates-a-reusable-control"></a>Zum Testen dieses Beispiels erstellt, die ein wiederverwendbares Steuerelement  
  
1.  Erstellen eines neuen Dialogfelds in einer vorhandenen Anwendung an. Weitere Informationen finden Sie unter der [Dialog-Editor](../windows/dialog-editor.md) Thema.  
  
     Benötigen Sie eine Anwendung, in der zum Entwickeln von wiederverwendbaren Steuerelements ein. Wenn Sie eine vorhandene Anwendung verwendet haben, erstellen Sie eine Dialogfeldern basierende Anwendung, die mithilfe von AppWizard.  
  
2.  Während das Projekt in Visual C++ geladen wird, verwenden Sie ClassWizard So erstellen eine neue Klasse namens `CYellowEdit` basierend auf `CEdit`.  
  
3.  Hinzufügen von drei Membervariablen zur Ihrer `CYellowEdit` Klasse. Die ersten beiden werden **COLORREF** Variablen, um die Textfarbe und Hintergrundfarbe aufzunehmen. Das dritte werden ein `CBrush` -Objekt, das den Pinsel für den Hintergrund gezeichnet aufnimmt. Die `CBrush` Objekts können Sie den Pinsel, lediglich verwiesen wird, die nach der Erstellung und den Pinsel, der automatisch beim Zerstören der `CYellowEdit` Steuerelement zerstört wird.  
  
4.  Initialisieren Sie die Membervariablen, indem Sie den Konstruktor wie folgt schreiben:  
  
 ```  
    CYellowEdit::CYellowEdit() 
 {  
    m_clrText = RGB(0,
    0,
    0);

    m_clrBkgnd = RGB(255,
    255,
    0);

    m_brBkgnd.CreateSolidBrush(m_clrBkgnd);

 }  
 ```  
  
5.  Mithilfe der Klassen-Assistent, fügen Sie einen Handler für die reflektierte `WM_CTLCOLOR` -Meldung an Ihre `CYellowEdit` Klasse. Beachten Sie, dass das Gleichheitszeichen vor der Nachrichtenname, in der Liste der Nachrichten, die Sie behandeln können, gibt an, dass die Meldung reflektiert wird. Hierzu finden Sie [Definieren eines Meldungshandlers für eine Nachricht reflektiert](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md).  
  
     Klassen-Assistent fügt die folgende meldungszuordnung Makro angehalten und eine Skeleton-Funktion für Sie hinzu:  
  
 ```  
    ON_WM_CTLCOLOR_REFLECT() 
 *// Note: other code will be in between....  
 
    HBRUSH CYellowEdit::CtlColor(CDC* pDC, UINT nCtlColor)   
 { *// TODO: Change any attributes of the DC here  
 *// TODO: Return a non-NULL brush if the *//   parent's handler should not be called  
    return NULL;  
 }  
 ```  
  
6.  Ersetzen Sie den Text der Funktion durch den folgenden Code ein. Dieser Code legt die Textfarbe, die Hintergrundfarbe von Text und die Hintergrundfarbe für den Rest des Steuerelements.  
  
 ```  
    pDC->SetTextColor(m_clrText);
*// text  
    pDC->SetBkColor(m_clrBkgnd);
*// text bkgnd  
    return m_brBkgnd;            // ctl bkgnd  
 ```  
  
7.  Erstellen Sie ein Bearbeitungssteuerelement in einem Dialogfeld, und fügen Sie es mit einer Membervariablen durch Doppelklicken auf das Bearbeitungssteuerelement bei gedrückter STRG-Taste. Klicken Sie im Dialogfeld Hinzufügen von Membervariablen Fertig stellen Sie den Variablennamen ein, und wählen Sie "Control" für die Kategorie, klicken Sie dann "CYellowEdit" für den Variablentyp. Vergessen Sie nicht die Reihenfolge der Registerkarten im Dialogfeld festlegen. Darüber hinaus werden Sie sicherstellen, dass die Headerdatei für die `CYellowEdit` -Steuerelement in der Headerdatei des Dialogfelds.  
  
8.  Erstellen Sie Ihre Anwendung, und führen Sie sie aus. Das Bearbeitungssteuerelement müssen einen gelben Hintergrund.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

