---
title: 'TN024: MFC-definierte Meldungen und Ressourcen | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.messages
dev_langs: C++
helpviewer_keywords:
- resources [MFC]
- Windows messages [MFC], MFC-defined
- messages [MFC], MFC
- TN024
ms.assetid: c65353ce-8096-454b-ad22-1a7a1dd9a788
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 17aadfd089d6917cd8cded239287034026ff7ad3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tn024-mfc-defined-messages-and-resources"></a>TN024: MFC-definierte Meldungen und Ressourcen
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis wird beschrieben, die interne Windows-Meldungen und Ressourcenformate, die von MFC verwendet. Diese Informationen wird die Implementierung des Frameworks erläutert und hilft Ihnen beim Debuggen Ihrer Anwendungsstatus. Für die eindrucksvolle, obwohl alle diese Informationen nicht offiziell unterstützt, ist möglicherweise Sie einige dieser Informationen für fortgeschrittene Implementierungen verwenden.  
  
 Dieser Hinweis enthält MFC privater Implementierungsdetails. alle Inhalte werden in der Zukunft gerechnet. MFC private Windows-Meldungen im Rahmen einer Anwendung nur eine Bedeutung haben, jedoch werden in Zukunft ändern, um eine systemweite Nachrichten enthalten.  
  
 Der Bereich von MFC private Windows-Meldungen und Ressourcentypen werden im Bereich von reservierten "System" von Microsoft Windows reserviert. Derzeit nicht alle Zahlen in den Bereichen verwendet werden, und in der Zukunft neue Zahlen im Bereich verwendet werden können. Die aktuell verwendeten Zahlen möglicherweise geändert werden.  
  
 -> 0x37F private MFC-Fenster, die Nachrichten im Bereich 0x360 befinden.  
  
 Private MFC-Ressource, die Typen im Bereich 0xF0 -> 0xFF.  
  
 **MFC-Private Windows-Meldungen**  
  
 Diese Windows-Nachrichten werden verwendet, anstelle von C++ virtuelle Funktionen, in dem ist relativ losen Kopplung zwischen Windows-Objekte und erforderlich, in denen eine virtuelle Funktion von C++ nicht geeignet wäre.  
  
 Diese privaten Windows-Meldungen und zugeordnete Parameter Strukturen deklariert werden, in der MFC-private-Header "AFXPRIV. H ". Darüber informiert werden, dass sämtlicher Code, der diesen Header enthält wahrscheinlich zerstört zu nicht dokumentiertem Verhalten führen in zukünftigen MFC-Versionen der vertrauenden Seite werden kann.  
  
 Im seltenen Fall belegen eine der folgenden Meldungen zu verarbeiten, sollten Sie verwenden die `ON_MESSAGE` Zuordnungsmakros Nachricht und verarbeitet die Nachricht in der generischen LRESULT/WPARAM/LPARAM-Format.  
  
 **WM_QUERYAFXWNDPROC**  
  
 Diese Meldung wird in einem Fenster gesendet, der erstellt wird. Dies wird als Methode zur Bestimmung der WndProc ist Teil des Erstellungsprozesses in sehr frühen gesendet **fxWndProc. FxWndProc** gibt 1 zurück.  
  
|||  
|-|-|  
|wParam|Nicht verwendet|  
|lParam|Nicht verwendet|  
|gibt|1, wenn die Verarbeitung durch **fxWndProc**|  
  
 **WM_SIZEPARENT**  
  
 Diese Meldung wird von einem Rahmenfenster, die direkt untergeordneten Elemente gesendet, während der Größenänderung (**CFrameWnd::OnSize** Aufrufe `CFrameWnd::RecalcLayout` welche Aufrufe `CWnd::RepositionBars`) an die Steuerleisten auf der Seite des Rahmens um neu positionieren. Die **AFX_SIZEPARENTPARAMS** Struktur enthält aktuelle verfügbar Clientrechteck des übergeordneten Elements und ein HDWP (die NULL sein kann), mit der aufzurufenden `DeferWindowPos` Neuzeichnen minimieren.  
  
|||  
|-|-|  
|wParam|Nicht verwendet|  
|lParam|Adresse der ein **AFX_SIZEPARENTPARAMS** Struktur|  
|gibt|Nicht verwendet (0)|  
  
 Ignorieren der Meldung gibt an, dass das Fenster im Layout schleifenspezifischen nicht.  
  
 **WM_SETMESSAGESTRING**  
  
 Diese Nachricht wird an ein Framefenster gesendet, Fragen sie zum Aktualisieren der Nachricht Position in der Statusleiste. Ein Zeichenfolgen-ID oder eine LPCSTR kann angegeben (aber nicht beide) sein.  
  
|||  
|-|-|  
|wParam|Zeichenfolge-ID (oder 0 (null))|  
|lParam|LPCSTR für die Zeichenfolge (oder NULL)|  
|gibt|Nicht verwendet (0)|  
  
 **WM_IDLEUPDATECMDUI**  
  
 Diese Meldung ist Leerlaufzeit gesendet, um die Zeit im Leerlauf-Aktualisierung des Update-Befehlshandler UI implementieren. Wenn das Fenster (normalerweise eine Steuerleiste) die Nachricht verarbeitet, erstellt er eine `CCmdUI` Objekt (oder ein Objekt einer abgeleiteten Klasse), und rufen Sie **CCmdUI::DoUpdate** für den "Elementen" in das Fenster. Dadurch werden die wiederum nach einer `ON_UPDATE_COMMAND_UI` Handler für die Objekte in der Befehlshandler Kette.  
  
|||  
|-|-|  
|wParam|BOOL bDisableIfNoHandler|  
|lParam|Nicht verwendet (0)|  
|gibt|Nicht verwendet (0)|  
  
 *bDisableIfNoHandler* ist ungleich NULL, um das Benutzeroberflächenobjekt zu deaktivieren, wenn weder ein `ON_UPDATE_COMMAND_UI` noch ein `ON_COMMAND` Handler.  
  
 **WM_EXITHELPMODE**  
  
 Diese Meldung wird bereitgestellt, um eine `CFrameWnd` , die kontextabhängig beenden Hilfemodus. Der Empfang dieser Nachricht beendet die modale Größenanpassungsschleife gestartet, indem **CFrameWnd::OnContextHelp.**  
  
|||  
|-|-|  
|wParam|Nicht verwendet (0)|  
|lParam|Nicht verwendet (0)|  
|gibt|Nicht verwendet|  
  
 **WM_INITIALUPDATE**  
  
 Diese Meldung wird durch die Dokumentvorlage auf alle Nachfolger eines Rahmenfensters gesendet, wenn es ihnen, ihre Erstversion des Updates sicher ist. Es zugeordnet zu einem Aufruf von `CView::OnInitialUpdate` aber kann verwendet werden, in anderen `CWnd`-abgeleitete Klassen für andere One-Shot aktualisieren.  
  
|||  
|-|-|  
|wParam|Nicht verwendet (0)|  
|lParam|Nicht verwendet (0)|  
|gibt|Nicht verwendet (0)|  
  
 **WM_RECALCPARENT**  
  
 Diese Meldung wird durch eine Sicht an das übergeordnete Fenster gesendet (über abgerufen `GetParent`) erzwingen eine neuberechnung Layout (in der Regel ruft das übergeordnete Element `RecalcLayout`). Hiermit wird in der OLE-serveranwendungen für den Frame an Größe zunehmen wachsen Gesamtgröße für die Sicht erforderlich ist.  
  
 Wenn das übergeordnete Fenster diese Nachricht verarbeitet muss "true" zurückgeben und füllen die RECT lParam mit der neuen Größe des Clientbereichs übergeben. Dies wird verwendet, `CScrollView` ordnungsgemäß behandelt Bildlaufleisten (setzen Sie dann auf der Außenseite des Fensters, wenn sie hinzugefügt werden) wird ein Serverobjekt beim direkten aktiviert.  
  
|||  
|-|-|  
|wParam|Nicht verwendet (0)|  
|lParam|LPRECT-RectClient kann NULL sein|  
|gibt|TRUE, wenn neue Clientrechteck zurückgegeben, "false" andernfalls|  
  
 **WM_SIZECHILD**  
  
 Diese Nachricht wird gesendet, indem `COleResizeBar` an seine Besitzerfenster (über `GetOwner`) Wenn der Benutzer die Größenanpassungsleiste zum Ändern der mit der Ziehpunkte ändert. `COleIPFrameWnd`reagiert auf diese Meldung wird versucht, das Rahmenfenster neu positionieren, da der Benutzer angefordert hat.  
  
 Das neue Rechteck, in Clientkoordinaten relativ zum Rahmenfenster enthält die Größenanpassungsleiste zum Ändern der angegeben wird, auf lParam zeigt.  
  
|||  
|-|-|  
|wParam|Nicht verwendet (0)|  
|lParam|LPRECT rectNew|  
|gibt|Nicht verwendet (0)|  
  
 **WM_DISABLEMODAL**  
  
 Diese Nachricht wird gesendet, um alle Popupfenster im Besitz eines Rahmenfensters, das deaktiviert wird. Das Rahmenfenster verwendet das Ergebnis, um zu bestimmen, ob das Popup-Fenster zu deaktivieren.  
  
 Hiermit können Sie spezielle Verarbeitung in der Popup-Fenster ausführen, wenn der Frame einen modalen Zustand wechselt oder verhindern, dass bestimmte Popupfenster erste deaktiviert. QuickInfos verwenden diese Nachricht selbst zerstört, wenn das Rahmenfenster z. B. in einen modalen Zustand wechselt.  
  
|||  
|-|-|  
|wParam|Nicht verwendet (0)|  
|lParam|Nicht verwendet (0)|  
|gibt|Wert ungleich NULL **nicht** deaktivieren Sie das Fenster, 0 gibt an, das Fenster wird deaktiviert|  
  
 **WM_FLOATSTATUS**  
  
 Diese Nachricht wird gesendet, um alle Popupfenster Besitz eines Rahmenfensters, wenn der Frame aktiviert oder, die von einem anderen Rahmenfenster der obersten Ebene deaktiviert wird. Dies wird verwendet, durch die Implementierung von **MFS_SYNCACTIVE** in `CMiniFrameWnd`, um die Aktivierung dieser Popup-Fenster mit der Aktivierung des das Rahmenfenster der obersten Ebene synchron zu halten.  
  
|||  
|-|-|  
|wParam|Ist eine der folgenden Werte:<br /><br /> **FS_SHOW**<br /><br /> **FS_HIDE**<br /><br /> **FS_ACTIVATE**<br /><br /> **FS_DEACTIVATE**<br /><br /> **FS_ENABLEFS_DISABLE**<br /><br /> **FS_SYNCACTIVE**|  
|lParam|Nicht verwendet (0)|  
  
 Der Rückgabewert muss ungleich NULL Wenn **FS_SYNCACTIVE** festgelegt ist und das Fenster synchronisiert die Aktivierung über den übergeordneten Frame. `CMiniFrameWnd`ungleich NULL zurück, wenn das Format, um festgelegt wird **MFS_SYNCACTIVE.**  
  
 Weitere Informationen finden Sie auf die Implementierung von `CMiniFrameWnd`.  
  
## <a name="wmactivatetoplevel"></a>WM_ACTIVATETOPLEVEL  
 Diese Nachricht wird an ein Fenster oberster Ebene gesendet, wenn ein Fenster in der Gruppe"der obersten Ebene" aktiviert oder deaktiviert ist. Ein Fenster ist Teil einer Gruppe der obersten Ebene aus, wenn es ein Fenster oberster Ebene (ohne übergeordnete oder Besitzer), oder es solches Fenster Besitzer ist. Diese Meldung wird verwendet, um ähnliche **WM_ACTIVATEAPP,** funktioniert jedoch in Situationen, in denen Windows, die zu verschiedenen Prozessen gehören in ein einziges Fensterhierarchie (in der OLE-Anwendungen häufig) gemischt werden.  
  
## <a name="wmcommandhelp-wmhelphittest-wmexithelpmode"></a>WM_COMMANDHELP WM_HELPHITTEST, WM_EXITHELPMODE  
 Diese Nachrichten werden in der Implementierung der kontextbezogene Hilfe verwendet. Finden Sie unter [technischer Hinweis 28](../mfc/tn028-context-sensitive-help-support.md) für Weitere Informationen.  
  
## <a name="mfc-private-resource-formats"></a>MFC-Private Ressourcenformate  
 Derzeit MFC definiert zwei private Ressourcenformate: **RT_TOOLBAR** und **RT_DLGINIT**.  
  
## <a name="rttoolbar-resource-format"></a>RT_TOOLBAR-Ressource-Format  
 Die Standardsymbolleiste von AppWizard bereitgestellten basiert auf einer **RT_TOOLBAR** benutzerdefinierte Ressource, die in MFC 4.0 eingeführt wurde. Sie können diese Ressource über Symbolleisten-Editor bearbeiten.  
  
## <a name="rtdlginit-resource-format"></a>RT_DLGINIT Ressourcenformat  
 Eine MFC-private Ressource-Format wird verwendet, um zusätzliche Dialogfeld Initialisierungsinformationen zu speichern. Dies schließt die anfängliche Zeichenfolgen in ein Kombinationsfeld gespeichert. Das Format dieser Ressource dient nicht manuell bearbeitet werden, aber von Visual C++ behandelt wird.  
  
 Visual C++, und dies **RT_DLGINIT** Ressource müssen Sie die entsprechenden Funktionen von MFC verwenden, da es sich um API-Alternative zu mithilfe der Informationen in der Ressource nicht. Mit Visual C++ ist es viel einfacher zu schreiben, verwalten und Ihre Anwendung langfristig zu übersetzen.  
  
 Die grundlegende Struktur einer **RT_DLGINIT** Ressource lautet wie folgt:  
  
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
  
 Ein wiederholter Abschnitt enthält die Steuerelement-ID zum Senden der Nachricht, die Nachricht # zu senden (eine normale Windows-Nachricht) und eine Variable Länge der Daten. Die Windows-Meldung wird in einem Formular gesendet:  
  
```  
SendDlgItemMessage(<Control ID>, <Message #>, 0, &<Data>);
```  
  
 Dies ist ein sehr Allgemeines Format, sodass alle Windows-Meldungen und Dateninhalt. Die Ressourcen-Editor von Visual C++ und MFC unterstützen nur eine begrenzte Teilmenge der Windows-Meldungen: CB_ADDSTRING für die anfängliche Liste Auswahlmöglichkeiten für Kombinationsfelder (die Daten ist eine Textzeichenfolge).  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

