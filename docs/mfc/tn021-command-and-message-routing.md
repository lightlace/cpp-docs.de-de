---
title: 'TN021: Befehls- und Meldungsrouting | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.routing
dev_langs: C++
helpviewer_keywords:
- TN021
- command routing [MFC], technical note TN021
- Windows messages [MFC], routing
ms.assetid: b5952c8b-123e-406c-a36d-a6ac7c6df307
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1854be249db91257228e6dab70fc7ff2f50664ce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tn021-command-and-message-routing"></a>TN021: Befehls- und Meldungsrouting
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis beschreibt Befehl routing und Dispatch-Architektur sowie erweiterte Themen fensterverwaltung Nachrichtenrouting.  
  
 Details finden Sie in Visual c++ Allgemein auf die hier beschriebenen Architekturen insbesondere den Unterschied zwischen Windows-Meldungen, steuerelementbenachrichtigungen und Befehle. Dieser Hinweis wird davon ausgegangen werden, mit der in der Dokumentation beschriebenen Probleme sehr vertraut sind und nur sehr Erweiterte Themen behandelt.  
  
## <a name="command-routing-and-dispatch-mfc-10-functionality-evolves-to-mfc-20-architecture"></a>Befehlsrouting und Verteilung MFC 1.0 Funktionalität weiterentwickelt mit MFC 2.0 Architektur  
 Windows verfügt über die **WM_COMMAND** Meldung, die überladen ist, sodass Benachrichtigungen über Menübefehle, Zugriffstasten und dialogsteuerelement Benachrichtigungen sind.  
  
 MFC-1.0 basiert auf, die etwas Befehlshandler (z. B. "OnFileNew") können einer **CWnd** abgeleitete Klasse, um als Antwort auf eine bestimmte aufgerufen **WM_COMMAND**. Dies wird zusammen mit der eine Datenstruktur, die die meldungszuordnung geklebt und führt einen Befehl sehr platzsparend-Mechanismus.  
  
 MFC-1.0 bereitgestellten auch zusätzliche Funktionen zur Trennung von steuerelementbenachrichtigungen von befehlsmeldungen. Befehle werden durch eine 16-Bit-ID, auch bezeichnet als eine Befehls-ID dargestellt. Befehle beginnen normalerweise aus einer **CFrameWnd** (d. h. ein Menü die Option oder eine übersetzte Zugriffstaste) und mit einer Vielzahl von anderen Fenstern geleitet.  
  
 MFC-1.0 verwendet Befehlsrouting beschränkt, wie für die Implementierung von dem Arbeitsspeicher (MDI, Multiple Document Interface). (Ein MDI-Rahmenfenster delegieren Befehle an das aktive untergeordnete MDI-Fenster.)  
  
 Diese Funktionalität wurde generalisiert und erweiterte in MFC 2.0 Befehle durch eine größere Anzahl an Objekten (nicht nur im Fenster) bearbeitet werden können. Er bietet eine weitere Formal und erweiterbare Architektur für das routing von Nachrichten und wiederverwendet, die Ziel Befehlsrouting zum Behandeln von nicht nur von Befehlen, sondern auch zum Aktualisieren von UI-Objekte (z. B. Menüelemente und Symbolleisten-Schaltflächen) entsprechend der aktuelle Verfügbarkeit eines Befehls .  
  
## <a name="command-ids"></a>Befehls-IDs  
 Eine Erläuterung des Befehls routing und binding-Prozess finden Sie in Visual C++. [Technischer Hinweis 20](../mfc/tn020-id-naming-and-numbering-conventions.md) enthält Informationen zum Benennen von ID.  
  
 Wir verwenden die generische Präfix "ID_" für die Befehls-IDs. Befehls-IDs sind > = 0 x 8000. Zeile oder den Status die Statusleiste wird der Befehlszeichenfolge-Beschreibung angezeigt, wenn es sich bei besteht eine STRINGTABLE-Ressource mit der gleichen IDs wie die Befehls-ID.  
  
 Angezeigt wird in den Ressourcen Ihrer Anwendung ein Befehl, den ID kann an mehreren Stellen:  
  
-   In einer STRINGTABLE-Ressource, die die gleiche ID wie die Nachricht Eingabeaufforderung aufweist.  
  
-   In der möglicherweise viele Menüressourcen, die auf Menüelemente verbunden sind, die den gleichen Befehl aufrufen.  
  
-   (Erweitert) in eine Schaltfläche für einen GOSUB-Befehl.  
  
 Angezeigt wird im Quellcode Ihrer Anwendung ein Befehl, den ID kann an mehreren Stellen:  
  
-   In Ihrer Ressource. H (oder anderen Hauptsymbol-Headerdatei) zum Definieren von anwendungsspezifischen Befehls-IDs.  
  
-   Vielleicht In einem ID-Array, das zum Erstellen einer Symbolleiste verwendet.  
  
-   In einer **ON_COMMAND** Makro.  
  
-   Vielleicht In einem **ON_UPDATE_COMMAND_UI** Makro.  
  
 Derzeit ist die einzige Implementierung in MFC, die Befehls-IDs erfordert werden > = 0 x 8000 ist die Implementierung der GOSUB Dialoge/Befehle.  
  
## <a name="gosub-commands-using-command-architecture-in-dialogs"></a>GOSUB-Befehle, die mit-Befehlsarchitektur in Dialogfeldern  
 Die befehlsarchitektur von routing und aktivieren die Befehle funktioniert gut mit Rahmenfenster, Menüelemente, Symbolleisten-Schaltflächen, Dialogleisten-Schaltflächen, Steuerleisten und andere Benutzeroberflächenelemente entwickelt, um bei Bedarf und die Routenwerte Befehle aktualisieren oder Steuerelement-IDs für "Main" ein Befehlsziel (in der Regel das Hauptrahmenfenster). Dieser main Befehlsziel möglicherweise die Benachrichtigungen Befehl oder das Steuerelement auf anderen Befehl Zielobjekte entsprechend weiterleiten.  
  
 Ein Dialogfeld (gebunden oder ungebunden) profitieren von einer einige der Funktionen der befehlsarchitektur, wenn Sie die entsprechenden Befehls-ID. die Steuerelement-ID des Steuerelements Dialogfeld zuweisen Unterstützung für Dialoge wird nicht automatisch, daher Sie zusätzlichen Code schreiben müssen.  
  
 Beachten Sie, dass für alle diese Funktionen ordnungsgemäß funktioniert, die Befehls-IDs werden sollte > = 0 x 8000. Da zahlreiche Dialoge an desselben Frames weitergeleitet werden konnten, werden freigegebene Befehle sollte > = 0 x 8000, während der nicht freigegebene IDCs in einem bestimmten Dialogfeld werden soll < = 0x7FFF.  
  
 Sie können eine normale Schaltfläche in einem normalen modales Dialogfeld mit der IDC neben der Schaltfläche festlegen, um die entsprechenden Befehls-ID. platzieren. Wenn der Benutzer die Schaltfläche auswählt, ruft den Besitzer des Dialogfelds (in der Regel das Hauptrahmenfenster) den Befehl genau wie alle anderen Befehl ab. Dies wird als GOSUB-Befehl bezeichnet, da es in der Regel verwendet wird, um ein weiteres Dialogfeld (eine GOSUB der das erste Dialogfeld ") zu öffnen.  
  
 Sie können auch die Funktion aufrufen **CWnd::UpdateDialogControls** auf Ihr Dialogfeld, und übergeben sie die Adresse eines Ihrer Hauptrahmenfenster. Diese Funktion wird aktivieren oder Deaktivieren der Dialogfeld-Steuerelemente, die basierend darauf, ob sie im Frame Befehlshandler haben. Diese Funktion wird für Sie automatisch aufgerufen, bei Steuerleisten in Ihrer Anwendung Leerlaufschleife, jedoch müssen Sie es für normale Dialoge, die diese Funktion aufweisen sollen direkt aufrufen.  
  
## <a name="when-onupdatecommandui-is-called"></a>Wenn ON_UPDATE_COMMAND_UI aufgerufen wird  
 Verwalten den Zustand aktiviert/überprüft der Menüelemente eines Programms ständig kann eine rechenintensive Problem darstellen. Ein gängiges Verfahren ist zum Aktivieren/Menüelemente Kontrollkästchen nur, wenn der Benutzer das POPUP auswählt. Die MFC-2.0-Implementierung von **CFrameWnd** behandelt die **WM_INITMENUPOPUP** Nachricht und der routing-befehlsarchitektur verwendet, um zu bestimmen, die Zustände von Menüs, die über **ON_UPDATE_COMMAND_ UI** Handler.  
  
 **CFrameWnd** verarbeitet auch die **WM_ENTERIDLE** Nachricht im aktuelle Menü ausgewählten Elements auf der Statusleiste (auch bekannt als die Nachricht Zeile) beschreiben.  
  
 Menüstruktur einer Anwendung, die von Visual C++ bearbeitet wird verwendet, um die potenziellen Befehle unter darstellen **WM_INITMENUPOPUP** Zeit. **ON_UPDATE_COMMAND_UI** Handler können ändern, das Bundesland oder den Text eines Menüs oder im Menü für erweiterten verwendet (z. B. der Datei MRU-Liste oder das Menü das Popupmenü OLE-Verben) tatsächlich ändern die Menüstruktur vor gezeichnet wird.  
  
 Dem Sortieren des **ON_UPDATE_COMMAND_UI** Verarbeitung erfolgt für Symbolleisten (und anderen Steuerleisten) Wenn die Anwendung die Leerlaufschleife eingibt. Finden Sie unter der *Klassenbibliotheksreferenz* und [technischer Hinweis 31](../mfc/tn031-control-bars.md) für Weitere Informationen zu Schiebeleisten-Steuerelemente.  
  
## <a name="nested-pop-up-menus"></a>Geschachtelte Popupmenüs  
 Wenn Sie eine geschachtelte Menüstruktur verwenden, werden Sie feststellen, dass die **ON_UPDATE_COMMAND_UI** Handler für das erste Menüelement im Popupmenü in zwei verschiedenen Fällen aufgerufen wird.  
  
 Es wird zuerst für das Menü das Popupmenü selbst aufgerufen. Dies ist erforderlich, da Popupmenüs keine IDs und wir die ID des ersten Menüelements im das Popupmenü zum Verweisen auf die gesamte Popupmenü verwenden. In diesem Fall die **M_pSubMenu** Membervariable der der **CCmdUI** Objekt nicht NULL und verweist auf das Menü das Popupmenü.  
  
 Zweitens wird sie aufgerufen, kurz bevor die Menüelemente im Popupmenü sind, gezeichnet werden soll. In diesem Fall die ID verweist nur auf das erste Menüelement und **M_pSubMenu** Membervariable der der **CCmdUI** Objekt werden auf NULL.  
  
 Dies ermöglicht es Ihnen so aktivieren Sie das Menü das Popupmenü die Menüelemente unterscheiden, erfordert jedoch, beachten Sie im Menücode zu schreiben. Beispielsweise ist in einer geschachtelten Menüs mit der folgenden Struktur:  
  
```  
File>  
    New> 
    Sheet (ID_NEW_SHEET)  
    Chart (ID_NEW_CHART)  
```  
  
 Die Befehle ID_NEW_SHEET und ID_NEW_CHART können unabhängig voneinander aktiviert oder deaktiviert werden. Die **neu** Popupmenü sollte aktiviert werden, wenn eine der beiden aktiviert ist.  
  
 Befehlshandler für ID_NEW_SHEET (mit dem ersten Befehl im Popupfenster) würde wie folgt aussehen:  
  
```  
void CMyApp::OnUpdateNewSheet(CCmdUI* pCmdUI)  
{  
    if (pCmdUI->m_pSubMenu != NULL)  
 { *// enable entire pop-up for "New" sheet and chart  
    BOOL bEnable = m_bCanCreateSheet || m_bCanCreateChart;  
 *// CCmdUI::Enable is a no-op for this case,
    so we *//   must do what it would have done.  
    pCmdUI->m_pMenu->EnableMenuItem(pCmdUI->m_nIndex, 
    MF_BYPOSITION |   
 (bEnable  MF_ENABLED : (MF_DISABLED | MF_GRAYED)));

    return; 
 } *// otherwise just the New Sheet command  
    pCmdUI->Enable(m_bCanCreateSheet);

} 
```  
  
 Befehlshandler für ID_NEW_CHART wäre eine normale Updateliste Befehlshandler und etwa Folgendes aussehen:  
  
```  
void CMyApp::OnUpdateNewChart(CCmdUI* pCmdUI)  
{  
    pCmdUI->Enable(m_bCanCreateChart);

} 
```  
  
## <a name="oncommand-and-onbnclicked"></a>ON_COMMAND- und ON_BN_CLICKED  
 Die Meldungszuordnungsmakros für **ON_COMMAND** und **ON_BN_CLICKED** sind identisch. Die MFC-Befehl und routing Benachrichtigungsmechanismus verwendet nur die Befehls-ID um zu entscheiden, wo Sie die Weiterleitung an. Steuern von Benachrichtigungen mit Notification Steuerungscode 0 (null) (**BN_CLICKED**) werden als Befehle interpretiert.  
  
> [!NOTE]
>  Der Handler Befehlskette tatsächlich durchlaufen alle benachrichtigungsmeldungen des Registersteuerelements. Beispielsweise ist es technisch möglich, dass Sie eine Benachrichtigung Steuerelementhandler für schreiben **EN_CHANGE** in Ihr Dokumentklasse. Dies ist nicht in der Regel empfehlenswert, da die praktische Anwendungsfälle dieser Funktion einige werden der Funktion von ClassWizard nicht unterstützt wird und zerbrechliche Code kann die Verwendung der Funktion führen.  
  
## <a name="disabling-the-automatic-disabling-of-button-controls"></a>Deaktiviert die automatische Deaktivierung von Schaltflächen-Steuerelemente  
 Wenn Sie ein Button-Steuerelement auf einer Dialogleiste platzieren oder in einem Dialog mit Where Aufrufen **CWnd::UpdateDialogControls** auf Ihren eigenen, Sie werden bemerken, die keine Schaltflächen **ON_COMMAND** oder **ON_UPDATE_COMMAND_UI** Handler werden automatisch für Sie deaktiviert werden, durch das Framework. In einigen Fällen müssen nicht über einen Handler verfügen, aber Sie werden die Schaltfläche aktiviert bleiben soll. Die einfachste Möglichkeit, dies zu erreichen ist einen dummy Befehlshandler (erleichtert, mit dem Klassen-Assistent) hinzufügen und keine darin.  
  
## <a name="window-message-routing"></a>Fenster Nachrichtenrouting  
 Nachfolgend wird beschrieben, einige erweiterten Themen auf die MFC-Klassen und Nachrichtenrouting Windows und andere Themen wie auswirken. Die hier aufgeführten Informationen werden nur kurz beschrieben. Finden Sie in der *Klassenbibliotheksreferenz* ausführliche Informationen zu öffentlichen APIs. Finden Sie in der MFC-Bibliothekscodes Quelle für Weitere Informationen zu Implementierungsdetails.  
  
 Finden Sie unter [technischen Hinweis 17](../mfc/tn017-destroying-window-objects.md) für Details beim Cleanup der Fenster, ein sehr wichtiger Thema für alle **CWnd**-abgeleitete Klassen.  
  
## <a name="cwnd-issues"></a>CWnd-Probleme  
 Die Memberfunktion Implementierung **CWnd:: OnChildNotify** bietet eine leistungsstarke und erweiterbare Architektur für untergeordnete Fenster (auch bekannt als Steuerelemente) zu verknüpfen, oder andernfalls informiert werden, der Nachrichten, Befehle und Kontrolle Benachrichtigungen, die zu ihrer übergeordneten (oder "Besitzer") zu wechseln. Wenn das untergeordnete Fenster (/ Steuern) ist ein C++ **CWnd** Objekt selbst, die virtuelle Funktion **OnChildNotify** wird zuerst aus der ursprünglichen Nachricht mit den Parametern aufgerufen (d. h. eine **MSG**Struktur). Das untergeordnete Fenster kann belassen die Nachricht, es Essen oder ändern Sie die Nachricht für das übergeordnete Element (selten).  
  
 Die Standardeinstellung **CWnd** Implementierung die folgenden Nachrichten verarbeitet und verwendet die **OnChildNotify** Hook untergeordneten Fenster (Steuerelemente) zum ersten Zugriff auf die Nachricht zulassen:  
  
- **WM_MEASUREITEM** und **WM_DRAWITEM** (selbst zeichnen)  
  
- **WM_COMPAREITEM** und **WM_DELETEITEM** (selbst zeichnen)  
  
- **WM_HSCROLL** und **WM_VSCROLL**  
  
- **WM_CTLCOLOR**  
  
- **WM_PARENTNOTIFY**  
  
 Beachten Sie die **OnChildNotify** Hook dient zum Ändern von Ownerdrawn-Nachrichten in Nachrichten selbst zeichnen.  
  
 Zusätzlich zu den **OnChildNotify** Hook, Scroll-Nachrichten besitzen weiteren Weiterleitung Verhalten. Nachstehen finden weitere Informationen über Bildlaufleisten und Quellen von Sie **WM_HSCROLL** und **WM_VSCROLL** Nachrichten.  
  
## <a name="cframewnd-issues"></a>CFrameWnd-Probleme  
 Die **CFrameWnd** -Klasse bietet die meisten Befehlsrouting und Benutzeroberflächen-Implementierung zu aktualisieren. Dies wird hauptsächlich für das Hauptrahmenfenster der Anwendung (**CWinApp::m_pMainWnd**) gilt jedoch für alle Frame-Fensters.  
  
 Das Hauptrahmenfenster ist das Fenster mit der Menüleiste und ist das übergeordnete Element der Statusleiste oder Nachricht Zeile. Finden Sie in der oben genannten Diskussion auf Befehlsrouting und **WM_INITMENUPOPUP.**  
  
 Die **CFrameWnd** Klasse ermöglicht die Verwaltung der aktiven Ansicht. Die folgenden Meldungen werden über die aktive Ansicht weitergeleitet:  
  
-   Alle befehlsmeldungen (die aktive Ansicht ruft zuerst den Zugriff darauf).  
  
- **WM_HSCROLL** und **WM_VSCROLL** Nachrichten von nebengeordnete-Bildlaufleisten (siehe unten).  
  
- **WM_ACTIVATE** (und **WM_MDIACTIVATE** für MDI) abrufen in Aufrufe an die virtuelle Funktion umgewandelt **CView::OnActivateView**.  
  
## <a name="cmdiframewndcmdichildwnd-issues"></a>CMDIFrameWnd/CMDIChildWnd Probleme  
 Beide Klassen für MDI-Rahmenfenster abgeleitet **CFrameWnd** und in bereitgestellte Benutzeroberfläche zu aktualisieren und aus diesem Grund sind beide aktiviert für diese Art von Befehlsrouting **CFrameWnd**. In einer typischen MDI-Anwendung nur das Hauptrahmenfenster (d. h. die **CMDIFrameWnd** Objekt) enthält die Menüleiste und die Statusleiste und aus diesem Grund ist die Hauptquelle der Befehl routing-Implementierung.  
  
 Das allgemeine routing Schema ist, dass die aktiven untergeordneten MDI-Fensters ersten Zugriff auf Befehle erhält. Die Standardeinstellung **PreTranslateMessage** -Funktionen behandeln Zugriffstastentabellen für beide untergeordnete MDI-Fenster (ersten) und den Frame MDI (zweiten) sowie die standard MDI-System-Befehl Zugriffstasten, die normalerweise von behandelt  **TranslateMDISysAccel** (last).  
  
## <a name="scroll-bar-issues"></a>Bildlaufleiste-Probleme  
 Wenn Scroll-Nachrichtenbehandlung (**WM_HSCROLL**/**OnHScroll** und/oder **WM_VSCROLL**/**OnVScroll**), sollten Sie versuchen, den Handlercode zu schreiben, damit er nicht abhängig ist, wird auf, in denen die Scroll Bar Nachricht stammt. Dies ist nicht nur allgemeine Windows-Problem, da es sich bei "true" Bildlaufleiste Steuerelemente oder aus Rollen Nachrichten stammen können **WS_HSCROLL**/**WS_VSCROLL** Bildlaufleisten, die nicht Bildlaufleisten-Steuerelementen sind.  
  
 MFC erweitert, um die Bildlaufleisten-Steuerelementen als untergeordnete oder gleichgeordnete Elemente des Fensters wird durch einen Bildlauf zu ermöglichen (in der Tat die über-/unterordnungsbeziehung zwischen dem Bildlaufleiste und das Fenster wird durch einen Bildlauf kann alles sein). Dies ist besonders wichtig für freigegebene Bildlaufleisten mit Splitterfenster. Finden Sie unter [technischen Hinweis 29](../mfc/tn029-splitter-windows.md) Details zur Implementierung **CSplitterWnd** einschließlich der Informationen auf Scroll Bar Probleme freigegeben.  
  
 Seite betrachtet, es gibt zwei **CWnd** abgeleitete Klassen, in denen die Stile Scroll-Leiste am Erstellungszeit, aufgefangen und nicht an Windows übergeben werden. Bei der Übergabe an eine Routine zum Erstellen von **WS_HSCROLL** und **WS_VSCROLL** können werden unabhängig voneinander festlegen, aber nach Erstellung nicht geändert werden kann. Natürlich sollten Sie nicht direkt testen, und legen Sie die Bits des WS_SCROLL-Stil des Fensters, die sie erstellt.  
  
 Für **CMDIFrameWnd** Scroll Bar Formatvorlagen übergebenen **erstellen** oder **LoadFrame** werden verwendet, um die MDICLIENT zu erstellen. Wenn Sie sicher, dass werden einen bildlauffähigen MDICLIENT Bereich (z. B. Windows Programm-Manager) aufweisen sollen beide Bildlaufleisten-Stile (**WS_HSCROLL** &#124; **WS_VSCROLL**) für das Format, das zum Erstellen der **CMDIFrameWnd**.  
  
 Für **CSplitterWnd** Scroll Bar Formatvorlagen gelten, für die spezielle freigegebene Bildlaufleisten für die Regionen Splitter. Für statisches Splitterfenster wird normalerweise nicht entweder Balkenart Scroll festgelegt werden. Für dynamische Splitterfenster, in der Regel müssen die Bildlaufleiste festgelegt für die Richtung, die Sie, d. h. teilen **WS_HSCROLL** , wenn Sie Zeilen teilen können **WS_VSCROLL** Wenn Spalten zu unterteilen.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

