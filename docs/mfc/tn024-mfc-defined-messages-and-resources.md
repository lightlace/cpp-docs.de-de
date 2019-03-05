---
title: 'TN024: MFC-definierte Meldungen und Ressourcen'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.messages
helpviewer_keywords:
- resources [MFC]
- Windows messages [MFC], MFC-defined
- messages [MFC], MFC
- TN024
ms.assetid: c65353ce-8096-454b-ad22-1a7a1dd9a788
ms.openlocfilehash: 029177821d37d5d26abe0b39ea1581e8a5ad602b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57278131"
---
# <a name="tn024-mfc-defined-messages-and-resources"></a>TN024: MFC-definierte Meldungen und Ressourcen

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

In diesem Hinweis wird beschrieben, die interne Windows-Meldungen und Ressourcenformate, die von MFC verwendete. Diese Informationen wird erläutert, die Implementierung des Frameworks und hilft Ihnen bei der Ihre Anwendung zu debuggen. Für die abenteuerlicher, obwohl alle diese Informationen nicht offiziell unterstützt, ist können Sie einige dieser Informationen für fortgeschrittene Implementierungen verwenden.

Dieser Hinweis enthält die privaten Implementierungsdaten MFC; der gesamte Inhalt werden in der Zukunft können geändert. Private MFC-Windows-Meldungen Bedeutung im Bereich nur eine Anwendung haben, jedoch werden in Zukunft geändert, um eine systemweite Nachrichten enthalten.

Der private Bereich von MFC-Windows-Meldungen und Ressourcentypen werden im Bereich von reservierten "System" von Microsoft Windows reserviert. Derzeit werden nicht alle Zahlen in den Bereichen verwendet werden, und klicken, in Zukunft neue Zahlen im Bereich verwendet werden können. Die aktuell verwendeten Zahlen können geändert werden.

Private MFC-Windows werden Nachrichten im Bereich von 0x360-0x37F >.

MFC-private-Ressource, die Typen im Bereich von 0xF0 sind -> 0xFF.

**Private Windows-MFC-Meldungen**

Diese Windows-Meldungen werden anstelle von virtuellen Funktionen von C++ verwendet, in denen ist relativ losen Kopplung zwischen Windows-Objekte und erforderlich, in denen eine virtuelle Funktion von C++ nicht geeignet wären.

Diese privaten Windows-Meldungen und zugeordnete Parameter Strukturen werden in den privaten MFC-Headerdateien deklariert "AFXPRIV. H ". Werden gewarnt, dass sämtlicher Code, der dieser Header enthält zu nicht dokumentiertem Verhalten führen und wahrscheinlich zerstört in zukünftigen Versionen von MFC verlassen kann.

Im seltenen Fall, die eine der folgenden Meldungen behandeln müssen verwenden Sie die ON_MESSAGE-Map-Makro und verarbeiten die Nachricht in das generische LRESULT/WPARAM/LPARAM-Format.

**WM_QUERYAFXWNDPROC**

Diese Nachricht wird in einem Fenster gesendet, der erstellt wird. Dies wird als eine Methode zum Ermitteln, ob der WndProc ist sehr früh im Prozess gesendet **fxWndProc. AfxWndProc** returns 1.

|||
|-|-|
|wParam|Nicht verwendet|
|lParam|Nicht verwendet|
|gibt|1, wenn die Verarbeitung durch **fxWndProc**|

**WM_SIZEPARENT**

Diese Meldung wird durch ein Rahmenfenster an seine unmittelbar untergeordneten Elemente gesendet, während der Größenänderung (`CFrameWnd::OnSize` Aufrufe `CFrameWnd::RecalcLayout` Aufrufen `CWnd::RepositionBars`) um die Steuerleisten auf der Seite des Rahmens um neu zu positionieren. Die AFX_SIZEPARENTPARAMS-Struktur enthält die aktuellen verfügbaren Clientrechteck des übergeordneten und einem HDWP (der NULL sein kann) mit dem aufzurufenden `DeferWindowPos` Neuzeichnen minimieren.

|||
|-|-|
|wParam|Nicht verwendet|
|lParam|Adresse einer AFX_SIZEPARENTPARAMS-Struktur|
|gibt|Nicht verwendet (0)|

Ignorieren die Nachricht gibt an, dass das Fenster im Layout schleifenspezifischen nicht.

**WM_SETMESSAGESTRING**

Diese Nachricht wird zu einem Rahmenfenster gesendet, Fragen sie zum Aktualisieren der in der Statusleiste an. Eine Zeichenfolge-ID oder eine LPCSTR kann angegeben (aber nicht beide) sein.

|||
|-|-|
|wParam|Zeichenfolgen Sie-ID (oder 0 (null))|
|lParam|LPCSTR für die Zeichenfolge (oder NULL)|
|gibt|Nicht verwendet (0)|

**WM_IDLEUPDATECMDUI**

Diese Nachricht wird in der Zeit im Leerlauf gesendet, die Leerlauf-Ablaufzeitpunkt-Aktualisierung der Update-Befehlshandler Benutzeroberfläche zu implementieren. Wenn das Fenster (normalerweise eine Steuerleiste) die Nachricht verarbeitet, erstellt eine `CCmdUI` Objekt (oder ein Objekt einer abgeleiteten Klasse), und rufen Sie `CCmdUI::DoUpdate` für jedes der im Fenster "Elemente". Dies wird wiederum eine ON_UPDATE_COMMAND_UI-Handler für die Objekte in der Kette der Befehlshandler geprüft.

|||
|-|-|
|wParam|BOOL bDisableIfNoHandler|
|lParam|Nicht verwendet (0)|
|gibt|Nicht verwendet (0)|

*bDisableIfNoHandler* das UI-Objekt zu deaktivieren, ist es weder eine ON_UPDATE_COMMAND_UI noch ein ON_COMMAND-Handler ungleich NULL ist.

**WM_EXITHELPMODE**

Diese Nachricht wird gesendet, um eine `CFrameWnd` , beenden Sie kontextbezogene Hilfe Modus. Der Empfang dieser Nachricht beendet die modale Größenanpassungsschleife zunächst `CFrameWnd::OnContextHelp`.

|||
|-|-|
|wParam|Nicht verwendet (0)|
|lParam|Nicht verwendet (0)|
|gibt|Nicht verwendet|

**WM_INITIALUPDATE**

Diese Nachricht wird durch die Dokumentvorlage für alle Nachfolger Rand eines Rahmenfensters gesendet, wenn es für sie zu ihrer Erstversion des Updates sicher ist. Sie ordnet einen Aufruf von `CView::OnInitialUpdate` kann jedoch verwendet werden in anderen `CWnd`-abgeleitete Klassen für die anderen One-Shot-Aktualisierung.

|||
|-|-|
|wParam|Nicht verwendet (0)|
|lParam|Nicht verwendet (0)|
|gibt|Nicht verwendet (0)|

**WM_RECALCPARENT**

Diese Nachricht wird von einer Ansicht an das übergeordnete Fenster gesendet (über abgerufen `GetParent`) erzwingen eine neuberechnung Layout (in der Regel ruft das übergeordnete Element `RecalcLayout`). Hiermit wird in der OLE-serveranwendungen, wo es notwendig, für den Frame Größe zu vergrößern, wächst die Gesamtgröße der Ansicht ist.

Wenn das übergeordnete Fenster diese Nachricht verarbeitet muss "true" zurück und geben Sie die RECT lParam die neue Größe des Clientbereichs übergeben. Hiermit wird `CScrollView` ordnungsgemäß behandelt Bildlaufleisten (setzen Sie dann auf der Außenseite des Fensters nach dem Hinzufügen) wird ein Serverobjekt Wenn direkt aktiviert.

|||
|-|-|
|wParam|Nicht verwendet (0)|
|lParam|LPRECT-RectClient kann NULL sein.|
|gibt|TRUE, wenn neue Client-Bildgröße zurückgegeben FALSE hat, andernfalls|

**WM_SIZECHILD**

Diese Nachricht wird gesendet, indem `COleResizeBar` auf sein Besitzerfenster (über `GetOwner`) Wenn der Benutzer die Größe ändert der Größenänderung-Leiste mit die Handles zur Größenänderung. `COleIPFrameWnd` Diese Nachricht antwortet, indem versucht wird, um das Rahmenfenster neu zu positionieren, wenn der Benutzer angefordert hat.

Das neue Rechteck, in Clientkoordinaten relativ zu das Rahmenfenster der Größenänderung-Leiste mit angegeben wird auf lParam gezeigt.

|||
|-|-|
|wParam|Nicht verwendet (0)|
|lParam|LPRECT rectNew|
|gibt|Nicht verwendet (0)|

**WM_DISABLEMODAL**

Diese Nachricht wird gesendet, um alle Popup-Fenster, die im Besitz von einem Rahmenfenster, das deaktiviert wird. Das Rahmenfenster verwendet das Ergebnis, um zu bestimmen, ob das Popup-Fenster zu deaktivieren.

Sie können dies verwenden, spezielle Verarbeitung in die Popup-Fenster ausführen, wenn der Frame in einen modalen Zustand wechselt oder um zu verhindern, dass bestimmte Popupfenster deaktiviert. QuickInfos verwenden diese Nachricht, um sich selbst zu zerstören, wenn das Rahmenfenster in einem modalen Zustand befindet, z. B. aufgenommen wird.

|||
|-|-|
|wParam|Nicht verwendet (0)|
|lParam|Nicht verwendet (0)|
|gibt|Wert ungleich NULL **nicht** deaktivieren Sie das Fenster, 0 gibt an, das Fenster wird deaktiviert|

**WM_FLOATSTATUS**

Diese Nachricht wird gesendet, um alle Popup-Fenster ein Rahmenfenster Besitz, wenn der Frame entweder aktiviert oder, die von einem anderen Fenster von Frames der obersten Ebene deaktiviert. Hiermit wird durch die Implementierung von MFS_SYNCACTIVE in `CMiniFrameWnd`, um die Aktivierung dieser Popupfenster mit der Aktivierung des das Rahmenfenster der obersten Ebene synchron zu halten.

|||
|-|-|
|wParam|Ist eine der folgenden Werte:<br /><br /> FS_SHOW<br /><br /> FS_HIDE<br /><br /> FS_ACTIVATE<br /><br /> FS_DEACTIVATE<br /><br /> FS_ENABLEFS_DISABLE<br /><br /> FS_SYNCACTIVE|
|lParam|Nicht verwendet (0)|

Der Rückgabewert muss ungleich NULL, wenn FS_SYNCACTIVE Satz und die Fenster synchronisiert seine Aktivierung mit übergeordneten Rahmens. `CMiniFrameWnd` ungleich NULL zurück, wenn die Formatvorlage auf MFS_SYNCACTIVE festgelegt ist.

Weitere Informationen finden Sie auf die Implementierung der `CMiniFrameWnd`.

## <a name="wmactivatetoplevel"></a>WM_ACTIVATETOPLEVEL

Diese Nachricht wird an ein Fenster der obersten Ebene gesendet, wenn ein Fenster in der Gruppe"der obersten Ebene" aktiviert oder deaktiviert ist. Ein Fenster ist Teil einer Gruppe der obersten Ebene aus, wenn ein Fenster der obersten Ebene (ohne übergeordnete oder Besitzer), ist, oder sie ist im Besitz von solches Fenster. Diese Meldung ist ähnlich verwendet wie WM_ACTIVATEAPP, aber funktioniert in Situationen, in denen Windows, die zu verschiedenen Prozessen gehören sind, in einer einzigen Fensterhierarchie (häufig in OLE-Anwendungen) kombiniert.

## <a name="wmcommandhelp-wmhelphittest-wmexithelpmode"></a>WM_COMMANDHELP, WM_HELPHITTEST, WM_EXITHELPMODE

Diese Nachrichten werden in der Implementierung der kontextbezogenen Hilfe verwendet. Näheres [technischer Hinweis 28](../mfc/tn028-context-sensitive-help-support.md) für Weitere Informationen.

## <a name="mfc-private-resource-formats"></a>MFC-Private-Resource-Formate

MFC definiert aktuell zwei private Ressourcenformate: RT_TOOLBAR und RT_DLGINIT.

## <a name="rttoolbar-resource-format"></a>RT_TOOLBAR-Ressource-Format

Die Standardsymbolleiste von AppWizard angegeben basieren auf eine benutzerdefinierte RT_TOOLBAR-Ressource, die in MFC 4.0 eingeführt wurde. Sie können diese Ressource, die mit der Symbolleisten-Editor bearbeiten.

## <a name="rtdlginit-resource-format"></a>RT_DLGINIT Ressourcenformat

Eine MFC-private Ressource-Format wird verwendet, um zusätzliche Dialogfeld Initialisierungsinformationen zu speichern. Dies schließt den Anfangssatz von Zeichenfolgen in einem Kombinationsfeld gespeichert. Das Format dieser Ressource dient nicht manuell bearbeitet werden, aber von Visual C++ verarbeitet wird.

Visual C++ und diese Ressource RT_DLGINIT sind nicht erforderlich, die entsprechenden Funktionen von MFC verwendet, da es sich um API-Alternative zu mithilfe der Informationen in der Ressource. Mit Visual C++ ist es viel einfacher zu schreiben, verwalten und Ihre Anwendung wird langfristig zu übersetzen.

Die grundlegende Struktur einer Ressource RT_DLGINIT lautet wie folgt aus:

```
+---------------+    \
| Control ID    |   UINT             |
+---------------+    |
| Message #     |   UINT             |
+---------------+    |
|length of data |   DWORD            |
+---------------+    |   Repeated
|   Data        |   Variable Length  |   for each control
|   ...         |   and Format       |   and message
+---------------+    /
|     0         |   BYTE
+---------------+
```

Ein wiederholter Abschnitt enthält die Steuerelement-ID zum Senden der Nachricht, die Nachricht # variabler Länge der Daten zu senden (eine normale Windows-Nachricht). Die Windows-Nachricht, die in einem Formular gesendet wird:

```
SendDlgItemMessage(<Control ID>, <Message #>, 0, &<Data>);
```

Dies ist ein sehr Allgemeines Format, können alle Windows-Nachrichten und den Dateninhalt. Die Ressourcen-Editor von Visual C++ und MFC unterstützen nur eine begrenzte Teilmenge der Windows-Meldungen: CB_ADDSTRING für die anfängliche Liste-Optionen für Kombinationsfelder (die Daten ist eine Zeichenfolge).

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
