---
title: 'TN021: Befehl und Nachrichtenrouting'
ms.date: 06/28/2018
f1_keywords:
- vc.routing
helpviewer_keywords:
- TN021
- command routing [MFC], technical note TN021
- Windows messages [MFC], routing
ms.assetid: b5952c8b-123e-406c-a36d-a6ac7c6df307
ms.openlocfilehash: ce8aa2013c8f2f351ca1028f0d6103135ba5ecd8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306180"
---
# <a name="tn021-command-and-message-routing"></a>TN021: Befehl und Nachrichtenrouting

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

In diesem Hinweis wird beschrieben, die-routing und Verteilung befehlsarchitektur sowie die erweiterten Themen in fensterverwaltung Nachrichtenrouting.

Finden Sie in Visual C++ für allgemeine Informationen zu den hier beschriebenen Architekturen besonders den Unterschied zwischen Windows-Meldungen, steuerelementbenachrichtigungen und Befehle. In diesem Hinweis wird angenommen, Sie sind vertraut mit den Problemen, die in der gedruckte Dokumentation beschrieben, und nur sehr fortgeschrittenen Themen behandelt.

## <a name="command-routing-and-dispatch-mfc-10-functionality-evolves-to-mfc-20-architecture"></a>Befehlsrouting und Verteilung von MFC 1.0 Funktionalität, die mit MFC 2.0 entwickelt sich Architektur

Windows verfügt über die WM_COMMAND-Meldung, die überlastet ist, um Benachrichtigungen über Befehle des Menüs, Zugriffstasten und dialogsteuerelement Benachrichtigungen zu ermöglichen.

MFC-1.0 erstellt, ein wenig ermöglicht einen Befehlshandler (z. B. "OnFileNew") in einem `CWnd` abgeleitete Klasse, die als Reaktion auf eine bestimmte WM_COMMAND aufgerufen werden. Dies wird zusammen mit der eine Datenstruktur, die die meldungszuordnung geklebt und führt einen Mechanismus sehr platzsparend-Befehl.

MFC-1.0 bereitgestellten auch zusätzliche Funktionen zum Aufteilen von steuerelementbenachrichtigungen von befehlsmeldungen. Befehle werden durch eine 16-Bit-ID, auch bezeichnet als eine Befehls-ID dargestellt. Befehle beginnen normalerweise aus einem `CFrameWnd` (d. h. ein Menü die Option oder eine übersetzte Accelerator) und mit einer Vielzahl von weiteren Fenstern weitergeleitet.

MFC-1.0 verwendet Befehlsrouting in gewisser Hinsicht beschränkt, für die Implementierung der Schnittstelle MDI (Multiple Document). (Ein MDI-Rahmenfenster delegieren Befehle aus, um das aktive untergeordnete MDI-Fenster.)

Diese Funktionalität wurde generalisiert und erweiterte in MFC 2.0-Befehlen durch eine größere Anzahl von Objekten (nicht nur im Fenster) behandelt werden können. Es bietet eine weitere formelle und erweiterbare Architektur für das routing von Nachrichten und wiederverwendet, die Ziel Befehlsrouting für die Behandlung von nicht nur Befehle, sondern auch zum Aktualisieren der UI-Objekte (z. B. Menüelemente und Symbolleistenschaltflächen) entsprechend der aktuelle Verfügbarkeit eines Befehls .

## <a name="command-ids"></a>Befehls-IDs

Eine Erläuterung des Befehls, routing und binding-Prozess finden Sie unter Visual C++. [Technischer Hinweis 20](../mfc/tn020-id-naming-and-numbering-conventions.md) Informationen zur Benennung von ID enthält.

Wir verwenden das generische "ID_"-Präfix für Befehls-IDs. Befehls-IDs sind > = 0 x 8000. Zeile oder den Status die Statusleiste wird der Beschreibungszeichenfolge für den Befehl angezeigt, wenn eine Ressource STRINGTABLE mit den gleichen IDs wie die Befehls-ID vorhanden ist

In den Ressourcen der Anwendung wird Sie ein Befehl aus, die ID kann an mehreren Stellen angezeigt:

- In einer STRINGTABLE-Ressource, die die gleiche ID wie die Nachricht eingabeaufforderungszeile verfügt.

- In möglicherweise viele Menüressourcen, die Menüelemente zugeordnet sind, die den gleichen Befehl aufrufen.

- (Erweitert), in eine Schaltfläche für einen GOSUB-Befehl.

Im Quellcode Ihrer Anwendung wird Sie ein Befehl aus, die ID kann an mehreren Stellen angezeigt:

- In Ihrer Ressource. H (oder anderen Hauptsymbol-Headerdatei) zum Definieren von anwendungsspezifischen Befehls-IDs.

- Z. B. In ein ID-Array verwendet, um eine Symbolleiste erstellen.

- In einem ON_COMMAND-Makro.

- Vielleicht In einer ON_UPDATE_COMMAND_UI-Makro.

Die einzige Implementierung in MFC, die Befehls-IDs erforderlich sind. derzeit werden > = 0 x 8000 ist die Implementierung der GOSUB Dialoge/Befehle.

## <a name="gosub-commands-using-command-architecture-in-dialogs"></a>GOSUB-Befehle, die mit-Befehlsarchitektur in Dialogfeldern

Die befehlsarchitektur von routing und aktivieren die Befehle funktioniert gut mit Rahmenfenster, Menübefehlen, Symbolleisten-Schaltflächen, Dialogleisten-Schaltflächen, andere Schiebeleisten-Steuerelemente und andere Elemente der Benutzeroberfläche entwickelt, um bei Bedarf und Route einschaltbefehle aktualisieren oder Steuerelement-IDs für "Main" ein Befehlsziel (in der Regel das Hauptrahmenfenster). Die Zielplattform Hauptbefehl möglicherweise Befehl oder das Steuerelement Benachrichtigungen an anderen Befehl Zielobjekte entsprechend weiterleiten.

Ein Dialogfeld (gebunden oder ungebunden) profitieren von einer einige der Features der befehlsarchitektur, wenn Sie die entsprechenden Befehls-ID. die Steuerelement-ID, der das Steuerelement des Dialogfelds zuweisen Unterstützung für Dialoge ist nicht automatisch, daher Sie zusätzlichen Code schreiben müssen.

Beachten Sie, dass für alle diese Funktionen ordnungsgemäß funktioniert, den Befehls-IDs müssen > = 0 x 8000. Freigegebene Befehle sollten sein, da viele Dialogfelder, desselben Frames weitergeleitet werden konnten, > = 0 x 8000, während der nicht freigegebene IDCs in einem bestimmten Dialogfeld liegen < = 0x7FFF.

Sie können eine normale Schaltfläche im normalen modales Dialogfeld mit dem IDC der Schaltfläche legen Sie auf der entsprechenden Befehls-ID. platzieren. Wenn der Benutzer die Schaltfläche auswählt, ruft den Besitzer des Dialogfelds (in der Regel das Hauptrahmenfenster) den Befehl genau wie jeder andere-Befehl ab. Dies wird einen Befehl GOSUB bezeichnet, da es in der Regel verwendet wird, um ein weiteres Dialogfeld (im ersten Dialogfeld eine GOSUB) zu öffnen.

Sie können auch die Funktion aufrufen `CWnd::UpdateDialogControls` auf das Dialogfeld, und übergeben sie die Adresse des das Hauptrahmenfenster. Diese Funktion aktivieren oder deaktivieren Ihrem Dialogfeld-Steuerelemente, die basierend darauf, ob sie im Frame Befehlshandler haben. Diese Funktion wird für Sie bei Steuerleisten in Ihrer Anwendung im Leerlauf Schleife automatisch aufgerufen, aber müssen Sie sie aufrufen, direkt für normale Dialoge, die diese Funktion enthalten sein sollen.

## <a name="when-onupdatecommandui-is-called"></a>Wenn ON_UPDATE_COMMAND_UI aufgerufen wird

Verwaltung des aktiviert/überprüft alle eines Programms Menüelemente ständig kann sehr viel rechenleistung beanspruchen problematisch sein. Eine gängige Methode ist zum Aktivieren/Menüelemente Kontrollkästchen nur, wenn der Benutzer das POPUP auswählt. Die MFC-2.0-Implementierung von `CFrameWnd` der WM_INITMENUPOPUP-Nachricht verarbeitet, und der routing-befehlsarchitektur verwendet, um die Zustände des Menüs durch ON_UPDATE_COMMAND_UI-Handler zu bestimmen.

`CFrameWnd` Außerdem behandelt die WM_ENTERIDLE-Nachricht an das aktuelle Menü, das ausgewählte Element auf der Statusleiste (auch bekannt als die Zeile "Message") beschrieben.

Menüstruktur einer Anwendung bearbeitet werden, indem Visual C++, wird verwendet, um die potenzielle WM_INITMENUPOPUP Zeitpunkt verfügbaren Befehle darstellen. ON_UPDATE_COMMAND_UI-Handler können Status oder der Text eines Menüs ändern, oder für die erweiterte verwendet (z. B. der Datei MRU-Liste oder im Popupmenü OLE-Verben), tatsächlich ändern die Menüstruktur, bevor Sie im Menü gezeichnet wird.

Diese Art von ON_UPDATE_COMMAND_UI Verarbeitung erfolgt für Symbolleisten (und anderen Steuerleisten) Wenn die Anwendung die Leerlaufschleife eingibt. Finden Sie unter den *Klassenbibliotheksreferenz* und [technischer Hinweis 31](../mfc/tn031-control-bars.md) für Weitere Informationen zu Schiebeleisten-Steuerelemente.

## <a name="nested-pop-up-menus"></a>Geschachtelte Popupmenüs

Wenn Sie eine geschachtelte Menüstruktur verwenden, bemerken Sie, dass der ON_UPDATE_COMMAND_UI-Handler für das erste Menüelement im Popup-Menü in zwei verschiedenen Fällen aufgerufen wird.

Erstens wird sie für das Popupmenü selbst aufgerufen. Dies ist erforderlich, da Popupmenüs keine IDs, und wir verwenden Sie die ID des ersten Menüelements im des Popupmenüs zum Verweisen auf die gesamte Popup-Menü. In diesem Fall die *M_pSubMenu* Membervariablen von der `CCmdUI` Objekt ist nicht NULL sein und verweist auf das Popup-Menü.

Zweitens wird sie aufgerufen, kurz bevor die Menüelemente im Popupmenü sind zu zeichnende. In diesem Fall die ID verweist nur auf das erste Menüelement und *M_pSubMenu* Membervariablen von der `CCmdUI` Objekt werden auf NULL.

Dies können Sie im Popupmenü, die sich von den Menüelementen zu aktivieren, erfordert jedoch, beachten Sie im Menücode zu schreiben. Z. B. in einem geschachtelten Menü mit der folgenden Struktur:

```Output
File>
    New>
    Sheet (ID_NEW_SHEET)
    Chart (ID_NEW_CHART)
```

Die Befehle ID_NEW_SHEET und ID_NEW_CHART können unabhängig voneinander aktiviert oder deaktiviert werden. Die **neu** im Popupmenü sollte aktiviert werden, wenn eine der beiden aktiviert ist.

Die Befehlshandler für ID_NEW_SHEET (der erste Befehl in das Popupfenster) würde wie folgt aussehen:

```cpp
void CMyApp::OnUpdateNewSheet(CCmdUI* pCmdUI)
{
    if (pCmdUI->m_pSubMenu != NULL)
    {
        // enable entire pop-up for "New" sheet and chart
        BOOL bEnable = m_bCanCreateSheet || m_bCanCreateChart;
        // CCmdUI::Enable is a no-op for this case, so we
        // must do what it would have done.
        pCmdUI->m_pMenu->EnableMenuItem(pCmdUI->m_nIndex,
            MF_BYPOSITION |
            (bEnable  MF_ENABLED : (MF_DISABLED | MF_GRAYED)));

        return;
    }
    // otherwise just the New Sheet command
    pCmdUI->Enable(m_bCanCreateSheet);
}
```

Die Befehlshandler für ID_NEW_CHART wäre eine normale Updateliste Befehlshandler und etwa aussehen:

```cpp
void CMyApp::OnUpdateNewChart(CCmdUI* pCmdUI)
{
    pCmdUI->Enable(m_bCanCreateChart);
}
```

## <a name="oncommand-and-onbnclicked"></a>ON_COMMAND- und ON_BN_CLICKED

Die Meldungszuordnungsmakros für **ON_COMMAND** und **ON_BN_CLICKED** sind identisch. Die MFC-Befehl und Steuerung routing Benachrichtigungsmechanismus verwendet nur die Befehls-ID um zu entscheiden, wo Sie die Weiterleitung an. Steuern der Benachrichtigungen mit Notification Steuercode 0 (null) (**BN_CLICKED**) als Befehle interpretiert werden.

> [!NOTE]
> Der Befehl-handlerkette tatsächlich durchlaufen alle benachrichtigungsmeldungen des Registersteuerelements. Beispielsweise ist es technisch möglich, dass Sie schreiben einen Steuerelement-Benachrichtigungshandler für **EN_CHANGE-Ereignis** in der Dokumentklasse. Dies ist nicht soweit möglich, da die praktischen Anwendungen diese Funktion nur wenige gibt, das Feature von Datensatzfeldern von ClassWizard nicht unterstützt wird und kann die Verwendung der Funktion in unsicherem Code führen.

## <a name="disabling-the-automatic-disabling-of-button-controls"></a>Deaktivieren die automatische Deaktivierung von Schaltflächen-Steuerelemente

Wenn Sie ein Schaltflächen-Steuerelement auf einer Dialogleiste platzieren, oder in einem Dialogfeld, das Verwenden von Where Sie aufrufen **CWnd::UpdateDialogControls** auf Ihren eigenen, Sie werden feststellen, die keine Schaltflächen **ON_COMMAND** oder **ON_UPDATE_COMMAND_UI** Handler werden automatisch für Sie deaktiviert werden, durch das Framework. In einigen Fällen Sie müssen sich nicht um einen Ereignishandler zu erhalten, aber Sie sollten sich auf die Schaltfläche ", der aktiviert bleiben. Die einfachste Möglichkeit hierzu ist einen dummy Befehlshandler (einfach mit der Klassen-Assistent) hinzufügen und keine darin.

## <a name="window-message-routing"></a>Fenster-Nachrichtenweiterleitung

Im folgenden werden einige Themen für fortgeschrittenere Benutzer auf die MFC-Klassen und die Windows-nachrichtenweiterleitung und anderen Themen wie auswirken beschrieben. Die folgenden Informationen werden nur kurz beschrieben. Finden Sie in der *Klassenbibliotheksreferenz* ausführliche Informationen zu öffentlichen APIs. Finden Sie in der Quellcode der MFC-Bibliothek für Weitere Informationen zu den Implementierungsdetails.

Näheres [technischen Hinweis 17](../mfc/tn017-destroying-window-objects.md) für Informationen zur Bereinigung der Fenster, ein sehr wichtiges Thema für alle **CWnd**-abgeleiteten Klassen.

## <a name="cwnd-issues"></a>CWnd-Probleme

Die Memberfunktion für die Implementierung **CWnd:: OnChildNotify** bietet eine leistungsfähige und erweiterbare Architektur für die untergeordneten Fenster (auch bekannt als Steuerelemente) zu verknüpfen, oder andernfalls informiert werden, der Nachrichten, Befehle und -Steuerelement Benachrichtigung, die zu ihrer übergeordneten (oder "Besitzer"). Wenn das untergeordnete Fenster (/ Steuern) ist eine C++ **CWnd** Objekt selbst, die virtuelle Funktion **OnChildNotify** zuerst aufgerufen wird mit den Parametern aus der ursprünglichen Nachricht (d. h. eine **MSG**Struktur). Das untergeordnete Fenster kann die Nachricht so belassen, Kontrolle oder ändern Sie die Nachricht für das übergeordnete Element (selten vorkommenden).

Der Standardwert **CWnd** Implementierung die folgenden Nachrichten verarbeitet und verwendet die **OnChildNotify** Hook, damit das untergeordnete Windows (Steuerelemente) zu den ersten Zugriff auf die Nachricht:

- **WM_MEASUREITEM** und **WM_DRAWITEM** (für Self Zeichnen)

- **WM_COMPAREITEM** und **WM_DELETEITEM** (für Self Zeichnen)

- **WM_HSCROLL** und **WM_VSCROLL**

- **WM_CTLCOLOR**

- **WM_PARENTNOTIFY**

Sie sehen die **OnChildNotify** Hook dient zum Ändern von Ownerdrawn-Nachrichten in Nachrichten selbst zeichnen.

Zusätzlich zu den **OnChildNotify** Hook, Scroll-Nachrichten haben weitere routing Verhalten. Sie finden Sie weiter unten Weitere Informationen über die Bildlaufleisten und Quellen von **WM_HSCROLL** und **WM_VSCROLL** Nachrichten.

## <a name="cframewnd-issues"></a>CFrameWnd-Probleme

Die **CFrameWnd** -Klasse bietet die meisten Befehlsrouting und Benutzeroberflächen-Implementierung wird aktualisiert. Dies wird hauptsächlich für das Hauptrahmenfenster der Anwendung (**CWinApp::m_pMainWnd**) gelten jedoch für alle Rahmenfenster.

Das Hauptrahmenfenster ist das Fenster mit der Menüleiste, und das übergeordnete Element der Statusleiste oder Meldung der Zeile. Finden Sie in der oben genannten Diskussion auf Befehlsrouting und **WM_INITMENUPOPUP.**

Die **CFrameWnd** Klasse ermöglicht die Verwaltung der aktiven Ansicht. Die folgenden Meldungen werden über die aktive Ansicht weitergeleitet:

- Alle Command-Meldungen (die aktive Ansicht erhält ersten Zugriff auf diese).

- **WM_HSCROLL** und **WM_VSCROLL** Nachrichten von nebengeordneten Scrollleisten (siehe unten).

- **WM_ACTIVATE** (und **WM_MDIACTIVATE** für MDI) abrufen in Aufrufe an die virtuelle Funktion aktiviert **CView::OnActivateView**.

## <a name="cmdiframewndcmdichildwnd-issues"></a>CMDIFrameWnd/CMDIChildWnd-Probleme

Beide Klassen für MDI-Rahmenfenster abgeleitet **CFrameWnd** und aus diesem Grund sind beide aktiviert für diese Art von Befehlsrouting und Benutzeroberflächen-Aktualisierung in bereitgestellten **CFrameWnd**. In einer typischen MDI-Anwendung, nur das Hauptrahmenfenster (d. h. die **CMDIFrameWnd** Objekt) enthält, die Menüleiste und die Statusleiste und daher ist die wichtigste Quelle der Befehl-routing-Implementierung.

Das allgemeine routing-Schema ist, dass das aktive untergeordnete MDI-Fenster den ersten Zugriff auf Befehle erhält. Der Standardwert **PreTranslateMessage** -Funktionen behandeln Zugriffstastentabellen für beide untergeordnete MDI-Fenster (ersten) und den MDI-Frame (zweiten) sowie der standard MDI-Systembefehl Zugriffstasten, die normalerweise von behandelt  **TranslateMDISysAccel** (letzten).

## <a name="scroll-bar-issues"></a>Bildlaufleiste-Probleme

Bei der Behandlung des Scroll-Nachricht (**WM_HSCROLL**/**OnHScroll** und/oder **WM_VSCROLL**/**OnVScroll**), sollten Sie versuchen, den Handlercode zu schreiben, damit es nicht abhängig ist, auf, in denen die Scroll-Leiste Nachricht stammt. Dies ist nicht nur allgemeine Windows-Problem, da es sich bei "true" Bildlaufleiste, Steuerelemente oder von Scroll Nachrichten stammen können **WS_HSCROLL**/**WS_VSCROLL** Scrollleisten an, die nicht-Schiebeleisten-Steuerelemente sind.

MFC erweitert ermöglichen für Schiebeleisten-Steuerelemente entweder untergeordnete oder gleichgeordnete Elemente des Fensters wird ein Bildlauf durchgeführt wird (in der Tat die über-/unterordnungsbeziehung zwischen dem Bildlaufleiste angezeigt und im Fenster der Bildlauf ausgeführt kann handeln). Dies ist besonders wichtig für freigegebene Bildlaufleisten mit Splitterfenster. Finden Sie in [technischen Hinweis 29](../mfc/tn029-splitter-windows.md) Details zur Implementierung von **CSplitterWnd** einschließlich weiterer Informationen auf Scroll-Leiste Probleme freigegeben.

Am Rande, es gibt zwei **CWnd** abgeleitete Klassen, in denen die Stile Scroll-Leiste am Erstellungszeit, aufgefangen und nicht an Windows übergeben werden. Bei der Übergabe an eine Routine zum Erstellen von **WS_HSCROLL** und **WS_VSCROLL** können werden unabhängig voneinander festlegen, aber nach der Erstellung nicht geändert werden kann. Natürlich sollten Sie nicht direkt testen, oder legen Sie die Bits WS_SCROLL Stil des Fensters, das sie erstellt.

Für **CMDIFrameWnd** Scroll-Leiste Formatvorlagen übergebenen **erstellen** oder **LoadFrame** verwendet, um die MDICLIENT zu erstellen. Wenn Sie sicher, dass werden einen bildlauffähigen MDICLIENT Bereich (z. B. Windows Programm-Manager) enthalten sein sollen sowohl Bildlaufleisten-Stile (**WS_HSCROLL** &#124; **WS_VSCROLL**) für das Format, das zum Erstellen der **CMDIFrameWnd**.

Für **CSplitterWnd** Scroll-Leiste Formatvorlagen anwenden, auf die speziellen freigegebenen Bildlaufleisten für das Splitter-Regionen. Für statisches Splitterfenster legen Sie normalerweise nicht entweder Standardstil der Statusleiste scrollen. Für dynamische Splitterfenster, in der Regel müssen die Bildlaufleiste festgelegt für die Richtung, die Sie, d. h. teilen **WS_HSCROLL** , wenn Sie Zeilen aufteilen, können **WS_VSCROLL** Wenn Spalten aufgeteilt werden können.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
