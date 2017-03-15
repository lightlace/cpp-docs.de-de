---
title: "TN062: Meldungsreflektion f&#252;r Windows-Steuerelemente | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.controls.messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Meldungsreflexion"
  - "Benachrichtigungsmeldungen"
  - "ON_CONTROL_REFLECT-Makro"
  - "ON_CONTROL_REFLECT_EX-Makro"
  - "ON_NOTIFY-Meldung"
  - "ON_NOTIFY_REFLECT-Meldung"
  - "ON_NOTIFY_REFLECT_EX-Meldung"
  - "ON_UPDATE_COMMAND_UI_REFLECT-Makro"
  - "ON_WM_CHARTOITEM_REFLECT-Makro"
  - "ON_WM_COMPAREITEM_REFLECT-Makro"
  - "ON_WM_CTLCOLOR_REFLECT-Makro"
  - "ON_WM_DELETEITEM_REFLECT-Makro"
  - "ON_WM_DRAWITEM_REFLECT-Makro"
  - "ON_WM_HSCROLL_REFLECT-Makro"
  - "ON_WM_MEASUREITEM_REFLECT-Makro"
  - "ON_WM_PARENTNOTIFY_REFLECT-Makro"
  - "ON_WM_VKEYTOITEM_REFLECT-Makro"
  - "ON_WM_VSCROLL_REFLECT-Makro"
  - "TN062"
  - "WM_COMMAND"
  - "WM_CTLCOLOR-Meldung"
  - "WM_NOTIFY-Meldung"
ms.assetid: 53efb0ba-fcda-4fa0-a3c7-14e0b78fb494
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# TN062: Meldungsreflektion f&#252;r Windows-Steuerelemente
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser technische Hinweis beschreibt Meldungsreflektion, eine neue Funktion in MFC 4.0.  Sie enthält auch Anweisungen für das Erstellen eines einfachen, wiederverwendbaren Steuerelements das Meldungsreflektion verwendet.  
  
 Dieser technische Hinweis nicht Gegenstand Meldungsreflektion, während er auf ActiveX\-Steuerelemente gelten \(zuvor aufgerufen OLE\-Steuerelemente\).  Siehe den Artikel [ActiveX\-Steuerelemente: Erstellen von Unterklassen von einem Windows\-Steuerelements](../mfc/mfc-activex-controls-subclassing-a-windows-control.md).  
  
 **Was ist Meldungs\-Reflektion?**  
  
 Windows\-Steuerelemente senden häufig Benachrichtigungen ihren übergeordneten Fenster.  Beispielsweise senden viele Steuerelemente eine Steuerfarbenbenachrichtigungsmeldung \(`WM_CTLCOLOR` oder einer davon Varianten\) zum übergeordneten Element, um das übergeordnete Element ermöglichen, einen Pinsel zum Zeichnen des Hintergrunds des Steuerelements anzugeben.  
  
 In Windows und in MFC vor Version 4.0, ist das übergeordnete Fenster, oft ein Dialogfeld, für das Behandeln dieser Meldungen zuständig.  Dies bedeutet, dass der Code zur Behandlung, die die Meldung in der Klasse des übergeordneten Fensters sein muss und dass diese in jeder Klasse dupliziert werden muss, die diese Meldung bearbeiten muss.  Im Fall oben, jedes Dialogfeld, dass gewünschte Steuerelemente mit benutzerdefinierten Hintergründen die Steuerfarbenbenachrichtigungsmeldung würden bearbeiten müssen.  Es ist viel einfacher sein, Code wiederverwenden, wenn einer Steuerelementklasse geschrieben werden kann, die die eigene Hintergrundfarbe behandelt.  
  
 In MFC 4.0 arbeitet der alte Mechanismus noch \- übergeordnete Fenster können Benachrichtigungsmeldungen bearbeiten.  Außerdem erleichtert jedoch MFC 4.0 Wiederverwendung, mithilfe einer Funktion bereitstellt, die "Meldungsreflektion" bezeichnet wird, die ermöglicht diese im Fenster des untergeordneten Steuerelements oder im übergeordneten Fenster behandelt werden Benachrichtigungsmeldungen, entweder oder beides.  Im Steuerhintergrundfarbenbeispiel können Sie jetzt eine Steuerelementklasse schreiben, die die eigene Hintergrundfarbe festgelegt wird, indem die reflektierte Meldung `WM_CTLCOLOR` \- Befehl behandelt, ohne auf das übergeordnete Element zu erstellen. \(Beachten Sie, dass, da Meldungsreflektion von MFC, nicht von Windows, die Klasse des übergeordneten Fensters implementiert wird von `CWnd` abgeleitet werden muss, damit Meldungsreflektion.\)  
  
 Frühere Versionen von MFC ausgeführt werden, das zur Meldungsreflektion ähnelt, indem virtuelle Funktionen für einige Meldungen, wie Nachrichten für Ownerdrawnlistenfelder \(`WM_DRAWITEM`, z.\) bereitgestellt haben.  Der neue Meldungsreflektionsmechanismus ist generalisiert und konsistent.  
  
 Meldungsreflektion ist mit dem Code kompatibel, der für Versionen von MFC vor 4.0 geschrieben wird.  
  
 Wenn Sie einen Handler für eine bestimmte Meldung oder einen Bereich von Nachrichten, in der Klasse des übergeordneten Fensters angegeben haben, überschreibt dieser reflektierte Meldungshandler für dieselbe Nachricht stellte Sie aufruft nicht die Basisklassenhandlerfunktion im eigenen Handler.  Wenn Sie `WM_CTLCOLOR` in der Dialogfeldklasse behandeln, überschreibt die Behandlung alle reflektierten Meldungshandler.  
  
 Wenn, in der Klasse des übergeordneten Fensters, Sie einen Handler für eine bestimmte Meldung **WM\_NOTIFY** oder einen Bereich von **WM\_NOTIFY** Meldungen bereitstellen, wird der Handler aufgerufen, wenn das untergeordnete Steuerelement, das diese Nachrichten sendet, einen Meldungshandler reflektierten nicht durch **ON\_NOTIFY\_REFLECT\(\)**.  Wenn Sie **ON\_NOTIFY\_REFLECT\_EX\(\)** in der Meldungszuordnung verwenden, kann möglicherweise der Meldungshandler dem übergeordneten Fenster, um die Meldung zu bearbeiten.  Wenn der Handler **FALSE** zurückgibt, wird das übergeordnete Fenster die Meldung auch bearbeitet, während ein Aufruf, der **TRUE** zurückgibt, das übergeordnete Element nicht zulässig, um sie zu behandeln.  Beachten Sie, dass die reflektierte Meldung vor der Benachrichtigung behandelt wird.  
  
 Wenn **WM\_NOTIFY** eine Meldung gesendet wird, wird das Steuerelement die erste Möglichkeit bereitgestellt, sie zu behandeln.  Wenn einer der anderen reflektierte Meldung gesendet, hat das übergeordnete Fenster die erste Möglichkeit, sie zu behandeln und das Steuerelement empfängt die reflektierte Meldung.  Dazu ist es erforderlich, eine Handlerfunktion und einen entsprechenden Eintrag in der Klassenmeldungszuordnung des Steuerelements.  
  
 Das Meldungszuordnungsmakro für reflektierte Meldungen lautet geringfügig anders als für reguläre Benachrichtigungen: sie hat **\_REFLECT**, das auf den üblichen Namen angefügt wird.  Um beispielsweise **WM\_NOTIFY** eine Meldung im übergeordneten zu bearbeiten, verwenden Sie Makro\- `ON_NOTIFY` in der Meldungszuordnung des übergeordneten Elements.  Um die reflektierte Meldung im untergeordneten Steuerelement zu ändern, verwenden Sie das **ON\_NOTIFY\_REFLECT**\-Makro in der Meldungszuordnung des untergeordneten Steuerelements.  In einigen Fällen sind die Parameter, auch unterschiedlich.  Beachten Sie, dass die den Meldungszuordnungseinträgen für Sie normalerweise hinzufügen und Skelettfunktionsimplementierungen mit korrekten Parametern enthalten kann.  
  
 Siehe [TN061: ON\_NOTIFY\- und WM\_NOTIFY\-Meldungen](../mfc/tn061-on-notify-and-wm-notify-messages.md) für Informationen über die neue **WM\_NOTIFY** Meldung.  
  
 **Meldungszuordnungseinträge und Handlerfunktions\-Prototypen für reflektierte Meldungen**  
  
 Um eine reflektierte Steuerelementbenachrichtigungsmeldung bearbeiten, verwenden Sie die Meldungszuordnungsmakros und die Funktionsprototypen, die in der nachfolgenden Tabelle aufgeführt werden.  
  
 Der Klassen\-Assistent kann diesen Meldungszuordnungseinträgen für Sie normalerweise hinzufügen und Skelettfunktionsimplementierungen bereitstellen.  Siehe [Definieren eines Meldungshandlers für eine reflektierte Meldung](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md) zu Informationen darüber, wie Handler für reflektierte Meldungen definiert.  
  
 Um vom Meldungsnamen zu reflektierten Makronamen zu konvertieren, müssen Sie **ON\_** ruhig fügen Sie **\_REFLECT** an.  `WM_CTLCOLOR` wird beispielsweise **ON\_WM\_CTLCOLOR\_REFLECT**. \(Weitere finden, welche Meldungen wiedergegeben werden können, führen Sie die gegenüberliegende Konvertierung auf den Makroeinträgen in der Tabelle weiter unten.\)  
  
 Die drei Ausnahmen zur Regel oben sind, wie folgt:  
  
-   Das Makro für **WM\_COMMAND** Benachrichtigungen ist **ON\_CONTROL\_REFLECT**.  
  
-   Das Makro für **WM\_NOTIFY** Reflektionen ist **ON\_NOTIFY\_REFLECT**.  
  
-   Das Makro für `ON_UPDATE_COMMAND_UI` Reflektionen ist **ON\_UPDATE\_COMMAND\_UI\_REFLECT**.  
  
 In jedem der obigen Sonderfälle, müssen Sie den Namen der Handlermemberfunktion angeben.  In den anderen Fällen müssen Sie den Standardnamen für die Handlerfunktion verwenden.  
  
 Die Bedeutung der Parameter und die Rückgabewerte der Funktionen werden mit entweder dem Funktionsnamen oder dokumentiert, der Funktionsname mit **Ein** repräsentierte voran.  Beispielsweise wird **CtlColor** in `OnCtlColor` dokumentiert.  Einige reflektierte Meldungshandler benötigen weniger Parameter als ähnliche Handler in ein übergeordnetes Fenster.  Beheben Sie einfach die Namen in der Tabelle unten mit den Namen der formalen Parameter in der Dokumentation ab.  
  
|Zuordnungseintrag|Funktionsprototyp|  
|-----------------------|-----------------------|  
|**ON\_CONTROL\_REFLECT\(**  `wNotifyCode` **,**  `memberFxn`  **\)**|**afx\_msg void**  `memberFxn`  **\( \);**|  
|**ON\_NOTIFY\_REFLECT\(**  `wNotifyCode` **,**  `memberFxn`  **\)**|*Ergebnis*  **\); afx\_msg void**  `memberFxn`  **\( NMHDR \***  `pNotifyStruct` **, LRESULT\***|  
|**ON\_UPDATE\_COMMAND\_UI\_REFLECT\(**  `memberFxn`  **\)**|**afx\_msg void**  `memberFxn`  **\( CCmdUI\***  `pCmdUI`  **\);**|  
|**ON\_WM\_CTLCOLOR\_REFLECT\(\)**|**afx\_msg HBRUSH CtlColor \( CDC\***  `pDC` **, UINT**  `nCtlColor`  **\);**|  
|**ON\_WM\_DRAWITEM\_REFLECT\(\)**|**afx\_msg void DrawItem \( LPDRAWITEMSTRUCT**  `lpDrawItemStruct`  **\);**|  
|**ON\_WM\_MEASUREITEM\_REFLECT\(\)**|**afx\_msg void MeasureItem \( LPMEASUREITEMSTRUCT**  `lpMeasureItemStruct`  **\);**|  
|**ON\_WM\_DELETEITEM\_REFLECT\(\)**|**afx\_msg void DeleteItem \( LPDELETEITEMSTRUCT**  `lpDeleteItemStruct`  **\);**|  
|**ON\_WM\_COMPAREITEM\_REFLECT\(\)**|**afx\_msg int CompareItem \( LPCOMPAREITEMSTRUCT**  `lpCompareItemStruct`  **\);**|  
|**ON\_WM\_CHARTOITEM\_REFLECT\(\)**|**afx\_msg int CharToItem \( UINT**  `nKey` **, UINT**  `nIndex`  **\);**|  
|**ON\_WM\_VKEYTOITEM\_REFLECT\(\)**|**afx\_msg int VKeyToItem \( UINT**  `nKey` **, UINT**  `nIndex`  **\);**|  
|**ON\_WM\_HSCROLL\_REFLECT\(\)**|**afx\_msg void HScroll \( UINT**  `nSBCode` **, UINT**  `nPos`  **\);**|  
|**ON\_WM\_VSCROLL\_REFLECT\(\)**|**afx\_msg void VScroll \( UINT**  `nSBCode` **, UINT**  `nPos`  **\);**|  
|**ON\_WM\_PARENTNOTIFY\_REFLECT\(\)**|**afx\_msg void ParentNotify \( UINT**  `message` **, LPARAM**  `lParam`  **\);**|  
  
 Die Makros **ON\_NOTIFY\_REFLECT** und **ON\_CONTROL\_REFLECT** über Variationen, die mehrere Objekte \(wie das Steuerelement und die übergeordnete\) ermöglichen eine bestimmte Meldung zu bearbeiten.  
  
|Zuordnungseintrag|Funktionsprototyp|  
|-----------------------|-----------------------|  
|**ON\_NOTIFY\_REFLECT\_EX\(**  `wNotifyCode` **,**  `memberFxn`  **\)**|*Ergebnis*  **\); afx\_msg BOOL**  `memberFxn`  **\( NMHDR \***  `pNotifyStruct` **, LRESULT\***|  
|**ON\_CONTROL\_REFLECT\_EX\(**  `wNotifyCode` **,**  `memberFxn`  **\)**|**afx\_msg BOOL**  `memberFxn`  **\( \);**|  
  
## Behandeln von reflektierten Meldungen: Ein Beispiel eines wiederverwendbaren Steuerelements  
 Dieses einfache Beispiel erstellt ein wiederverwendbares Steuerelement, das `CYellowEdit`.  Das Steuerelement funktioniert genauso wie ein reguläres Bearbeitungssteuerelement, es veranschaulicht schwarzen Text auf einem gelben Hintergrund angezeigt.  Es würde einfach sein, Memberfunktionen hinzuzufügen, die das `CYellowEdit`\-Steuerelement von verschiedenen Farben der Anzeige ermöglichen würden.  
  
#### Um das Beispiel versuchen, das eines wiederverwendbaren Steuerelements erstellt  
  
1.  Erstellen Sie ein neues Dialogfeld in einer vorhandenen Anwendung.  Weitere Informationen finden Sie im Thema [Dialog\-Editor](../mfc/dialog-editor.md).  
  
     Sie müssen eine Anwendung verfügen, in der das wiederverwendbare Steuerelement entwickeln.  Falls keine vorhandene Anwendung zu verwenden ist, erstellen Sie eine auf Dialogfeldern basierende Anwendung mithilfe des Anwendungs\-Assistenten.  
  
2.  Wenn das Projekt in Visual C\+\+ geladen wurde, verwenden Sie die eine neue Klasse, zu erstellen, die `CYellowEdit` auf `CEdit` aufgerufen wird.  
  
3.  Fügen Sie CMMI\-Familie Variablen der `CYellowEdit`\-Klasse hinzu.  Die ersten beiden sind **COLORREF**\-Variablen, z der Textfarbe und der Hintergrundfarbe aufzunehmen.  Das dritte ist ein `CBrush`\-Objekt, das den Pinsel für das Zeichnen des Hintergrunds enthält.  Das `CBrush`\-Objekt ermöglicht es Ihnen, den Pinsel einmal erstellen und lediglich verweist ihn nach dem, und der Pinsel automatisch zerstören, wenn das `CYellowEdit`\-Steuerelement zerstört wird.  
  
4.  Initialisieren Sie die Membervariablen, indem Sie den Konstruktor schreiben, wie folgt:  
  
    ```  
    CYellowEdit::CYellowEdit()  
    {  
       m_clrText = RGB( 0, 0, 0 );  
       m_clrBkgnd = RGB( 255, 255, 0 );  
       m_brBkgnd.CreateSolidBrush( m_clrBkgnd );  
    }  
    ```  
  
5.  Verwenden des Klassen\-Assistenten fügen Sie Handler für reflektierte Meldung die `WM_CTLCOLOR` der Klasse `CYellowEdit` hinzu.  Beachten Sie, dass das Gleichheitszeichen vor dem Meldungsnamen in der Liste der Meldungen, die Sie bearbeiten können, angibt, dass die Meldung angezeigt wird.  Dies wird in [Definieren eines Meldungshandlers für eine reflektierte Meldung](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md) beschrieben.  
  
     Der Klassen\-Assistent fügt die folgenden Meldungszuordnungsmakro\- und \-Skelettfunktion für Sie hinzu:  
  
    ```  
    ON_WM_CTLCOLOR_REFLECT()  
  
    // Note: other code will be in between....  
  
    HBRUSH CYellowEdit::CtlColor(CDC* pDC, UINT nCtlColor)   
    {  
       // TODO: Change any attributes of the DC here  
  
       // TODO: Return a non-NULL brush if the  
       //   parent's handler should not be called  
       return NULL;  
    }  
    ```  
  
6.  Ersetzen Sie den Text der Funktion durch den folgenden Code.  Der Code gibt der Textfarbe, der Texthintergrundfarbe und der Hintergrundfarbe für Rest des Steuerelements an.  
  
    ```  
    pDC->SetTextColor( m_clrText );   // text  
    pDC->SetBkColor( m_clrBkgnd );   // text bkgnd  
    return m_brBkgnd;            // ctl bkgnd  
    ```  
  
7.  Erstellen Sie ein Bearbeitungssteuerelement im Dialogfeld, fügen Sie es in eine Membervariable an, durch Doppelklicken auf das Bearbeitungssteuerelement der um eine Steuertaste nach unten beibehalten.  Im Hinzufügens\-Membervariablendialogfeld beenden Sie den Variablennamen und wählen Sie "Steuerelement" für die Kategorie, dann "CYellowEdit" für den Variablentyp aus.  Vergessen Sie nicht, die Aktivierreihenfolge im Dialogfeld festlegen.  Außerdem sollten Sie sicher, dass die Headerdatei für das `CYellowEdit`\-Steuerelement in der Headerdatei des Dialogfelds.  
  
8.  Erstellen Sie Ihre Anwendung, und führen Sie sie aus.  Das Bearbeitungssteuerelement hat einen gelben Hintergrund.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)