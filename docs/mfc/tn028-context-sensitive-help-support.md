---
title: 'TN028: Kontextbezogene Hilfe Support'
ms.date: 11/04/2016
f1_keywords:
- vc.help
helpviewer_keywords:
- context-sensitive Help [MFC], MFC applications
- TN028
- resource identifiers, context-sensitive Help
ms.assetid: 884f1c55-fa27-4d4c-984f-30907d477484
ms.openlocfilehash: 5689e314c2ba94068619a066e5f458e06819b2b7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58773475"
---
# <a name="tn028-context-sensitive-help-support"></a>TN028: Kontextbezogene Hilfe Support

In diesem Hinweis werden die Regeln für die Zuweisung von Hilfe Kontexten-IDs und andere Probleme Hilfe in MFC beschrieben. Kontextbezogene Hilfe-Support muss es sich um die Hilfe-Compiler, der in Visual C++ verfügbar ist.

> [!NOTE]
>  Zusätzlich zur Implementierung kontextbezogene Hilfe, die WinHelp verwenden, unterstützt MFC auch HTML-Hilfe. Weitere Informationen zu dieser Unterstützung und die Programmierung mit HTML-Hilfe, finden Sie unter [HTML-Hilfe: Kontextbezogene Hilfe für Programme](../mfc/html-help-context-sensitive-help-for-your-programs.md).

## <a name="types-of-help-supported"></a>Hilfetypen unterstützt

Es gibt zwei Arten der kontextbezogenen Hilfe in Windows-Anwendungen implementiert. Die erste, bezeichnet als "F1-Hilfe" umfasst die WinHelp mit den geeigneten Kontext basierend auf dem derzeit aktiven Objekt starten. Die zweite ist "UMSCHALT + F1". In diesem Modus ändert sich des Mauszeigers auf den Hilfecursor, und klicken Sie auf ein Objekt auf der Benutzer wird. An diesem Punkt wird die WinHelp gestartet, um Hilfe für das Objekt zu ermöglichen, die auf der Benutzer geklickt hat.

Die Microsoft Foundation Classes implementieren beide der folgenden Formen der Hilfe. Darüber hinaus unterstützt das Framework zwei einfache Hilfebefehle ein, den Index und die Hilfe verwenden.

## <a name="help-files"></a>Hilfedateien

Microsoft Foundation Classes gehen davon aus einer einzelnen Hilfedatei. Diese Hilfedatei müssen den gleichen Namen und Pfad wie die Anwendung. Wenn die ausführbare Datei C:\MyApplication\MyHelp.exe ist muss die Datei z. B. C:\MyApplication\MyHelp.hlp sein. Den Pfad durch Festlegen der *M_pszHelpFilePath* Membervariable der der [CWinApp-Klasse](../mfc/reference/cwinapp-class.md).

## <a name="help-context-ranges"></a>Hilfe-Kontext-Bereiche

Die standardmäßige Implementierung von MFC ist erforderlich, ein Programm, um einige Regeln bezüglich der Zuordnung von Hilfekontext IDs entsprechen. Diese Regeln sind, einen Bereich von IDs, die bestimmte Steuerelemente zugeordnet wird. Sie können diese Regeln durch die Bereitstellung von verschiedenen Implementierungen der verschiedenen Hilfe-bezogenen Memberfunktionen überschreiben.

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

## <a name="simple-help-commands"></a>Einfach "Help"-Befehle

Es gibt zwei einfache Help-Befehle, die von der Microsoft Foundation Classes implementiert werden:

- ID_HELP_INDEX, die von implementiert ist [CWinApp::OnHelpIndex](../mfc/reference/cwinapp-class.md#onhelpindex)

- ID_HELP_USING, die von implementiert ist [CWinApp::OnHelpUsing](../mfc/reference/cwinapp-class.md#onhelpusing)

Der erste Befehl zeigt die Hilfe-Index für die Anwendung. Das zweite zeigt die Hilfe zur Verwendung von der WinHelp-Anwendung.

## <a name="context-sensitive-help-f1-help"></a>Kontextbezogene Hilfe (F1-Hilfe)

Die F1-Taste wird durch eine Zugriffstaste, die in der Tabelle mit Zugriffstasten wird das Hauptfenster platziert in der Regel an einen Befehl mit einer ID von ID_HELP übersetzt. ID_HELP-Befehl kann auch über eine Schaltfläche mit einer ID ID_HELP auf der wichtigsten Fenster oder Dialogfeld generiert werden.

Unabhängig davon, wie die ID_HELP-Befehl generiert wird wird sie als normale Befehl weitergeleitet, bis einen Befehlshandler erreicht. Weitere Informationen über die MFC-Befehlsrouting Architektur finden Sie unter [technischen Hinweis 21](../mfc/tn021-command-and-message-routing.md). Wenn die Anwendung Help aktiviert wurde, wird der ID_HELP-Befehl vom behandelt [CWinApp::OnHelp](../mfc/reference/cwinapp-class.md#onhelp). Das Anwendungsobjekt empfängt die hilfemeldung an und leitet dann den Befehl entsprechend. Dies ist erforderlich, da die Standard-Befehlsrouting nicht zur Bestimmung der spezifischsten Kontexts geeignet ist.

`CWinApp::OnHelp` versucht, WinHelp in der folgenden Reihenfolge zu starten:

1. Überprüft, ob eine aktive `AfxMessageBox` rufen Sie mit der eine Hilfe-ID. Wenn ein Meldungsfeld derzeit aktiv ist, wird die WinHelp mit dem Kontext entsprechenden in dieser MessageBox gestartet.

1. Sendet eine Nachricht WM_COMMANDHELP des aktiven Fensters. Wenn das Fenster von WinHelp starten nicht reagiert, wird dieselbe Nachricht klicken Sie dann auf den übergeordneten Elementen dieses Fenster gesendet, bis die Nachricht verarbeitet wird oder das aktuelle Fenster ein Fenster auf oberster Ebene ist.

1. Sendet einen ID_DEFAULT_HELP-Befehl an das Hauptfenster. Dadurch wird die standardmäßige Hilfe aufgerufen. Mit diesem Befehl wird in der Regel zugeordnet `CWinApp::OnHelpIndex`.

Um die Standard-ID Basiswerte (z. B. 0 x 10000 für Befehle und 0 x 20000 für Ressourcen wie z. B. Dialogfeldern) Global zu überschreiben, sollte die Anwendung überschreiben [CWinApp::WinHelp](../mfc/reference/cwinapp-class.md#winhelp).

Um überschreiben diese Funktion und die Möglichkeit, dass ein Hilfekontext bestimmt wird, sollten Sie die WM_COMMANDHELP-Meldung zu behandeln. Sie möchten möglicherweise spezifische Hilfe routing bereitstellen als das Framework bietet, wie es nur so umfassend wie die aktuellen untergeordneten MDI-Fensters wird. Sie sollten auch spezifische Hilfe für ein bestimmtes Fenster oder Dialogfeld möglicherweise basierend auf den aktuellen internen Zustand des Objekts oder das aktive Steuerelement im Dialogfeld bereitzustellen.

## <a name="wmcommandhelp"></a>WM_COMMANDHELP

```

afx_msg LRESULT CWnd::OnCommandHelp(WPARAM wParam, LPARAM lParam)
```

WM_COMMANDHELP ist eine private Windows-MFC-Nachricht, die durch das aktive Fenster empfangen wird, wenn Hilfe angefordert wird. Wenn das Fenster auf diese Nachricht erhält, kann es aufrufen `CWinApp::WinHelp` mit Kontext, der interne Zustand des Fensters entspricht.

*lParam*<br/>
Enthält den derzeit verfügbaren Hilfekontext. *lParam* ist 0 (null), wenn keine Hilfekontext ermittelt wurde. Eine Implementierung von `OnCommandHelp` können die Kontext-ID in *lParam* zum Bestimmen von eines anderen Kontexts oder es können nur übergeben `CWinApp::WinHelp`.

*wParam*<br/>
Wird nicht verwendet und ist 0 (null).

Wenn die `OnCommandHelp` Funktionsaufrufe `CWinApp::WinHelp`, sollte zurückgegeben **"true"**. Zurückgeben von **"true"** beendet die Weiterleitung von diesen Befehl aus, für andere Klassen und anderen Fenstern.

## <a name="help-mode-shiftf1-help"></a>Hilfemodus (UMSCHALT + F1-Hilfe)

Dies ist die zweite Form der kontextbezogenen Hilfe. In diesem Modus wird in der Regel durch Drücken von UMSCHALT + F1 oder über der Symbolleiste von/eingegeben. Sie wird als Befehl (ID_CONTEXT_HELP) implementiert. Der Message-Filter-Hook wird nicht zum Übersetzen mit diesem Befehl bei der ein modales Dialogfeld oder Menü aktiv ist, daher mit diesem Befehl ist nur für den Benutzer verfügbar, wenn die Anwendung die Haupt-Meldungsverteilschleife ausgeführt wird (`CWinApp::Run`).

Nach der Eingabe dieser Modus, wird der Hilfe-Mauszeiger über alle Bereiche der Anwendung angezeigt, auch wenn die Anwendung normalerweise einen eigene Cursor für den entsprechenden Bereich (z. B. Größenanpassungsrahmens um das Fenster ") angezeigt wird. Der Benutzer kann die Maus oder Tastatur zu verwenden, um einen Befehl auswählen. Anstatt den Befehl auszuführen, wird die Hilfe zum Befehl "," angezeigt. Außerdem kann der Benutzer ein sichtbares Objekt auf dem Bildschirm z. B. eine Schaltfläche auf der Symbolleiste klicken, und Hilfe für das Objekt angezeigt wird. In diesem Modus Hilfe erfolgt über `CWinApp::OnContextHelp`.

Während der Ausführung dieser Schleife werden alle Tastatureingaben ist inaktiv, mit Ausnahme der Schlüssel, die das Menü zuzugreifen. Darüber hinaus Befehl Übersetzung erfolgt weiterhin über `PreTranslateMessage` , damit Benutzer eine Tastenkombination drücken, und erhalten Sie Hilfe zum Befehl ",".

Wenn bestimmte stehen Übersetzungen oder Aktionen platzieren, in der `PreTranslateMessage` -Funktion, die während der Modus der UMSCHALT + F1-Hilfe, stattfinden sollte nicht sollten Sie überprüfen die *M_bHelpMode* Mitglied `CWinApp` vor dem Ausführen, die Vorgänge. Die `CDialog` Implementierung `PreTranslateMessage` überprüft dies vor dem Aufruf `IsDialogMessage`, z. B. Dadurch wird "Dialogfeld" Navigationstasten auf nicht modale Dialogfelder UMSCHALT + F1 Modus deaktiviert. Darüber hinaus `CWinApp::OnIdle` wird trotzdem aufgerufen, während diese Schleife.

Wenn der Benutzer einen Befehl im Menü auswählt, wird sie als Hilfe zum Befehl "," behandelt (über WM_COMMANDHELP, siehe unten). Wenn der Benutzer einen sichtbaren Bereich des Fensters Anwendungen klickt, erfolgt eine Entscheidung treffen, gibt an, ob es sich um einen nicht-Klick oder ein Client, auf handelt. `OnContextHelp` Handles-Zuordnung von nicht-Client klickt automatisch auf Clients Klicks. Wenn es sich um einen Client, auf handelt, sendet er klicken Sie dann eine WM_HELPHITTEST an das Fenster, das auf die geklickt wurde an. Wenn das Fenster einen Wert ungleich NULL zurückgibt, wird dieser Wert als den Kontext Hilfe verwendet. Wenn 0 (null), gibt `OnContextHelp` versucht das übergeordnete Fenster (und falls dies fehlschlägt, seinem übergeordneten Element und so weiter). Wenn ein Hilfekontext nicht bestimmt werden kann, wird standardmäßig im Hauptfenster ein ID_DEFAULT_HELP-Befehl an der anschließend (normalerweise) zugeordnet ist `CWinApp::OnHelpIndex`.

## <a name="wmhelphittest"></a>WM_HELPHITTEST

```

afx_msg LRESULT CWnd::OnHelpHitTest(
WPARAM, LPARAM lParam)
```

WM_HELPHITTEST ist eine MFC-privaten Windows-Meldung, die durch das aktive Fenster, die während der Modus der UMSCHALT + F1-Hilfe geklickt empfangen wird. Wenn das Fenster auf diese Nachricht empfängt, gibt er eine **DWORD** Hilfe-ID für die Verwendung durch WinHelp.

LOWORD(lParam) enthält die x-Gerät-Koordinate, in Bezug auf den Clientbereich des Fensters mit der Maus geklickt wurde.

HIWORD(lParam) enthält die y-Koordinate.

*wParam*<br/>
Wird nicht verwendet und ist 0 (null). Wenn der Rückgabewert ungleich NULL ist, wird die WinHelp mit diesen Kontext aufgerufen. Wenn der Rückgabewert 0 (null) ist, wird das übergeordnete Fenster Hilfe abgefragt.

In vielen Fällen können Sie die Treffertests Code nutzen, die Sie bereits verfügen können. Die Implementierung der `CToolBar::OnHelpHitTest` ein Beispiel Behandlung der WM_HELPHITTEST-Meldung (der Code nutzt den Treffertest-Code, der auf Schaltflächen und QuickInfos im verwendet `CControlBar`).

## <a name="mfc-application-wizard-support-and-makehm"></a>Assistentenunterstützung für MFC-Anwendung und MAKEHM

Die MFC-Anwendungs-Assistent erstellt die erforderlichen Dateien zum Erstellen einer Hilfedatei (CNT und HPJ-Dateien). Darüber hinaus zahlreiche vordefinierte RTF-Dateien, die vom Microsoft-Hilfecompiler akzeptiert werden. Viele der Themen, die abgeschlossen sind, aber einige kann für die spezifische Anwendung geändert werden müssen.

Automatische Erstellung einer Datei "Zuordnung help" wird durch ein Dienstprogramm namens MAKEHM unterstützt. Das Hilfsprogramm MAKEHM kann Ressourcen von einer Anwendung übersetzen. H-Datei zu einer Hilfedatei für die Zuordnung. Zum Beispiel:

```
#define IDD_MY_DIALOG   2000
#define ID_MY_COMMAND   150
```

wird in übersetzt:

```
HIDD_MY_DIALOG    0x207d0
HID_MY_COMMAND    0x10096
```

Dieses Format ist kompatibel mit der Hilfe-Compiler-Funktion, die Kontext-IDs (die Zahlen auf der rechten Seite) mit Themennamen (die Symbole auf der linken Seite) zuordnet.

Der Quellcode für MAKEHM finden Sie in der MFC-Programmierung Utilities-Beispiel [MAKEHM](../overview/visual-cpp-samples.md).

## <a name="adding-help-support-after-running-the-mfc-application-wizard"></a>Hilfe Support nach Ausführen des Assistenten der MFC-Anwendung hinzufügen

Überprüfen Sie die Option "Kontextbezogene Hilfe" auf der Seite "Erweiterte Features" des Assistenten für MFC-Anwendung vor dem Erstellen Ihrer Anwendung ist die beste Möglichkeit, Hilfe zu Ihrer Anwendung hinzufügen werden. Auf diese Weise den MFS-Anwendungsassistenten automatisch hinzugefügt, die erforderlichen Meldungszuordnungseinträge Ihre `CWinApp`-abgeleitete Klasse, um Hilfe zu unterstützen.

## <a name="help-on-message-boxes"></a>Hilfe zur Meldungsfelder

Hilfe in den Meldungsfeldern (manchmal als "Warnungen" bezeichnet) wird unterstützt, über die `AfxMessageBox` -Funktion, die einen Wrapper für die `MessageBox` Windows-API.

Es gibt zwei Versionen der `AfxMessageBox`, eine für die Verwendung mit einem Zeichenfolgen-ID und ein anderes für die Verwendung mit einem Zeiger auf Zeichenfolge (`LPCSTR`):

```
int AFXAPI AfxMessageBox(LPCSTR lpszText,
    UINT nType,
    UINT nIDHelp);

int AFXAPI AfxMessageBox(UINT nIDPrompt,
    UINT nType,
    UINT nIDHelp);
```

In beiden Fällen besteht eine optionale Hilfe-ID.

Im ersten Fall ist die Standardeinstellung für nIDHelp 0 (null) und keine Hilfe zu diesem Meldungsfeld angibt. Wenn der Benutzer F1 drückt, während z. B. Message Box aktiv ist, erhält der Benutzer keine Hilfe (selbst wenn die Anwendung die Hilfefunktion unterstützt). Wenn dies nicht erwünscht ist, sollte eine Hilfe-ID für nIDHelp angegeben werden.

Im zweiten Fall ist der Standardwert für nIDHelp-1 und gibt an, dass die Hilfe-ID nIDPrompt identisch ist. Hilfe funktioniert nur, wenn die Anwendung Help-fähige, natürlich ist). Sie sollten für nIDHelp 0 angeben, wenn Sie möchten, dass das Meldungsfeld keine Hilfe unterstützt. Soll die Nachricht Hilfe aktiviert ist, sondern eine andere Hilfe-ID als nIDPrompt wünschen, geben Sie einfach einen positiven Wert für die anderen nIDPrompt nIDHelp.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
