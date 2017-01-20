---
title: "TN021: Befehls- und Meldungsrouting"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.routing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Befehlsrouting [C++], Technische Hinweise zu TN021"
  - "TN021"
  - "Windows-Nachrichten [C++], Routing"
ms.assetid: b5952c8b-123e-406c-a36d-a6ac7c6df307
caps.latest.revision: 12
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# TN021: Befehls- und Meldungsrouting
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis beschreibt die Befehlsrouting\- und \-Dispatcharchitektur sowie die erweiterten Themen in der allgemeinen FensterMeldungslenkung.  
  
 Einzelheiten erfahren Sie im Visual C\+\+ für allgemeine Informationen zu den Architekturen an, hier, die besonders die Unterschiede Windows\-Meldungen, Steuerelementbenachrichtigungen und Befehle beschrieben werden.  Dieser Hinweis wird vorausgesetzt, dass Sie mit den Problemen sehr vertraut sind, die in der Dokumentation und erweiterten gedruckten nur Themen der Adressen sehr beschrieben werden.  
  
## Befehls\-Routing Dispatch und MFC 1.0\-Funktionalität entwickelt mit MFC 2.0\-Architektur  
 Windows enthält die Meldung, die **WM\_COMMAND** überladen ist, um Benachrichtigungen von Menübefehlen, von Zugriffstasten und von DialogfeldSteuerelementbenachrichtigungen bereitzustellen.  
  
 MFC 1.0 erstellte auf dem wenig, indem ein Befehlshandler \(beispielsweise, "OnFileNew"\) in einer **CWnd** abgeleiteten Klasse ermöglicht, um als Reaktion auf bestimmtes **WM\_COMMAND** aufgerufen werden.  Dies wird mit einer Datenstruktur geklebt, die die Meldungszuordnung aufgerufen und führt zu einem sehr Leerzeichen\-effizienten Befehlsmechanismus.  
  
 MFC 1.0 wurde auch zusätzliche Features für das Trennen von Steuerelementbenachrichtigungen von den Befehlsmeldungen bereit.  Befehle werden von einer 16\-Bit\-ID dargestellt, manchmal die als Befehl ID  Befehle werden normalerweise von **CFrameWnd** \(das heißt, ein Menü ausgewählt oder eine übersetzte Zugriffstaste\) ab und rufen weitergeleitet zu einer Vielzahl anderer Fenster ab.  
  
 MFC 1.0 verwendete Befehlsrouting in einem gebundenen Gespür für die Implementierung des Multiple Document Interface \(MDI\). \(Ein MDI\-Rahmenfensterdelegat Befehle an seinen aktiven untergeordneten MDI\-Fenster.\)  
  
 Diese Funktionalität ist in MFC 2.0 generalisiert wurde und erweitert, um Befehle zu ermöglichen, durch einen größeren Bereich von Objekte \(nicht nur Fensterobjekte\) behandelt werden.  Sie stellt eine formalere und erweiterbarere Architektur für das Weiterleiten von Meldungen an und verwendet das Befehlszielrouting nicht nur für von Befehle, sondern auch für das Aktualisieren mit Benutzeroberflächenobjekten \(wie Menüelemente und Symbolleisten\-Schaltflächen\) um die aktuelle Verfügbarkeit eines Befehls widerzuspiegeln erneut.  
  
## Befehls\-IDs  
 Siehe Visual C\+\+ für eine Erläuterung des Befehlsroutings und des Bindungsvorgangs.  [Technischer Hinweis 20](../mfc/tn020-id-naming-and-numbering-conventions.md) enthält Informationen über ID\-Benennung.  
  
 Wir verwenden das generische Präfix "ID\_" für Befehls\-IDs.  Befehls\-IDs sind \>\= 0x8000.  Die die Meldungszeile oder \-Statusleiste zeigen die Befehlsbeschreibungszeichenfolge an, wenn eine STRINGTABLE\-Ressource mit denselben IDs wie Befehl gibt die ID  
  
 In die Ressourcen der Anwendung, wird eine Befehls\-ID\-Dose in mehreren lauten:  
  
-   In einer STRINGTABLE\-Ressource, die dieselbe ID wie die MeldungZeileneingabeaufforderung hat.  
  
-   In vielen möglicherweise Menüressourcen, die auf die Menüelemente angefügt werden, die den gleichen Befehl aufrufen.  
  
-   \(GEWECHSELT\) in einer Dialogfeldschaltfläche für einen GOSUB\-Befehl.  
  
 Im Quellcode der Anwendung, wird eine Befehls\-ID\-Dose in mehreren lauten:  
  
-   In dem RESOURCE.H \(oder anderen\) zum zentralen Symbolheaderdatei anwendungsspezifischer Befehls\-IDs zu definieren.  
  
-   Vielleicht in einem ID\-Array verwendet, um eine Symbolleiste zu erstellen.  
  
-   In einem Makro **ON\_COMMAND**.  
  
-   Vielleicht in einem **ON\_UPDATE\_COMMAND\_UI**\-Makro.  
  
 Die einzige Implementierung in MFC, das Reservieren erfordert, \>\= 0x8000 ist die Implementierung von GOSUB\-Dialogfeldern\/\-Befehlen.  
  
## GOSUB\-Befehle, mit der Befehls\-Architektur in Dialogfeldern  
 Die Befehlsarchitektur des Routings und Aktivieren von Befehlsarbeiten gut mit den Rahmenfenstern, Menüelemente, Symbolleistenschaltflächen, Dialogleistenschaltflächen, anderen Steuerleisten und anderen UI\-Elementen hervor, die entwickelt wurden, um bei Bedarf aktualisiert und Befehle oder Steuerelement\-IDs zu einem Hauptbefehlsziel \(normalerweise das Hauptrahmenfenster\) weiterzuleiten.  Diese Hauptbefehlsziel möglicherweise den Befehl oder die Steuerelementbenachrichtigungen einer anderen weiterleitet, erlernen Sie Zielobjekte entsprechend.  
  
 Ein Dialogfeld \(modal oder nicht modal\) kann für einige der Funktionen der Befehlsarchitektur profitieren, wenn Sie die Steuerelement\-ID des Dialogfeldsteuerelements zur entsprechenden Befehl ID zuweisen  Unterstützung für Dialogfelder ist nicht automatisch, müssen Sie möglicherweise einen zusätzlichen Code schreiben.  
  
 Beachten Sie, dass für alle diese Funktionen ordnungsgemäß, die Befehls\-IDs sollten sein \>\= 0x8000 arbeiten.  Da viele Dialogfelder abrufen können weitergeleitet zu den gleichen Frame, sollten freigegebene Befehle sein \>\= 0x8000, während das nicht freigegebene IDC in ein bestimmtes Dialogfeld sollte \<\= 0x7FFF.  
  
 Sie können eine normale Schaltfläche in einem normalen modalen Dialogfeld mit dem Schaltflächensatzes IDC des zur entsprechenden Befehl platzieren ID  Wenn der Benutzer die Schaltfläche auswählt, ruft der Besitzer des Dialogfelds \(normalerweise das Hauptrahmenfenster\) den Befehl nicht von anderen Befehl ab.  Dies wird als GOSUB\-Befehl aufgerufen, da normalerweise verwendet wird, um ein anderes Dialogfeld \(ein GOSUB des ersten Dialogfelds\) einzublenden.  
  
 Sie können die **CWnd::UpdateDialogControls** im Dialogfeld auch aufrufen und sie übergeben die Adresse des Hauptrahmenfensters.  Diese Funktion aktiviert oder deaktiviert die Dialogfeldkontrollen darauf basiert, ob sie Befehlshandler in den Frames haben.  Diese Funktion wird automatisch für Sie für die Leerlaufschleife Steuerleisten in Ihrer Anwendung, Sie müssen diese jedoch direkt für normale Dialogfelder aufrufen, diese Funktion haben möchten.  
  
## Wenn ON\_UPDATE\_COMMAND\_UI aufgerufen wird  
 Wartungsaktiviert\/aktivierter Zustand von sämtlichem die Menüelemente eines Programms kann ein Problem rechenintensives ständig sein.  Eine gängige Technik ist zu aktivieren\/Überprüfungsmenüelemente nur, wenn der Benutzer das POPUP auswählt.  Die MFC 2.0\-Implementierung von **CFrameWnd** behandelt die Meldung und **WM\_INITMENUPOPUP** verwendet die Befehlsroutingarchitektur, um Änderungen der Menüs durch **ON\_UPDATE\_COMMAND\_UI**\-Handler zu bestimmen.  
  
 **CFrameWnd** behandelt auch **WM\_ENTERIDLE** die Meldung, um das aktuelle Menüelement zu beschreiben, das auf der Statusleiste ausgewählt wird \(auch die Meldungszeile\).  
  
 Die Menüstruktur einer Anwendung, mit Visual C\+\+ bearbeitet, wird verwendet, um die möglichen Befehle darstellen, die an **WM\_INITMENUPOPUP** Zeit verfügbar sind.  **ON\_UPDATE\_COMMAND\_UI** Sie können den Zustand oder den Text eines Menüs oder für erweiterte Verwendung ändern \(wie die Datei\-MRU\-Liste oder das OLE\-Verbpopupmenü\), ändern tatsächlich die Menüstruktur, bevor das Menü gezeichnet wird.  
  
 Dieselbe Sortierung von **ON\_UPDATE\_COMMAND\_UI** Verarbeitung ist für Symbolleisten ausgeführt \(und anderen Steuerleisten\) wenn deren Leerlaufschleife eingibt.  Siehe die *Klassenbibliothek zu verweisen* und [Technischer Hinweis 31](../mfc/tn031-control-bars.md) weitere Informationen zu Steuerleisten.  
  
## Geschachtelte Popupmenüs  
 Wenn Sie eine geschachtelte Menüstruktur verwenden, beachten Sie, dass der **ON\_UPDATE\_COMMAND\_UI**\-Handler zum ersten Menüelement im Popupmenü in zwei verschiedenen Fällen aufgerufen wird.  
  
 Zuerst wird es für das Kontextmenü selbst aufgerufen.  Dies ist erforderlich, da Popupmenüs nicht IDs verfügen und Sie die ID des ersten Menüelements des Popupmenüs verwenden, um das ganze Popupmenü zuzugreifen.  In diesem Fall ist die **m\_pSubMenu**\-Membervariable des **CCmdUI**\-Objekts nicht NULL und zeigt im Popupmenü.  
  
 Zweitens wird sie aufgerufen, unmittelbar bevor die Menüelemente im Popupmenü gezeichnet werden sollen.  In diesem Fall verweist nur die ID zum ersten Menüelement und die **m\_pSubMenu**\-Membervariable des **CCmdUI**\-Objekts ist NULL.  
  
 Dieses ermöglicht, das Popupfenster zu aktivieren, das aus den Menüelementen unterscheidet, erfordert jedoch, dass Sie einem Menü bewussten Code schreiben.  Bei einem geschachtelten Menü mit der folgenden Struktur:  
  
```  
File>  
    New>  
        Sheet (ID_NEW_SHEET)  
        Chart (ID_NEW_CHART)  
```  
  
 Die ID\_NEW\_SHEET\- und ID\_NEW\_CHART\-Befehle können unabhängig aktiviert oder deaktiviert werden.  Das Popupmenü sollte **Neu** aktiviert werden, wenn einer der beiden aktiviert ist.  
  
 Der für ID\_NEW\_SHEET Befehlshandler \(der ersten Befehl im Popup\) würde etwa wie folgt aussehen:  
  
```  
void CMyApp::OnUpdateNewSheet(CCmdUI* pCmdUI)  
{  
    if (pCmdUI->m_pSubMenu != NULL)  
    {  
        // enable entire pop-up for "New" sheet and chart  
        BOOL bEnable = m_bCanCreateSheet || m_bCanCreateChart;  
  
        // CCmdUI::Enable is a no-op for this case, so we  
        //   must do what it would have done.  
        pCmdUI->m_pMenu->EnableMenuItem(pCmdUI->m_nIndex,  
            MF_BYPOSITION |   
                (bEnable ? MF_ENABLED : (MF_DISABLED | MF_GRAYED)));  
        return;  
    }  
    // otherwise just the New Sheet command  
    pCmdUI->Enable(m_bCanCreateSheet);  
}  
```  
  
 Der Befehlshandler für ID\_NEW\_CHART wird ein normaler Updatebefehlshandler und \-blick etwa wie sein:  
  
```  
void CMyApp::OnUpdateNewChart(CCmdUI* pCmdUI)  
{  
    pCmdUI->Enable(m_bCanCreateChart);  
}  
```  
  
## ON\_COMMAND und ON\_BN\_CLICKED  
 Die Meldungszuordnungsmakros für **ON\_COMMAND** und **ON\_BN\_CLICKED** sind identisch.  Der MFC\-Befehls\- und \-Steuerelementbenachrichtigungsroutingmechanismus verwendet nur die Befehls\-ID, um zu entscheiden, wo auf weiterleitet.  Steuerelementbenachrichtigungen mit Steuerelementbenachrichtigungscode von null \(**BN\_CLICKED**\) werden als Befehle interpretiert.  
  
> [!NOTE]
>  Tatsächlich werden alle Steuerelement\-Benachrichtigungen die Befehlshandlerkette durch.  Beispielsweise ist es technisch möglich, Sie einen Steuerelementbenachrichtigungshandler für **EN\_CHANGE** in der Dokumentklasse zu schreiben.  Dies ist im Allgemeinen nicht, da die praktische wenige Anwendungen dieser Funktion sind, die Funktion wird nicht unterstützt, und Sie über die Verwendung der Funktion kann empfindlichen Code führen.  
  
## Deaktivieren des automatischen Deaktivierens der Schaltflächen\-Steuerelemente  
 Wenn Sie ein Button\-Steuerelement auf einer Dialogleiste oder Dialogfeld platzieren, mit dem Sie das **CWnd::UpdateDialogControls** auf eigenen aufrufen, sehen Sie, dass Schaltflächen, nicht die **ON\_COMMAND** oder **ON\_UPDATE\_COMMAND\_UI**\-Handler haben, automatisch für Sie vom Framework deaktiviert werden.  In einigen Fällen ist es nicht erforderlich, um einen Handler verfügen, möchten Sie jedoch die Schaltfläche aktiviert bleiben.  Die einfachste Möglichkeit, dies zu erreichen ist, einen Befehlshandler blinden hinzuzufügen \(einfach, mit die auszuführen\) nichts und darin verwendet.  
  
## Fenster\-Meldungslenkung  
 Im Folgenden beschreibt mehr komplexere Themen auf MFC\-Klassen und wie Windows\-Meldungs\-Routing und anderen Themen sie auswirken.  Die Informationen werden hier nur kurz beschrieben.  Informieren Sie den *der Class Library Reference* für Informationen über öffentliche APIs an.  Verwenden Sie stattdessen den MFC\-Bibliotheksquellcode weitere Informationen darüber Implementierungsdetails an.  
  
 finden Sie unter [Technischer Hinweis 17](../mfc/tn017-destroying-window-objects.md) für Informationen zu Fensterbereinigung, ein sehr wichtiges Thema für alle **CWnd** abgeleitete Klassen.  
  
## CWnd\-Probleme  
 Die Implementierungsmemberfunktion **CWnd::OnChildNotify** stellt eine leistungsfähige und erweiterbare Architektur für untergeordnete Fenster \(auch Steuerelemente\) eine Einbindung bereit oder ist andernfalls von Meldungen, von Befehlen und den Steuerelementbenachrichtigungen informiert, die zum übergeordneten Element wechseln \(oder "Besitzer"\).  Wenn das untergeordnete Fenster \(\/control\) ein C\+\+\-Objekt **CWnd** selbst ist, wird die virtuelle Funktion **OnChildNotify** zunächst mit den Parametern der ursprüngliche Nachricht aufgerufen \(das heißt, eine **MSG**\-Struktur\).  Das untergeordnete Fenster die Meldung kann allein verlassen, sie essen oder die Meldung für das übergeordnete Element ändern \(selten\).  
  
 Die standardmäßige Implementierung **CWnd** behandelt die folgenden Meldungen und verwendet den **OnChildNotify** Hook, um untergeordnete Fenster \(Steuerelemente\) zum ersten Zugriff an der Meldung zu ermöglichen:  
  
-   **WM\_MEASUREITEM** und **WM\_DRAWITEM** \(für Selbstzeichnung\)  
  
-   **WM\_COMPAREITEM** und **WM\_DELETEITEM** \(für Selbstzeichnung\)  
  
-   **WM\_HSCROLL** und **WM\_VSCROLL**  
  
-   **WM\_CTLCOLOR**  
  
-   **WM\_PARENTNOTIFY**  
  
 Beachten Sie den **OnChildNotify** Hook werden zum Ändern von Ownerdrawnmeldungen in Selbstzeichnungsmeldungen.  
  
 Neben **OnChildNotify** Hook haben Bildlaufmeldungen weiteres Routingverhalten.  Siehe unten für weitere Informationen über Bildlaufleisten und Quellen von **WM\_HSCROLL** und **WM\_VSCROLL** Meldungen.  
  
## CFrameWnd\-Probleme  
 Die **CFrameWnd**\-Klasse stellt die meiste Befehlsroutings und Benutzeroberfläche Implementierung zu aktualisieren.  Dieses wird hauptsächlich für das Hauptrahmenfenster der Anwendung \(**CWinApp::m\_pMainWnd**\) verwendet jedoch gilt für alle Rahmenfenster.  
  
 Das Hauptrahmenfenster ist das Fenster mit der Menüleiste und ist das übergeordnete Element der Statusleisten\- oder die Meldungszeile.  Einzelheiten erfahren Sie im die obige Diskussion auf Befehl Routing und **WM\_INITMENUPOPUP.** an  
  
 Die **CFrameWnd**\-Klasse stellt Verwaltung der aktiven Ansicht.  Die folgenden Meldungen werden durch die aktive Ansicht gesendet:  
  
-   Alle anweisen Meldungen \(die aktive Ansicht ruft ersten Zugriff darauf ab\).  
  
-   **WM\_HSCROLL** und **WM\_VSCROLL** von Meldungen von den nebengeordneten Bildlaufleisten \(siehe unten\).  
  
-   \(**WM\_ACTIVATE** und **WM\_MDIACTIVATE** für MDI\) Rufen gemacht zu Aufrufe der virtuellen Funktion **CView::OnActivateView** ausgelöst.  
  
## CMDIFrameWnd\-\/CMDIChildWndprobleme  
 Beide MDI\-Rahmenfensterklassen werden von **CFrameWnd** und daher werden für die gleiche Art Befehlsroutings und des Benutzeroberflächeaktualisierens aktiviert, die in **CFrameWnd** bereitgestellt werden.  In einer typischen MDI\-Anwendung nur das Hauptrahmenfenster \(das heißt, das **CMDIFrameWnd**\-Objekt\) hält die Menüleiste und die Statusleiste an und ist daher die Hauptquelle der Befehlsroutingimplementierung.  
  
 Das allgemeine Routingschema ist, dass das aktive untergeordnete MDI\-Fenster ersten Zugriff auf Befehle abruft.  Die standardmäßige **PreTranslateMessage** bearbeiten Zugriffstastentabellen Funktionen für untergeordnete MDI\-Fenster \(zuerst\) und die MDI\-Frame \(Sekunden\) sowie die SystemBefehlszugriffstasten standardmäßigen MDI, die normalerweise durch **TranslateMDISysAccel** behandelt werden \(zuletzt angezeigt\).  
  
## Bildlaufleisten\-Probleme  
 Von wenn Sie ROLLENMeldung \(**WM\_HSCROLL**\/**OnHScroll** und\/oder **WM\_VSCROLL**\/**OnVScroll**\) behandeln, sollten Sie versuchen, den Handlercode schreiben, sodass beruht er nicht auf, wobei die Bildlaufleistenmeldung stammt.  Dies ist nicht nur ein Problem allgemeinen Windows, da Bildlaufmeldungen von den wahren ScrollBar\-Steuerelemente oder **WS\_HSCROLL**\/**WS\_VSCROLL** Bildlaufleisten stammen können, die nicht ScrollBar\-Steuerelemente sind.  
  
 MFC erweitert das, um zu dürfen, damit ScrollBar\-Steuerelemente entweder untergeordnetes Element oder gleichgeordnete Elemente des Fensters befinden, das durch einen Bildlauf angezeigt wird \(tatsächlich, können die Beziehungen zwischen übergeordneten und untergeordneten der Bildlaufleiste und das Fenster, das durch einen Bildlauf angezeigt wird, alle sein\).  Dies ist für freigegebene Bildlaufleisten mit Splitterfenstern besonders wichtig.  finden Sie unter [Technischer Hinweis 29](../mfc/tn029-splitter-windows.md) für Informationen über die Implementierung von **CSplitterWnd** einschließlich Informationen über freigegebene Bildlaufleistenprobleme an.  
  
 Auf einer Randbemerkung gibt es zwei **CWnd** abgeleitete Klassen, in denen die Bildlaufleistenformate, die an der Erstellungszeit angegeben werden, und nicht aufgefangen werden Windows zu übergeben.  Wenn sie einer Erstellungsroutine übergeben werden, können **WS\_HSCROLL** und **WS\_VSCROLL** unabhängig festgelegt werden, kann aber, nach Erstellung nicht geändert werden kann.  Natürlich sollten Sie das WS\_ nicht direkt testen oder festlegen? FÜHREN Sie Stilbite des Fensters Bildlauf das sie erstellt haben.  
  
 Für **CMDIFrameWnd** die Bildlaufleistenformate, die Sie in **Erstellen** übergeben, oder **LoadFrame** werden verwendet, um das MDICLIENT zu erstellen.  Wenn Sie einen bildlauffähigen MDICLIENT\-Bereich haben möchten \(z Windows\-Programm\-Manager\) stellen Sie sicher, beide Bildlaufleistenformate festzulegen \(**WS\_HSCROLL** &#124; **WS\_VSCROLL**\) für das Format verwendet, um die **CMDIFrameWnd** zu erstellen.  
  
 Für **CSplitterWnd** gelten die Bildlaufleistenformate auf besondere freigegebenen Bildlaufleisten für die Splitterbereiche zu.  Für statische Splitterfenster legen Sie normalerweise nicht jedes Bildlaufleistenformat fest.  Für dynamische Splitterfenster haben Sie normalerweise das Bildlaufleistenformat festgelegt für die Richtung, die Sie aufteilen h. **WS\_HSCROLL**, wenn Sie Zeilen teilen können, **WS\_VSCROLL**, wenn Sie Spalten unterteilen können.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)