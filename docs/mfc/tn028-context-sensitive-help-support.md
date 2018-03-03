---
title: ': Tn028 Bereitstellen kontextbezogener Hilfe | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.help
dev_langs:
- C++
helpviewer_keywords:
- context-sensitive Help [MFC], MFC applications
- TN028
- resource identifiers, context-sensitive Help
ms.assetid: 884f1c55-fa27-4d4c-984f-30907d477484
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d8054fe4fae4aafa88c34833a5a2a92a6b9b44bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tn028-context-sensitive-help-support"></a>TN028: Bereitstellen kontextbezogener Hilfe
In diesem Hinweis werden die Regeln für die Zuweisung von Hilfe Kontexten-IDs sowie zu weiteren Problemen Hilfe in MFC beschrieben. Kontextbezogene Hilfe und Unterstützung erfordert den Hilfecompiler, der in Visual C++ verfügbar ist.  
  
> [!NOTE]
>  Zusätzlich zur Implementierung kontextbezogene Hilfe, die WinHelp verwenden, unterstützt MFC auch HTML-Hilfe. Weitere Informationen zu dieser Unterstützung und die Programmierung mit HTML-Hilfe, finden Sie unter [HTML-Hilfe: kontextbezogene Hilfe für Programme](../mfc/html-help-context-sensitive-help-for-your-programs.md).  
  
## <a name="types-of-help-supported"></a>Hilfetypen unterstützt  
 Es gibt zwei Arten von kontextbezogene Hilfe, die in Windows-Anwendungen implementiert. Die erste Seite bezeichnet als "F1 Help" umfasst die WinHelp mit den entsprechenden Kontext basierend auf dem derzeit aktiven Objekt starten. Die zweite ist der Modus "UMSCHALT + F1". In diesem Modus ändert sich des Mauszeigers auf den Hilfecursor, und der Benutzer auf ein Objekt klicken, wird fortgesetzt. An diesem Punkt wird WinHelp gestartet, um Hilfe für das Objekt zu gewähren, die auf der Benutzer geklickt hat.  
  
 Implementieren Sie die Microsoft Foundation Classes beiden der folgenden Formen der Hilfe. Darüber hinaus unterstützt das Framework zwei Hilfebefehle ein einfaches, Hilfe und Hilfe verwenden.  
  
## <a name="help-files"></a>Hilfedateien  
 Die Microsoft Foundation Classes gehen davon aus einer einzelnen Hilfedatei. Diese Hilfedatei muss den gleichen Namen und Pfad wie die Anwendung haben. Beispielsweise ist die ausführbare Datei C:\MyApplication\MyHelp.exe muss die Hilfedatei C:\MyApplication\MyHelp.hlp sein. Sie legen Sie den Pfad über die `m_pszHelpFilePath` Membervariable der der [CWinApp-Klasse](../mfc/reference/cwinapp-class.md).  
  
## <a name="help-context-ranges"></a>Hilfe-Kontext-Bereiche  
 Die standardmäßige Implementierung von MFC erfordert ein Programm, um einige Regeln über die Zuweisung von Hilfekontext IDs folgen. Diese Regeln sind eines Bereichs von IDs, die bestimmte Steuerelemente zugeordnet. Sie können diese Regeln überschreiben, indem Sie verschiedene Implementierungen von verschiedenen hilfebezogenen Memberfunktionen bereitstellen.  
  
```  
0x00000000 - 0x0000FFFF : user defined  
0x00010000 - 0x0001FFFF : commands (menus/command buttons)  
0x00010000 + ID_  
(note: 0x18000-> 0x1FFFF is the practical range since command IDs are>=0x8000)  
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
  
## <a name="simple-help-commands"></a>Einfache "Help"-Befehle  
 Es gibt zwei einfache Hilfe-Befehle, die von der Microsoft Foundation Classes implementiert werden:  
  
-   ID_HELP_INDEX von implementiert [CWinApp::OnHelpIndex](../mfc/reference/cwinapp-class.md#onhelpindex)  
  
-   ID_HELP_USING von implementiert [CWinApp::OnHelpUsing](../mfc/reference/cwinapp-class.md#onhelpusing)  
  
 Der erste Befehl zeigt die Hilfe-Index für die Anwendung. Die zweite zeigt die Hilfe verwenden die WinHelp-Anwendung.  
  
## <a name="context-sensitive-help-f1-help"></a>Kontextbezogene Hilfe (F1-Hilfe)  
 Die F1-Taste wird in der Regel an einen Befehl mit der ID übersetzt `ID_HELP` durch eine Zugriffstaste, die in das Hauptfenster Zugriffstastentabelle platziert. Die `ID_HELP` -Befehl kann auch generiert werden, durch eine Schaltfläche mit der ID `ID_HELP` auf der wichtigsten Fenster oder Dialogfeld.  
  
 Unabhängig davon, wie der `ID_HELP` Befehl generiert wird, es wird als normale Befehl weitergeleitet, bis Befehlshandler erreicht. Weitere Informationen über die MFC-Befehlsrouting Architektur finden Sie unter [technischen Hinweis 21](../mfc/tn021-command-and-message-routing.md). Wenn die Anwendung Hilfe aktiviert ist, hat die `ID_HELP` wird vom Befehl behandelt [CWinApp::OnHelp](../mfc/reference/cwinapp-class.md#onhelp). Das Anwendungsobjekt empfängt die Hilfe-Nachricht, und klicken Sie dann den Befehl wird entsprechend weitergeleitet. Dies ist erforderlich, da Sie nicht die Standard-Befehlsrouting zum Bestimmen des spezifischen Kontexts geeignet ist.  
  
 `CWinApp::OnHelp`versucht, die WinHelp in der folgenden Reihenfolge gestartet:  
  
1.  Überprüft, ob eine aktive `AfxMessageBox` Aufruf mit einem Hilfe-ID. Wenn ein Meldungsfeld gerade aktiv ist, wird mit dem entsprechenden in dieser MessageBox Kontext WinHelp gestartet.  
  
2.  Sendet eine Nachricht WM_COMMANDHELP an das aktive Fenster. Wenn dieses Fensters durch Starten WinHelp nicht reagiert, wird dieselbe Nachricht klicken Sie dann auf den übergeordneten Elementen dieses Fensters gesendet, bis die Nachricht verarbeitet oder das aktuelle Fenster ein Fenster der obersten Ebene ist.  
  
3.  ID_DEFAULT_HELP-Befehl an das Hauptfenster gesendet. Dadurch wird die Standardeinstellung Hilfe aufgerufen. Mit diesem Befehl wird in der Regel zugeordnet `CWinApp::OnHelpIndex`.  
  
 Um die Standard-ID Basiswerte (z. B. 0 x 10000 für Befehle und 0 x 20000 für Ressourcen, z. B. Dialogfeldern) Global zu überschreiben, sollten die Anwendung überschreiben [CWinApp::WinHelp](../mfc/reference/cwinapp-class.md#winhelp).  
  
 Überschreiben Sie diese Funktionalität und die Möglichkeit, dass ein Hilfekontext bestimmt wird, sollten die WM_COMMANDHELP Nachricht behandelt werden. Sie möchten möglicherweise spezifische Hilfe routing bereitstellen als das Framework bietet, dauern, da nur tiefer als der aktuellen untergeordneten MDI-Fensters wird. Sie sollten auch spezifische Hilfe für ein bestimmtes Fenster oder Dialogfeld basieren auf den aktuellen internen Zustand des Objekts oder das zum aktiven Steuerelement innerhalb des Dialogfelds bereitzustellen.  
  
## <a name="wmcommandhelp"></a>WM_COMMANDHELP  
  
```  
 
afx_msg LRESULT CWnd::OnCommandHelp(WPARAM wParam, LPARAM lParam)  
 
```  
  
 WM_COMMANDHELP ist eine private Windows-MFC-Nachricht, die durch das aktive Fenster empfangen wird, wenn Hilfe angefordert wird. Wenn das Fenster diese Nachricht empfängt, kann er aufgerufen `CWinApp::WinHelp` mit Kontext, der interne Zustand des Fensters entspricht.  
  
 `lParam`  
 Enthält den derzeit verfügbaren Hilfe-Kontext. `lParam`ist NULL, wenn keine Hilfekontext ermittelt wurde. Eine Implementierung der `OnCommandHelp` können die Kontext-ID in `lParam` zum Bestimmen von eines anderen Kontexts oder es können nur übergeben `CWinApp::WinHelp`.  
  
 `wParam`  
 Wird nicht verwendet und wird NULL sein.  
  
 Wenn die `OnCommandHelp` Funktionsaufrufe `CWinApp::WinHelp`, sollte zurückgegeben `TRUE`. Zurückgeben von `TRUE` beendet das routing von mit diesem Befehl, um andere Klassen und anderen Fenstern.  
  
## <a name="help-mode-shiftf1-help"></a>Hilfemodus (UMSCHALT + F1-Hilfe)  
 Dies ist die zweite Form der kontextbezogene Hilfe. In diesem Modus wird im Allgemeinen durch Drücken von UMSCHALT + F1 oder über die Menüleiste eingegeben. Es wird als Befehl implementiert (**ID_CONTEXT_HELP**). Der Meldungshook des Filters wird nicht verwendet, um diesen Befehl beim ein modales Dialogfeld übersetzen oder im Menü aktiv ist, daher mit diesem Befehl ist nur für den Benutzer verfügbar, wenn die Anwendung die Haupt-Meldungsverteilschleife ausgeführt wird (`CWinApp::Run`).  
  
 Nach der Eingabe dieser Modus, wird der Mauszeiger Hilfe über alle Bereiche der Anwendung, angezeigt, auch wenn die Anwendung normalerweise einen eigenen Cursor für diesen Bereich (z. B. Größenanpassungsrahmens um das Fenster) angezeigt wird. Der Benutzer kann die Maus oder Tastatur verwenden, um einen Befehl auswählen. Anstatt den Befehl auszuführen, wird die Hilfe zum Befehl "," angezeigt. Darüber hinaus kann der Benutzer auf ein sichtbares Objekt auf dem Bildschirm, z. B. eine Schaltfläche auf der Symbolleiste klicken und Hilfe für dieses Objekt angezeigt wird. In diesem Modus Hilfe gebotenen `CWinApp::OnContextHelp`.  
  
 Während der Ausführung dieser Schleife werden alle Tastatureingabe ist inaktiv, mit Ausnahme von Schlüsseln, die auf das Menü zugreifen. Darüber hinaus Befehl weiterhin Kleinbuchstaben über `PreTranslateMessage` , damit der Benutzer eine Tastenkombination drücken und Hilfe zum Befehl "," empfangen.  
  
 Wenn bestimmte stehen Übersetzungen oder Aktionen fügen Sie in der `PreTranslateMessage` Funktion, die UMSCHALT + F1-Hilfe im Modus erfolgen darf keine sollten Sie überprüfen die `m_bHelpMode` Mitglied `CWinApp` vor dem Ausführen dieser Vorgänge. Die `CDialog` Implementierung von `PreTranslateMessage` überprüft dies vor dem Aufruf `IsDialogMessage`, z. B. "Dialogfeld" Navigationstasten auf keine modalen Dialogfelder während UMSCHALT + F1-Modus wird deaktiviert. Darüber hinaus `CWinApp::OnIdle` wird weiterhin aufgerufen werden, während diese Schleife.  
  
 Wenn der Benutzer einen Befehl aus dem Menü auswählt, wird sie als Hilfe zum Befehl "," verarbeitet (über **WM_COMMANDHELP**, siehe unten). Wenn der Benutzer einen sichtbaren Bereich des Fensters Anwendungen klickt, wird eine Identifizierung vorgenommen, ob es mit einem Klick Größenanpassungslogik oder ein Client, auf. `OnContextHelp`Handles-Zuordnung von nicht-klickt auf Clients automatisch auf. Ist er ein Client klicken, anschließend sendet er eine **WM_HELPHITTEST** für das Fenster, das auf die geklickt wurde. Wenn dieses Fensters einen Wert ungleich NULL zurückgibt, ist dieser Wert Hilfestellung bei der als Kontext verwendet. Wenn sie 0 (null), gibt `OnContextHelp` versucht das übergeordnete Fenster (und falls dies fehlschlägt, die das übergeordnete Element und so weiter). Wenn ein Hilfekontext nicht bestimmt werden kann, wird standardmäßig zum Senden einer **ID_DEFAULT_HELP** -Befehl an das Hauptfenster dann (normalerweise) zugeordnet ist `CWinApp::OnHelpIndex`.  
  
## <a name="wmhelphittest"></a>WM_HELPHITTEST  
  
```  
 
afx_msg LRESULT CWnd::OnHelpHitTest(
WPARAM, LPARAM lParam)  
```  
  
 **WM_HELPHITTEST** ist eine MFC-private Windows-Meldung, die durch das aktive Fenster, die während des Modus für UMSCHALT + F1-Hilfe geklickt empfangen wird. Wenn das Fenster diese Nachricht empfängt, gibt einen DWORD-Hilfe-ID für die Verwendung von WinHelp zurück.  
  
 LOWORD(lParam)  
 enthält die X-Achse Gerät Koordinate, in dem mit der Maus relativ zum Clientbereich des Fensters geklickt wurde.  
  
 HIWORD(lParam)  
 enthält die y-Koordinate.  
  
 `wParam`  
 Wird nicht verwendet und wird NULL sein. Wenn der Rückgabewert ungleich NULL ist, wird die WinHelp mit diesem Kontext aufgerufen. Ist der Rückgabewert 0 (null), wird das übergeordnete Fenster abgefragt, um Hilfe zu erhalten.  
  
 In vielen Fällen können Sie Code Treffertests nutzen, die Sie bereits verfügen können. Die Implementierung der **CToolBar::OnHelpHitTest** ein Beispiel für die Behandlung der **WM_HELPHITTEST** Nachricht (der Code nutzt den Treffertest-Code auf Schaltflächen und QuickInfos im verwendet `CControlBar`).  
  
## <a name="mfc-application-wizard-support-and-makehm"></a>Assistentenunterstützung für MFC-Anwendung und MAKEHM  
 Die MFC-Anwendungs-Assistent erstellt die erforderlichen Dateien zum Erstellen einer Hilfedatei (CNT und HPJ-Dateien). Darüber hinaus eine Anzahl von vorgefertigten RTF-Dateien, die von der Microsoft-Hilfe-Compiler akzeptiert werden. Viele Themen abgeschlossen sind, jedoch müssen ggf. bei der jeweiligen Anwendung geändert werden.  
  
 Automatische Erstellung einer Datei "help Zuordnung" wird von einem Dienstprogramm MAKEHM unterstützt. MAKEHM-Hilfsprogramm kann eine Anwendung Ressource übersetzen. H-Datei zu einer Hilfedatei für die Zuordnung. Zum Beispiel:  
  
```  
#define IDD_MY_DIALOG   2000  
#define ID_MY_COMMAND   150  
```  
  
 wird übersetzt werden:  
  
```  
HIDD_MY_DIALOG    0x207d0  
HID_MY_COMMAND    0x10096  
```  
  
 Dieses Format ist kompatibel mit den Hilfecompiler-Funktion, die Kontext-IDs (die Zahlen auf der rechten Seite) mit Thema Namen (die Symbole auf der linken Seite) zuordnet.  
  
 Der Quellcode für MAKEHM steht in der MFC-Programmierung Utilities-Beispiel [MAKEHM](../visual-cpp-samples.md).  
  
## <a name="adding-help-support-after-running-the-mfc-application-wizard"></a>Nach dem Ausführen des MFC-Assistenten zum Hinzufügen von Hilfe und Unterstützung  
 Die beste Methode zum Hinzufügen von Hilfe für Ihre Anwendung ist auf die Option "Kontextbezogene Hilfe" auf der Seite Erweiterte Funktionen des Assistenten für MFC-Anwendung vor dem Erstellen der Anwendungsstatus aktivieren. Auf diese Weise die MFC-Anwendung-Assistenten automatisch hinzugefügt erforderlichen Meldungszuordnungseinträge auf Ihre `CWinApp`-abgeleitete Klasse, um Hilfe zu unterstützen.  
  
## <a name="help-on-message-boxes"></a>Hilfe zur Meldungsfelder  
 Hilfe in den Meldungsfeldern (manchmal als "Warnungen" bezeichnet) wird unterstützt, über die `AfxMessageBox` -Funktion, die einen Wrapper für die `MessageBox` Windows-API.  
  
 Es gibt zwei Versionen des `AfxMessageBox`, eine für die Verwendung mit einem Zeichenfolgen-ID und ein anderes für die Verwendung mit einem Zeiger auf Zeichenfolge (`LPCSTR`):  
  
```  
int AFXAPI AfxMessageBox(LPCSTR lpszText,
    UINT nType,
    UINT nIDHelp);

int AFXAPI AfxMessageBox(UINT nIDPrompt,
    UINT nType,
    UINT nIDHelp);
```  
  
 In beiden Fällen besteht eine optionale Hilfe-ID.  
  
 Im ersten Fall ist die Standardeinstellung für nIDHelp 0, was keine Hilfe für das Meldungsfeld angibt. Wenn der Benutzer F1 drückt, während z. B. Nachricht Feld aktiv ist, erhält der Benutzer keine Hilfe (selbst wenn die Anwendung Help unterstützt). Wenn dies nicht erwünscht ist, sollte eine Hilfe-ID für nIDHelp bereitgestellt werden.  
  
 Im zweiten Fall wird der Standardwert für nIDHelp-1 und bedeutet, dass die Hilfe-ID nIDPrompt identisch ist. Hilfe funktionieren nur, wenn die Anwendung Help aktiviert, natürlich ist). Sie sollten 0 für nIDHelp angeben, wenn Sie möchten, dass das Meldungsfeld keine Hilfe und Unterstützung verfügen. Soll die Nachricht an die Hilfe aktiviert ist, werden jedoch eine unterschiedliche Hilfe-ID als nIDPrompt verwendet werden soll, geben Sie einen positiven Wert einfach für andere nIDPrompt nIDHelp.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

