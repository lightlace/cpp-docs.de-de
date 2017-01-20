---
title: "TN024: MFC-definierte Meldungen und Ressourcen"
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
  - "vc.mfc.messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Nachrichten [C++], MFC"
  - "Ressourcen [MFC]"
  - "TN024"
  - "Windows-Nachrichten [C++], MFC-definiert"
ms.assetid: c65353ce-8096-454b-ad22-1a7a1dd9a788
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# TN024: MFC-definierte Meldungen und Ressourcen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis beschreibt die internen Windows\-Meldungen und formatiert Ressource verwendet von MFC.  Diese Informationen verdeutlichen die Implementierung des Framework und werden Ihnen helfen, wenn sie die Anwendung debuggen.  Für das abenteuerliche obwohl alle diese Informationen nicht offiziell unterstützt sind, verwenden Sie möglicherweise einige dieser Informationen für komplexere Implementierungen.  
  
 Dieser Hinweis enthält private Implementierungsdetails MFC; der gesamte Inhalt ist zukünftig geändert.  Private Windows\-Meldungen MFC Bedeutung haben, im Rahmen einer Anwendung nur jedoch werden in der Zukunft ändern, um systemweite Meldungen enthalten.  
  
 Der Bereich von privaten Windows\-Meldungen MFC sowie die Ressourcentypen sind im reservierten "System Bereich, der von Microsoft Windows und platziert wird.  Derzeit werden nicht alle Zahlen in Bereichen verwendet und in Zukunft neue werden Zahlen kann im Gültigkeitsbereich verwendet.  Die gerade verwendeten Zahlen können geändert werden.  
  
 Private Windows\-Meldungen MFC ähneln im Bereich 0x360\-0x37F \>.  
  
 Private Ressourcentypen MFC ähneln im Bereich 0xF0\-0xFF \>.  
  
 **Private Windows\-Meldungen MFC**  
  
 Diese Windows\-Meldungen werden anstelle virtueller Funktionen C\+\+ verwendet, in denen relativ lose Kopplung zwischen Fensterobjekten erforderlich ist und sich virtuelle Funktion einer C\+\+ nicht geeignet ist.  
  
 Diese privaten Windows\-Meldungen und zugeordneten Parameterstrukturen werden in der privaten Header "AFXPRIV.H" MFC deklariert.  Achten gewarnt Sie, das jeden möglicherweise von Code, der diese enthält, Header auf nicht dokumentiertem Verhalten und ist wahrscheinlich einlaufen zukünftige Versionen von MFC basiert.  
  
 Im seltenen Fall gegeben, um eine dieser Nachrichten behandeln, sollten Sie das `ON_MESSAGE` Meldungszuordnungsmakro verwenden und die Meldung im generischen LRESULT\-\/WPARAM\/LPARAMformat bearbeiten.  
  
 **WM\_QUERYAFXWNDPROC**  
  
 Diese Meldung wird an ein Fenster gesendet, das erstellt wird.  Dies ist sehr frühzeitig im Erstellungsprozess als Methode zur gesendet, sofern das WndProc gibt 1 zurück. **AfxWndProc. AfxWndProc**.  
  
|||  
|-|-|  
|wParam|Nicht in Verwendung|  
|lParam|Nicht in Verwendung|  
|gibt|1 nach **AfxWndProc** verarbeitet werden|  
  
 **WM\_SIZEPARENT**  
  
 Diese Meldung werden durch ein Rahmenfenster zu den unmittelbar untergeordneten Elementen während der Größenanpassung \(**CFrameWnd::OnSize** ruft `CFrameWnd::RecalcLayout` auf, das `CWnd::RepositionBars` aufruft\), um übermittelt die Steuerleisten um die Frames neu anzuordnen.  Die **AFX\_SIZEPARENTPARAMS**\-Struktur enthält das aktuelle verfügbare Clientrechteck übergeordneten und dem des HDWP \(die möglicherweise NULL sind\), um `DeferWindowPos` aufzurufen, um das neu zu minimieren.  
  
|||  
|-|-|  
|wParam|Nicht in Verwendung|  
|lParam|Adresse einer **AFX\_SIZEPARENTPARAMS**\-Struktur|  
|gibt|Wird nicht verwendet \(0\)|  
  
 Die Meldung Ignorieren, gibt an, dass das Fenster nicht am Layout beteiligt ist.  
  
 **WM\_SETMESSAGESTRING**  
  
 Diese Meldung wird in einem Rahmenfenster gesendet, um es zu bitten, die Meldungszeile in der Statusleiste zu aktualisieren.  Entweder eine Zeichenfolgen\-ID oder ein LPCSTR sind zulässig \(jedoch nicht beide\).  
  
|||  
|-|-|  
|wParam|Zeichenfolgen\-ID oder \(null\)|  
|lParam|LPCSTR für die Zeichenfolge \(oder NULL\)|  
|gibt|Wird nicht verwendet \(0\)|  
  
 **WM\_IDLEUPDATECMDUI**  
  
 Diese Meldung wird in der Leerlaufzeit, das Leerlaufupdate von UpdateBefehl Benutzeroberflächenhandlern implementieren gesendet.  Wenn das Fenster \(normalerweise eine Steuerleiste\) die Meldung verarbeitet, erstellt es ein `CCmdUI`\-Objekt \(oder Objekt einer abgeleiteten Klasse\) und Aufruf **CCmdUI::DoUpdate** für jedes der "Elemente" im Fenster.  Diese überprüft wiederum für einen Handler `ON_UPDATE_COMMAND_UI` für die Objekte in der Befehlshandlerkette.  
  
|||  
|-|-|  
|wParam|BOOL\-bDisableIfNoHandler|  
|lParam|Wird nicht verwendet \(0\)|  
|gibt|Wird nicht verwendet \(0\)|  
  
 *bDisableIfNoHandler* ist ungleich 0 \(null\), das Benutzeroberflächenobjekt zu deaktivieren, wenn weder `ON_UPDATE_COMMAND_UI` noch `ON_COMMAND` einen Handler gibt.  
  
 **WM\_EXITHELPMODE**  
  
 Diese Meldung wird an `CFrameWnd` gesendet, das Modus der kontextbezogenen Hilfe zu verlassen.  An\- dieser Nachricht beendet die modalen Schleife, die von **CFrameWnd::OnContextHelp.** gestartet wird  
  
|||  
|-|-|  
|wParam|Wird nicht verwendet \(0\)|  
|lParam|Wird nicht verwendet \(0\)|  
|gibt|Nicht in Verwendung|  
  
 **WM\_INITIALUPDATE**  
  
 Diese Meldung werden durch die Normal\-Vorlage für alle Nachfolgerelemente eines Rahmenfensters gesendet, wenn die Verwendung für sie ist, deren ursprüngliche Aktualisierung durchzuführen.  Sie belegt, einen Aufruf von `CView::OnInitialUpdate` kann jedoch in anderen `CWnd` verwendet werden \- abgeleitete Klassen für andere monostabiles Aktualisieren.  
  
|||  
|-|-|  
|wParam|Wird nicht verwendet \(0\)|  
|lParam|Wird nicht verwendet \(0\)|  
|gibt|Wird nicht verwendet \(0\)|  
  
 **WM\_RECALCPARENT**  
  
 Diese Meldung wird in einer Ansicht an das übergeordnete Fenster \(Abrufen über `GetParent`\) gesendet um eine Layoutneuberechnung zu erzwingen \(normalerweise, ruft das übergeordnete Element `RecalcLayout` auf\).  Dies wird in OLE\-Serveranwendungen verwendet, in denen es erforderlich für die Frames ist, die Größe zu erweitern, da die Gesamtgröße der Ansicht vergrößert.  
  
 Wenn das übergeordnete Fenster die Meldung verarbeitet, sollte es TRUE zurückgeben und \- Struktur zu füllen, das in lParam mit dem neuen übergeben wird, skalieren Sie dem Clientbereich.  Dies wird in `CScrollView` verwendet, um Platz Bildlaufleisten \(auf der Außenseite des Fensters, wenn sie hinzugefügt werden\), korrekt behandeln wenn ein Serverobjekt können direkt ist.  
  
|||  
|-|-|  
|wParam|Wird nicht verwendet \(0\)|  
|lParam|LPRECT, das rectClient ist, kann NULL|  
|gibt|TRUE, wenn neue Clientrechteck zurückgegebenen, FALSE andernfalls|  
  
 **WM\_SIZECHILD**  
  
 Diese Meldung wird von `COleResizeBar` auf den Besitzerfenster gesendet \(über `GetOwner`\) Wenn der Benutzer die Größe geänderte Leiste mit den Ziehpunkten Größe ändert.  `COleIPFrameWnd` reagiert auf diese Meldung, indem es, versucht das Rahmenfenster neu anzuordnen, da der Benutzer anfordert.  
  
 Das neue Rechteck, angegeben in Clientkoordinaten relativ zum Rahmenfenster, das der Größe geänderte Leiste enthält, wird durch lParam am gezeigt.  
  
|||  
|-|-|  
|wParam|Wird nicht verwendet \(0\)|  
|lParam|LPRECT\-rectNew|  
|gibt|Wird nicht verwendet \(0\)|  
  
 **WM\_DISABLEMODAL**  
  
 Diese Meldung wird auf alle Popupfenstern gesendet, die von ein Rahmenfenster besitzen, das deaktiviert ist.  Das Rahmenfenster verwendet das Ergebnis, um zu bestimmen, ob das Popupfenster deaktiviert.  
  
 Sie können dieses verwenden, um die spezielle Verarbeitung im Popupfenster auszuführen, wenn der Frame einen modalen Zustand eingeben oder bestimmte Popupfenster im Abrufen zu halten deaktiviert.  QuickInfo verwenden diese Meldung, um zum Beispiel zu zerstören, wenn das Rahmenfenster in einen modalen Zustand wechselt.  
  
|||  
|-|-|  
|wParam|Wird nicht verwendet \(0\)|  
|lParam|Wird nicht verwendet \(0\)|  
|gibt|Wert ungleich 0 \(null\) zu **NICHT** Deaktivierung des Fenster 0, gibt das Fenster deaktiviert an|  
  
 **WM\_FLOATSTATUS**  
  
 Diese Meldung wird auf alle Popupfenstern gesendet, die von ein Rahmenfenster besitzen, wenn der Frame entweder durch ein anderes Rahmenfenster der obersten Ebene aktiviert oder deaktiviert werden.  Dies wird durch die Implementierung von **MFS\_SYNCACTIVE** in `CMiniFrameWnd` verwendet, um die Aktivierung dieser Popupfenster mit der Aktivierung des Rahmenfensters der höchsten Ebene zu halten.  
  
|||  
|-|-|  
|wParam|Ist einer der folgenden Werte:<br /><br /> **FS\_SHOW**<br /><br /> **FS\_HIDE**<br /><br /> **FS\_ACTIVATE**<br /><br /> **FS\_DEACTIVATE**<br /><br /> **FS\_ENABLEFS\_DISABLE**<br /><br /> **FS\_SYNCACTIVE**|  
|lParam|Wird nicht verwendet \(0\)|  
  
 Der Rückgabewert sollte ungleich 0 \(null\), wenn **FS\_SYNCACTIVE** festgelegt ist und das Fenster seine Aktivierung mit übergeordneten Frame syncronizes.  `CMiniFrameWnd` gibt einen Wert ungleich 0 \(null\) zurück, wenn das Format auf **MFS\_SYNCACTIVE.** festgelegt wird  
  
 Weitere Informationen finden Sie in der Implementierung von `CMiniFrameWnd`.  
  
## WM\_ACTIVATETOPLEVEL  
 Diese Meldung wird an ein Fenster der obersten Ebene gesendet, wenn ein Fenster in der Gruppe "der obersten Ebene" entweder aktiviert oder deaktiviert ist.  Ein Fenster wird ein Teil einer Gruppe der obersten Ebene, wenn es ein Fenster auf oberster Ebene \(ohne übergeordneten oder Besitzer\) ist, oder es wird mit ein solches Fenster gehört.  Diese Meldung ist zu **WM\_ACTIVATEAPP,** jedoch zu den Arbeiten in Situationen ähnlich, in denen die Fenster, die verschiedenen Prozessen gehören, in einer einzelnen Fensterhierarchie \(Common in den OLE\-Anwendungen\) kombiniert werden.  
  
## WM\_COMMANDHELP, WM\_HELPHITTEST, WM\_EXITHELPMODE  
 Diese Meldungen werden in der Implementierung der kontextbezogenen Hilfe verwendet.  finden Sie unter [Technischer Hinweis 28](../mfc/tn028-context-sensitive-help-support.md) weitere Informationen an.  
  
## Private Ressourcen\-Formate MFC  
 Derzeit MFC definiert zwei private Ressourcenformate: **RT\_TOOLBAR** und **RT\_DLGINIT**.  
  
## RT\_TOOLBAR\-Ressourcen\-Format  
 Die Standardsymbolleiste, die vom Anwendungs\-Assistenten angegeben wird, ist auf Grundlage einer benutzerdefinierten Ressource **RT\_TOOLBAR**, die in MFC 4.0 eingeführt wurde.  Sie können diese Ressource mithilfe des Symbolleisten\-Editors bearbeiten.  
  
## RT\_DLGINIT\-Ressourcen\-Format  
 Ein privates Ressourcenformat MFC wird verwendet, um zusätzliche Dialogfeldinitialisierungsinformationen zu speichern.  Dieses enthält die ursprünglichen Zeichenfolgen ein, die in einem Kombinationsfeld gespeichert werden.  Das Format dieser Ressource ist nicht vorgesehen, manuell bearbeitet werden, die jedoch mit Visual C\+\+ behandelt.  
  
 Visual C\+\+ und **RT\_DLGINIT** diese Ressource ist nicht erforderlich, die zugehörigen Funktionen von MFC verwendet, da es APIalternative zur Verwendung der Informationen in der Ressource gibt.  Mit Visual C\+\+ ist es viel einfacher, die Anwendung zu erstellen, beizubehalten und langfristig zu übersetzen.  
  
 Die grundlegende Struktur einer **RT\_DLGINIT** Ressource ist, wie folgt:  
  
```  
+---------------+                    \  
| Control ID    |   UINT             |  
+---------------+                    |  
| Message #     |   UINT             |  
+---------------+                    |  
|length of data |   DWORD            |  
+---------------+                    |   Repeated  
|   Data        |   Variable Length  |   for each control  
|   ...         |   and Format       |   and message  
+---------------+                    /  
|     0         |   BYTE  
+---------------+  
```  
  
 Ein wiederholter Abschnitt enthält die Steuerelement\-ID, um die Meldung an, die Meldung \# zu senden \(eine normale Windows\-Meldung\) und ein variabler Länge von Daten zu senden.  Die Windows\-Meldung wird in einem Formular gesendet:  
  
```  
SendDlgItemMessage(<Control ID>, <Message #>, 0, &<Data>);  
```  
  
 Dies ist ein sehr Muster und können alle Windows\-Meldungen und Daten.  Der Visual C\+\+\-Ressourcen\-Editor und MFC unterstützen nur eine geringe Teilmenge Windows\-Meldungen: CB\_ADDSTRING für die ursprünglichen ListeAuswahlen für Kombinationsfelder \(die Daten sind eine Textzeichenfolge.\)  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)