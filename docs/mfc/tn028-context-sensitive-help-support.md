---
title: "TN028: Bereitstellen kontextbezogener Hilfe"
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
  - "vc.help"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Kontextbezogene Hilfe, MFC-Anwendungen"
  - "Ressourcenbezeichner, Kontextbezogene Hilfe"
  - "TN028"
ms.assetid: 884f1c55-fa27-4d4c-984f-30907d477484
caps.latest.revision: 13
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# TN028: Bereitstellen kontextbezogener Hilfe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Hinweis beschreibt die Regeln zum Zuweisen von Hilfekontexte IDs und anderen Hilfeproblemen in MFC.  Unterstützung der kontextbezogenen Hilfe fordert den Hilfecompiler, der in Visual C\+\+ verfügbar ist.  
  
> [!NOTE]
>  Neben kontextbezogene Hilfe mithilfe WinHelps ebenfalls implementieren, MFC\-Unterstützung mithilfe von HTML.  Weitere Informationen über diese Unterstützung und Programmierung mit HTML, finden Sie unter [Help: Kontextbezogene Hilfe für die Programme](../mfc/html-help-context-sensitive-help-for-your-programs.md).  
  
## Typen der Hilfe unterstützt  
 Es gibt zwei Typen kontextbezogene Hilfe implementiert in Windows\-Anwendungen.  Der erste, wird als "F1\-Hilfe", scrollen WinHelp im entsprechenden Kontext anhand das aktive Objekt zu starten.  Das zweite ist "UMSCHALT\+F1\-" Modus.  In diesem Modus ändert sich der Mauszeiger zum Hilfe\-Cursor, und der Benutzer weiterhin, um in einem Objekt zu klicken.  An diesem Punkt wird WinHelp gestartet, um Hilfe für das Objekt zu geben, den der Benutzer auf klicken.  
  
 Das Microsoft Foundation Classes\-Werkzeug beide Formen der Hilfe.  Zusätzlich unterstützt das Framework zwei einfache Hilfebefehle, Hilfeindex und mithilfe.  
  
## Hilfedateien  
 Die Microsoft Foundations\-Klassen akzeptieren eine einzelne Hilfedatei an.  Diese Hilfedatei muss den gleichen Namen und Pfad wie die Anwendung haben.  Wenn die ausführbare Datei C:\\MyApplication\\MyHelp.exe ist, muss die Hilfedatei C:\\MyApplication\\MyHelp.hlp.sein  Sie legen den Pfad durch die `m_pszHelpFilePath`\-Membervariable [CWinApp Class](../mfc/reference/cwinapp-class.md).  
  
## Hilfe\-Kontext\-Bereiche  
 Die Standardimplementierung von MFC benötigt ein Programm, mehreren Regeln über die Zuweisung von Hilfekontext\-ids folgen.  Diese Regeln sind ein Bereich von den IDs, die bestimmten Steuerelementen zugeordnet sind.  Diese Regeln können Sie überschreiben, indem Sie unterschiedliche Implementierungen der verschiedenen Hilfe\-verknüpften Memberfunktionen bereitstellen.  
  
```  
0x00000000 - 0x0000FFFF : user defined  
0x00010000 - 0x0001FFFF : commands (menus/command buttons)  
   0x00010000 + ID_  
   (note: 0x18000-> 0x1FFFF is the practical range since command IDs are >=0x8000)  
0x00020000 - 0x0002FFFF : windows and dialogs  
   0x00020000 + IDR_  
   (note: 0x20000-> 0x27FFF is the practical range since IDRs are <= 0x7FFF)  
0x00030000 - 0x0003FFFF : error messages (based on error string ID)  
   0x00030000 + IDP_  
0x00040000 - 0x0004FFFF : special purpose (non-client areas)  
   0x00040000 + HitTest area  
0x00050000 - 0x0005FFFF : controls (those that are not commands)  
   0x00040000 + IDW_  
```  
  
## Einfache "Hilfe\-" Befehle  
 Es gibt zwei einfache Hilfebefehle, die von Microsoft Foundation Classes implementiert werden:  
  
-   ID\_HELP\_INDEX, das vom [CWinApp::OnHelpIndex](../Topic/CWinApp::OnHelpIndex.md) implementiert wird  
  
-   ID\_HELP\_USING, das vom [CWinApp::OnHelpUsing](../Topic/CWinApp::OnHelpUsing.md) implementiert wird  
  
 Der erste Befehl zeigt den Hilfeindex für die Anwendung an.  Das zweite zeigt die Benutzerhilfe auf der Verwendung des WinHelp\-Programms an.  
  
## Kontextbezogene Hilfe \(F1\-Hilfe\)  
 Die F1\-TASTE wird normalerweise einem Befehl mit einer ID von `ID_HELP` durch eine Zugriffstaste übersetzt, die in der Zugriffstastentabelle des Hauptfensters platziert wird.  Der `ID_HELP` Befehl auch von einer Schaltfläche mit einer ID von `ID_HELP` für das Hauptfenster oder das Dialogfeld generiert werden.  
  
 Unabhängig davon, wie der `ID_HELP` Befehl generiert wird, wird sie als normaler Befehl weitergeleitet, bis er einen Befehlshandler erreicht.  Weitere Informationen über die MFC\-BefehlRoutingarchitektur, finden Sie unter [Technischer Hinweis 21](../mfc/tn021-command-and-message-routing.md).  Wenn die Anwendung die aktivierte Hilfe verfügt, wird der `ID_HELP` Befehl von [CWinApp::OnHelp](../Topic/CWinApp::OnHelp.md) behandelt.  Das Anwendungsobjekt empfängt die Hilfemeldung und leitet anschließend den Befehl ordnungsgemäß weiter.  Dies ist notwendig, da das Standardbefehlsrouting nicht zum Bestimmen des bestimmtsten Kontext geeignet ist.  
  
 `CWinApp::OnHelp` versucht, WinHelp in der folgenden Reihenfolge zu starten:  
  
1.  Überprüfungen für einen aktiven `AfxMessageBox` Aufruf mit einer ID Hilfe  Wenn ein Meldungsfeld derzeit aktiv, wird WinHelp mit dem Kontext gestartet, der zu diesem Meldungsfeld geeignet ist.  
  
2.  Sendet eine WM\_COMMANDHELP\-Meldung das aktive Fenster.  Wenn dieses Fenster nicht reagiert, indem WinHelp startet, wird dieselbe Nachricht dann an Vorgängern dieses Fensters gesendet, wenn die Meldung verarbeitet ist, oder das aktive Fenster ein Fenster der obersten Ebene ist.  
  
3.  Sendet einen ID\_DEFAULT\_HELP\-Befehl im Hauptfenster.  Dadurch wird die Standardeinstellung Hilfe auf.  Dieser Befehl ist im Allgemeinen `CWinApp::OnHelpIndex` zugeordnet.  
  
 Um die Standard\- ID\-Basiswerte \(z. B. 0x10000 für Befehle und 0x20000 für Ressourcen wie Dialogfelder\) global zu überschreiben, sollte die Anwendung [CWinApp::WinHelp](../Topic/CWinApp::WinHelp.md) überschreiben.  
  
 Um diese Funktionalität und die Methode zu überschreiben die ein Hilfekontext bestimmt wird, sollten Sie die WM\_COMMANDHELP\-Meldung bearbeiten.  Sie möchten möglicherweise mehr bestimmtes Hilferouting bereitstellen, als das Framework bereitstellt, da nur so aussehen wie das aktuelle untergeordnete MDI\-Fenster geht.  Sie können auch mehr spezielle Hilfe für ein bestimmtes Fenster oder Dialogfeld, können abhängig vom aktuellen internen Zustand dieses Objekts oder das aktive Steuerelement innerhalb des Dialogfelds stellen.  
  
## WM\_COMMANDHELP  
  
```  
  
afx_msg LRESULT CWnd::OnCommandHelp(WPARAM wParam, LPARAM lParam)  
```  
  
 WM\_COMMANDHELP ist eine private Meldung von MFC, die vom aktiven Fenster empfangen wird, wenn die Hilfe angefordert wird.  Wenn das Fenster die Meldung empfängt, ruft es `CWinApp::WinHelp` mit Kontext auf, der den internen Zustand des Fensters übereinstimmt.  
  
 `lParam`  
 Enthält den zur Zeit verfügbaren Hilfekontext.  `lParam` ist ungewöhnlich, wenn kein Hilfekontext bestimmt wurde.  Eine Implementierung von `OnCommandHelp` kann die Kontext\-ID in `lParam` verwenden, um einen anderen Kontext zu bestimmen oder kann ihn zu einfach `CWinApp::WinHelp` übergeben.  
  
 `wParam`  
 Wird nicht verwendet und ist null sein.  
  
 Wenn die `OnCommandHelp` durch `CWinApp::WinHelp`, die `TRUE` zurückgeben.  Die Rückgabe von `TRUE` beendet das Routing dieses Befehls zu anderen Klassen und zu anderen Fenstern.  
  
## Hilfe\-Modus \(UMSCHALT\+F1\-Hilfe\)  
 Dies ist die zweite Formular der kontextbezogenen Hilfe.  Im Allgemeinen wird dieser Modus eingeführt, mit oder über das Menü und die Symbolleiste UMSCHALT\+F1 drückt.  Es wird als Befehl \(**ID\_CONTEXT\_HELP**\) implementiert.  Der Meldungsfilterhook wird nicht verwendet, um diesen Befehl zu übersetzen, während ein modales Dialogfeld oder Menüs aktiv ist, daher ist dieser Befehl dem Benutzer nur verfügbar, wenn die Anwendung die Haupt\-Meldungsverteilschleife \(`CWinApp::Run`\).  
  
 Nachdem dieser Modus eingegeben hat, wird der Hilfemauszeiger zu allen Bereichen der Anwendung angezeigt, selbst wenn die Anwendung normalerweise den eigenen Cursor für diesen Bereich anzeigen würde \(beispielsweise die Größenanpassungsrahmen um das Fenster\).  Der Benutzer ist in der Lage, die Maus oder die Tastatur verwenden, um einen Befehl aus.  Anstatt, Ausführen des Befehls angezeigt, wird Hilfe zu diesem Befehl.  Außerdem kann der Benutzer auf ein sichtbares Objekt auf dem Bildschirm, wie eine Schaltfläche auf der Symbolleiste, und Hilfe wird für das Objekt angezeigt.  Dieser Modus der Hilfe wird von `CWinApp::OnContextHelp` bereitgestellt.  
  
 Während der Ausführung dieser Schleife, ist alles Tastatureingabe, nur Schlüssel inaktiv, die auf das Menü zugreifen.  Außerdem Befehlsübersetzung wird weiterhin über `PreTranslateMessage` ausgeführt, um den Benutzer zu ermöglichen, eine Zugriffstaste zu drücken und Hilfe zu diesem Befehl empfangen.  
  
 Wenn es bestimmte Übersetzungen gibt, oder die Aktionen, die in `PreTranslateMessage` erfolgen, arbeiten, das nicht während des UMSCHALT\+F1\-Hilfemodus erfolgen sollte, sollten Sie den `m_bHelpMode`\-Member von `CWinApp` überprüfen, bevor Sie diese Vorgänge ausführen.  Die `CDialog` Implementierung von `PreTranslateMessage` überprüft dies, bevor `IsDialogMessage`, z aufruft.  Deaktiviert "Dialogfeldnavigations" Tasten auf nicht modalen Dialogfeldern während UMSCHALT\+F1\-Modus.  Darüber hinaus wird `CWinApp::OnIdle` dennoch während dieser Schleife aufgerufen.  
  
 Wenn der Benutzer einen Befehl im Menü auswählen, wird es als Hilfe zu diesem Befehl behandelt \(von **WM\_COMMANDHELP**, siehe unten\).  Wenn der Benutzer auf einen sichtbaren Bereich des Anwendungsfensters klickt, wird eine Überprüfung ausgeführt, ob ein Nicht\-Client\-Klick oder ein Clientklick ist.  das `OnContextHelp` Handlezuordnen von Nicht\-Client\-Klicken den Client klickt automatisch.  Wenn ein Clientklick ist, sendet anschließend **WM\_HELPHITTEST** auf das Fenster, auf das geklickt wurde.  Wenn dieses Fenster einen Wert ungleich 0 \(null\) zurückgibt, wird dieser Wert als Kontext für die Hilfe verwendet.  Wenn er null zurückgibt, versucht `OnContextHelp` das übergeordnete Fenster \(und das Verlassen das, das übergeordnete Element, z.\).  Wenn ein Hilfekontext nicht bestimmt werden kann, ist der Standardwert, einen Befehl **ID\_DEFAULT\_HELP** im Hauptfenster zu senden, das dann \(normalerweise\) `CWinApp::OnHelpIndex` zugeordnet ist.  
  
## WM\_HELPHITTEST  
  
```  
  
afx_msg LRESULT CWnd::OnHelpHitTest(  
WPARAM, LPARAM lParam)  
```  
  
 **WM\_HELPHITTEST** ist eine private Fenstermeldung MFC, die vom aktiven Fenster empfangen wird, die während des UMSCHALT\+F1\-Hilfemodus geklickt wird.  Wenn das Fenster die Meldung empfängt, wird eine DWORD Hilfe ID für WinHelp zurück.  
  
 LOWORD \(lParam\)  
 enthält die x\-Achsen\-Gerätekoordinate, auf der auf die Maus relativ zum Clientbereich des Fensters geklickt wurde.  
  
 HIWORD \(lParam\)  
 enthält die y\-Achsen\-Koordinate.  
  
 `wParam`  
 wird nicht verwendet und ist null sein.  Falls der Rückgabewert ungleich 0 ist, wird mit diesem WinHelp Kontext bezeichnet.  Falls der Rückgabewert ist, ist das übergeordnete Fenster für Hilfe abgefragt.  
  
 In vielen Fällen können Sie Treffertestscode nutzen, den Sie möglicherweise bereits verfügen.  Siehe die Implementierung von **CToolBar::OnHelpHitTest** ein Beispiel der Behandlung der **WM\_HELPHITTEST** Meldung \(der Code nutzt den Treffertestcode, der auf Schaltflächen und QuickInfo in `CControlBar` verwendet wird\).  
  
## MFC\-Anwendungs\-Assistenten\-Unterstützung und MAKEHM  
 Der MFC\-Anwendungs\-Assistent erstellt die notwendigen Dateien, eine Hilfedatei zu erstellen \(.cnt\- und .hpj\-Dateien\).  Sie schließt auch mehrere vordefinierte RTF\-Dateien ein, die vom Microsoft\-Hilfe\-Compiler akzeptiert werden.  Viele der Themen sind vollständig, aber einige müssen möglicherweise für Ihre spezielle Anwendung geändert werden.  
  
 Automatische Erstellung einer "Hilfezuordnungs" Datei wird durch ein Dienstprogramm MAKEHM unterstützt, das aufgerufen wird.  Das Dienstprogramm kann das RESOURCE.H\-Datei einer Anwendung in einer Hilfezuordnungsdatei übersetzen.  Beispiel:  
  
```  
#define IDD_MY_DIALOG   2000  
#define ID_MY_COMMAND   150  
```  
  
 wird in übersetzt:  
  
```  
HIDD_MY_DIALOG    0x207d0  
HID_MY_COMMAND    0x10096  
```  
  
 Dieser Stil ist mit der Funktion des Hilfecompilers kompatibel, die Kontext\-IDs \(den Zahlen auf der rechten Seite\) mit Themaennamen zuordnet \(die Symbole auf der linken Seite\).  
  
 Der Quellcode für MAKEHM ist Programmierung im Beispiel [MAKEHM](../top/visual-cpp-samples.md) Hilfsverfügbar MFC.  
  
## Hilfeunterstützung hinzufügen, nachdem der MFC\-Anwendungs\-Assistent ausgeführt wurde  
 Die beste Methode, Hilfe der Anwendung einzufügen, ist die Option "der kontextbezogenen Hilfe" auf der Seite der erweiterten Features des MFC\-Anwendungs\-Assistenten zu überprüfen, bevor sie die Anwendung erstellt.  Somit der MFC\-Anwendungs\-Assistent fügt automatisch die erforderlichen Meldungszuordnungseinträgen dem `CWinApp` abgeleiteten Klasse zur Unterstützungshilfe hinzu.  
  
## Hilfe in Meldungsfeldern  
 Hilfe in Meldungsfeldern \(manchmal als Warnungen\) wird durch die `AfxMessageBox`\-Funktion, ein Wrapper für die Windows\-API `MessageBox` unterstützt.  
  
 Es gibt zwei Versionen von `AfxMessageBox`, einem für einer Zeichenfolgen\-ID und anderen für einen Zeiger string \(`LPCSTR`\):  
  
```  
int AFXAPI AfxMessageBox(LPCSTR lpszText, UINT nType, UINT nIDHelp);  
int AFXAPI AfxMessageBox(UINT nIDPrompt, UINT nType, UINT nIDHelp);  
```  
  
 In beiden Fällen gibt es eine optionale ID Hilfe  
  
 Im ersten Fall ist der Standard für nIDHelp 0, das keine Hilfe für diesem Meldungsfeld angibt.  Wenn der Benutzer während wie Meldungsfeld ist aktiv F1 drückt, erhält der Benutzer keine Hilfe \(selbst wenn die Anwendungsunterstützungshilfe\).  Wenn dies nicht erwünscht ist, sollte eine Hilfe ID für nIDHelp bereitgestellt werden.  
  
 Im zweiten Fall ist der Standardwert für nIDHelp \-1, das der ID Hilfe entspricht nIDPrompt angibt.  Hilfe funktioniert nur wenn die Anwendung Hilfe\-aktiviert wird, benötigen.\)  Sie sollten für nIDHelp 0 bereitstellen, wenn Sie möchten, dass das Meldungsfeld keine Hilfeunterstützung haben.  Wenn die Meldung die aktivierte Hilfe sein sollen, jedoch eine andere ID als Hilfe nIDPrompt möchten, erstellen Sie einfach einen positiven Wert für das nIDHelp bereit, bei dem von nIDPrompt unterscheidet.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)