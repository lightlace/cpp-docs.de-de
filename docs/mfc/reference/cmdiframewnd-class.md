---
title: CMDIFrameWnd-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMDIFrameWnd
- AFXWIN/CMDIFrameWnd
- AFXWIN/CMDIFrameWnd::CMDIFrameWnd
- AFXWIN/CMDIFrameWnd::CreateClient
- AFXWIN/CMDIFrameWnd::CreateNewChild
- AFXWIN/CMDIFrameWnd::GetWindowMenuPopup
- AFXWIN/CMDIFrameWnd::MDIActivate
- AFXWIN/CMDIFrameWnd::MDICascade
- AFXWIN/CMDIFrameWnd::MDIGetActive
- AFXWIN/CMDIFrameWnd::MDIIconArrange
- AFXWIN/CMDIFrameWnd::MDIMaximize
- AFXWIN/CMDIFrameWnd::MDINext
- AFXWIN/CMDIFrameWnd::MDIPrev
- AFXWIN/CMDIFrameWnd::MDIRestore
- AFXWIN/CMDIFrameWnd::MDISetMenu
- AFXWIN/CMDIFrameWnd::MDITile
helpviewer_keywords:
- CMDIFrameWnd [MFC], CMDIFrameWnd
- CMDIFrameWnd [MFC], CreateClient
- CMDIFrameWnd [MFC], CreateNewChild
- CMDIFrameWnd [MFC], GetWindowMenuPopup
- CMDIFrameWnd [MFC], MDIActivate
- CMDIFrameWnd [MFC], MDICascade
- CMDIFrameWnd [MFC], MDIGetActive
- CMDIFrameWnd [MFC], MDIIconArrange
- CMDIFrameWnd [MFC], MDIMaximize
- CMDIFrameWnd [MFC], MDINext
- CMDIFrameWnd [MFC], MDIPrev
- CMDIFrameWnd [MFC], MDIRestore
- CMDIFrameWnd [MFC], MDISetMenu
- CMDIFrameWnd [MFC], MDITile
ms.assetid: fa8736e6-511b-4c51-8b4d-eba78378aeb9
ms.openlocfilehash: 9f5289491a7c14749865cfd163417440bc542aba
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58776530"
---
# <a name="cmdiframewnd-class"></a>CMDIFrameWnd-Klasse

Stellt die Funktionalität eines untergeordneten Windows-MDI-Rahmenfensters (Multiple Document Interface) bereit, zusammen mit Membern zum Verwalten des Fensters.

## <a name="syntax"></a>Syntax

```
class CMDIFrameWnd : public CFrameWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMDIFrameWnd::CMDIFrameWnd](#cmdiframewnd)|Erstellt ein Objekt vom Typ `CMDIFrameWnd`.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMDIFrameWnd::CreateClient](#createclient)|Erstellt ein Windows MDICLIENT-Fenster für diese `CMDIFrameWnd`. Wird aufgerufen, indem die `OnCreate` Memberfunktion `CWnd`.|
|[CMDIFrameWnd::CreateNewChild](#createnewchild)|Erstellt ein neues untergeordnetes Fenster an.|
|[CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup)|Gibt zurück, das Popup-Menü Fenster.|
|[CMDIFrameWnd::MDIActivate](#mdiactivate)|Aktiviert einen anderen untergeordneten MDI-Fensters.|
|[CMDIFrameWnd::MDICascade](#mdicascade)|Ordnet alle untergeordneten Fenster in einem kaskadierenden Format an.|
|[CMDIFrameWnd::MDIGetActive](#mdigetactive)|Ruft den derzeit aktiven untergeordneten MDI-Fensters, zusammen mit einem Flag, das angibt, ab, unabhängig davon, ob das untergeordnete Element maximiert ist.|
|[CMDIFrameWnd::MDIIconArrange](#mdiiconarrange)|Ordnet alle minimierten untergeordneten Dokumentfenster an.|
|[CMDIFrameWnd::MDIMaximize](#mdimaximize)|Maximieren ein untergeordneten MDI-Fensters.|
|[CMDIFrameWnd::MDINext](#mdinext)|Aktiviert das untergeordnete Fenster unmittelbar hinter dem derzeit aktiven untergeordneten Fenster aus, und fügt das derzeit aktiven untergeordneten Fenster hinter alle anderen untergeordneten Fenster.|
|[CMDIFrameWnd::MDIPrev](#mdiprev)|Aktiviert das vorherige untergeordnete Fenster, und schaltet das Fenster derzeit aktives untergeordnetes unmittelbar hinter ihm.|
|[CMDIFrameWnd::MDIRestore](#mdirestore)|Untergeordnete MDI-Fensters wiederhergestellt von maximierte oder minimierte Größe.|
|[CMDIFrameWnd::MDISetMenu](#mdisetmenu)|Ersetzt das Menü mit einem MDI-Rahmenfenster, das Popup-Menü Fenster oder beides.|
|[CMDIFrameWnd::MDITile](#mditile)|Ordnet alle untergeordneten Fenster in einem gekachelten Format an.|

## <a name="remarks"></a>Hinweise

Um eine nützliche MDI-Rahmenfenster für Ihre Anwendung zu erstellen, leiten Sie eine Klasse von `CMDIFrameWnd`. Hinzufügen von Membervariablen des Typs der abgeleiteten Klasse zum Speichern von Daten, die spezifisch für Ihre Anwendung. Implementieren Sie Meldungshandler-Memberfunktionen und eine Meldungszuordnung in der abgeleiteten Klasse, um anzugeben, was passiert, wenn Meldungen an das Fenster weitergeleitet werden.

Sie können ein MDI-Rahmenfenster erstellen, durch den Aufruf der [erstellen](../../mfc/reference/cframewnd-class.md#create) oder [LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe) Memberfunktion `CFrameWnd`.

Vor dem Aufruf `Create` oder `LoadFrame`, müssen Sie die Frame-Window-Objekt, auf dem Heap mit C++ erstellen **neue** Operator. Vor dem Aufruf `Create` können Sie auch eine Fensterklasse mit Registrieren der [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) -Funktion verwenden, um die Stile-Symbol und die Klasse für den Frame festgelegt.

Verwenden der `Create` Member-Funktion, Parameter zum Erstellen des Frames als sofortige Argumente übergeben.

`LoadFrame` erfordert weniger Argumente als `Create`, und ruft stattdessen die meisten von den Standardwerten aus Ressourcen, einschließlich der Beschriftung, Symbol, Zugriffstastentabelle und im Menü des Frames. Für den Zugriff durch `LoadFrame`, alle diese Ressourcen müssen die Ressourcen-ID (z. B. IDR_MAINFRAME).

Obwohl `MDIFrameWnd` ergibt sich aus `CFrameWnd`, abgeleitet von eine Rahmenfenster (Klasse) `CMDIFrameWnd` müssen nicht mit deklariert werden `DECLARE_DYNCREATE`.

Die `CMDIFrameWnd` Klasse erbt einen Großteil von der Standardimplementierung von `CFrameWnd`. Eine ausführliche Liste dieser Funktionen, finden Sie in der [CFrameWnd](../../mfc/reference/cframewnd-class.md) klassenbeschreibung. Die `CMDIFrameWnd` -Klasse verfügt über die folgenden zusätzlichen Funktionen:

- Ein MDI-Rahmenfenster verwaltet die MDICLIENT-Fenster, in Verbindung mit Schiebeleisten-Steuerelemente neu positionieren. Das MDI-Clientfenster ist das direkt übergeordnete Element des untergeordneten MDI-Frame-Fenster. Die WS_HSCROLL und WS_VSCROLL Window-Stile, die auf angegebenen ein `CMDIFrameWnd` gelten für das MDI-Clientfenster anstatt das Hauptrahmenfenster, damit der Benutzer den MDI-Client-Bereich (wie in der Windows Programmmanager, z. B.) einen Bildlauf durchführen kann.

- Ein MDI-Rahmenfenster besitzt ein Standardmenü, das als Menüleiste verwendet wird, wenn keine aktiven untergeordneten MDI-Fensters vorhanden ist. Liegt eine aktive untergeordnete MDI-Element, wird die Menüleiste des MDI-Rahmenfensters von untergeordneten MDI-Fenster-Menü automatisch ersetzt.

- Ein MDI-Rahmenfenster funktioniert in Verbindung mit der aktuellen untergeordneten MDI-Fensters, falls vorhanden. Befehlsmeldungen werden z. B. zum derzeit aktiven untergeordneten MDI-Fensters vor dem MDI-Rahmenfensters mitverwenden delegiert.

- Ein MDI-Rahmenfenster hat die Standardhandler für die folgenden standardmäßigen Fenster Befehle:

    - ID_WINDOW_TILE_VERT

    - ID_WINDOW_TILE_HORZ

    - ID_WINDOW_CASCADE

    - ID_WINDOW_ARRANGE

- Ein MDI-Rahmenfenster hat auch eine Implementierung von ID_WINDOW_NEW, die einen neuen Frame und eine Ansicht für das aktuelle Dokument erstellt. Eine Anwendung kann diese standardimplementierungen der Befehl zum Anpassen der Behandlung von MDI-Fensters überschreiben.

Verwenden Sie nicht die C++ **löschen** Operator, um ein Rahmenfenster zu zerstören. Verwenden Sie stattdessen `CWnd::DestroyWindow`. Die `CFrameWnd` Implementierung `PostNcDestroy` löscht das C++-Objekt aus, wenn das Fenster zerstört wird. Der Benutzer schließt das Rahmenfenster, der Standardwert `OnClose` Handler ruft `DestroyWindow`.

Weitere Informationen zu `CMDIFrameWnd`, finden Sie unter [Frame Windows](../../mfc/frame-windows.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIFrameWnd`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="cmdiframewnd"></a>  CMDIFrameWnd::CMDIFrameWnd

Erstellt ein `CMDIFrameWnd`-Objekt.

```
CMDIFrameWnd();
```

### <a name="remarks"></a>Hinweise

Rufen Sie die `Create` oder `LoadFrame` Memberfunktion versucht, das sichtbar MDI-Rahmenfenster erstellen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#13](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_1.cpp)]

##  <a name="createclient"></a>  CMDIFrameWnd::CreateClient

Erstellt das MDI-Client, der verwaltet die `CMDIChildWnd` Objekte.

```
virtual BOOL CreateClient(
    LPCREATESTRUCT lpCreateStruct,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>Parameter

*lpCreateStruct*<br/>
Ein long-Zeiger auf eine [CREATESTRUCT](/windows/desktop/api/winuser/ns-winuser-tagcreatestructa) Struktur.

*pWindowMenu*<br/>
Ein Zeiger auf das Popup-Menü Fenster.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion sollte aufgerufen werden, wenn Sie außer Kraft setzen der `OnCreate` direkt Member-Funktion.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#14](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_2.cpp)]

##  <a name="createnewchild"></a>  CMDIFrameWnd::CreateNewChild

Erstellt ein neues untergeordnetes Fenster an.

```
CMDIChildWnd* CreateNewChild(
    CRuntimeClass* pClass,
    UINT nResource,
    HMENU hMenu = NULL,
    HACCEL hAccel = NULL);
```

### <a name="parameters"></a>Parameter

*pClass*<br/>
Die Laufzeit-Klasse des untergeordneten Fensters erstellt werden.

*nResource*<br/>
Die ID des freigegebenen Ressourcen, die das untergeordnete Fenster zugeordnet.

*hMenu*<br/>
Ein Menü des untergeordneten Fensters.

*hAccel*<br/>
Das untergeordnete Fenster die Zugriffstaste.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion, um untergeordnete Fenster eine MDI-Rahmenfenster erstellen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#15](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_3.cpp)]

##  <a name="getwindowmenupopup"></a>  CMDIFrameWnd::GetWindowMenuPopup

Rufen Sie diese Memberfunktion zum Abrufen eines Handles für den aktuellen Popup-Menü, die mit dem Namen "Fenster" (im Popupmenü mit Menüelementen, die für die Verwaltung von MDI-Fensters).

```
virtual HMENU GetWindowMenuPopup(HMENU hMenuBar);
```

### <a name="parameters"></a>Parameter

*hMenuBar*<br/>
Der aktuelle Menüleiste.

### <a name="return-value"></a>Rückgabewert

Fenster im Popupmenü eine vorhanden ist. andernfalls NULL.

### <a name="remarks"></a>Hinweise

Die Standardimplementierung sucht ein Popupmenü mit standardmäßigen Menübefehle wie z. B. ID_WINDOW_NEW und ID_WINDOW_TILE_HORZ ab.

Überschreiben Sie diese Memberfunktion auf, wenn Sie ein Menü "Fenster" verfügen, die nicht die standardmäßige Menü-Befehls-IDs verwendet.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#16](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_4.cpp)]

##  <a name="mdiactivate"></a>  CMDIFrameWnd::MDIActivate

Aktiviert einen anderen untergeordneten MDI-Fensters.

```
void MDIActivate(CWnd* pWndActivate);
```

### <a name="parameters"></a>Parameter

*pWndActivate*<br/>
Verweist auf die untergeordneten MDI-Fensters aktiviert werden.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion sendet die [WM_MDIACTIVATE](../../mfc/reference/cwnd-class.md#onmdiactivate) Nachricht sowohl das untergeordnete Fenster aktiviert wird und das untergeordnete Fenster deaktiviert wird.

Dies ist die gleiche Nachricht, die gesendet wird, wenn der Benutzer den Fokus auf einer untergeordneten MDI-Fensters festlegt, mit der Maus oder Tastatur.

> [!NOTE]
>  Eine untergeordnete MDI-Fenster wird unabhängig von der MDI-Rahmenfenster aktiviert. Das untergeordnete Fenster, die der letzten Aktivierung wird gesendet, wenn der Frame aktiv wird, eine [WM_NCACTIVATE](../../mfc/reference/cwnd-class.md#onncactivate) Nachricht an eine aktive Fensterrahmen und Titelleiste, sondern zeichnen ist eine andere WM_MDIACTIVATE-Nachricht nicht empfangen.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup).

##  <a name="mdicascade"></a>  CMDIFrameWnd::MDICascade

Ordnet alle untergeordneter MDI-Fenster in einem Format Cascade an.

```
void MDICascade();
void MDICascade(int nType);
```

### <a name="parameters"></a>Parameter

*nType*<br/>
Gibt ein Flag Cascade an. Nur das Flag kann angegeben werden: MDITILE_SKIPDISABLED, verhindert, dass die aktiven untergeordneten MDI-Fenster überlappend angeordnet wird.

### <a name="remarks"></a>Hinweise

Die erste Version des `MDICascade`, überlappend an alle untergeordneten MDI, einschließlich der deaktiviert werden, ohne Parameter. Die zweite Version wird optional nicht deaktiviert Cascade untergeordnete MDI-Fenster, bei der Angabe von MDITILE_SKIPDISABLED für die *nType* Parameter.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#17](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_5.cpp)]

##  <a name="mdigetactive"></a>  CMDIFrameWnd::MDIGetActive

Ruft ab, der aktuellen aktiven untergeordneten MDI-Fensters, zusammen mit einem Flag zur Angabe, ob das untergeordnete Fenster maximiert ist.

```
CMDIChildWnd* MDIGetActive(BOOL* pbMaximized = NULL) const;
```

### <a name="parameters"></a>Parameter

*pbMaximized*<br/>
Ein Zeiger auf einen Rückgabewert von "bool". Auf "true" bei der Rückgabe festgelegt, wenn das Fenster maximiert ist; andernfalls "false".

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die aktiven untergeordneten MDI-Fensters.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).

##  <a name="mdiiconarrange"></a>  CMDIFrameWnd::MDIIconArrange

Ordnet alle minimierten untergeordneten Dokumentfenster an.

```
void MDIIconArrange();
```

### <a name="remarks"></a>Hinweise

Es hat keine Auswirkungen auf untergeordnete Fenster, die nicht minimiert werden.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CMDIFrameWnd::MDICascade](#mdicascade).

##  <a name="mdimaximize"></a>  CMDIFrameWnd::MDIMaximize

Maximiert das angegebene untergeordnete MDI-Fenster.

```
void MDIMaximize(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
Verweist auf das zu maximierende Fenster.

### <a name="remarks"></a>Hinweise

Wenn ein untergeordnetes Fenster maximiert ist, wird Windows, um seinen Clientbereich, füllen Sie die Client-Fenster zu machen. Windows fügt Steuerelementmenü des untergeordneten Fensters in der Menüleiste des Frames, sodass der Benutzer wiederherstellen kann, oder schließen das untergeordnete Fenster. Es fügt auch den Titel des untergeordneten Fensters auf den Titel des Rahmenfensters hinzu.

Wenn ein anderes untergeordnetes MDI-Fenster aktiviert ist, wenn das momentan aktive untergeordnete MDI-Fenster maximiert ist, wird Windows derzeit aktive untergeordnetes wiederhergestellt und wird das neu aktivierten untergeordneten Fenster maximiert.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).

##  <a name="mdinext"></a>  CMDIFrameWnd::MDINext

Aktiviert das untergeordnete Fenster unmittelbar hinter dem derzeit aktiven untergeordneten Fenster aus, und fügt das derzeit aktiven untergeordneten Fenster hinter alle anderen untergeordneten Fenster.

```
void MDINext();
```

### <a name="remarks"></a>Hinweise

Wenn das momentan aktive untergeordnete MDI-Fenster maximiert ist, wird die Memberfunktion derzeit aktive untergeordnetes wiederhergestellt und neu aktivierte untergeordneten maximiert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#18](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_6.cpp)]

##  <a name="mdiprev"></a>  CMDIFrameWnd::MDIPrev

Aktiviert das vorherige untergeordnete Fenster, und schaltet das Fenster derzeit aktives untergeordnetes unmittelbar hinter ihm.

```
void MDIPrev();
```

### <a name="remarks"></a>Hinweise

Wenn das momentan aktive untergeordnete MDI-Fenster maximiert ist, wird die Memberfunktion derzeit aktive untergeordnetes wiederhergestellt und neu aktivierte untergeordneten maximiert.

##  <a name="mdirestore"></a>  CMDIFrameWnd::MDIRestore

Untergeordnete MDI-Fensters wiederhergestellt von maximierte oder minimierte Größe.

```
void MDIRestore(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
Verweist auf das wiederherzustellende Fenster.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CMDIChildWnd::MDIRestore](../../mfc/reference/cmdichildwnd-class.md#mdirestore).

##  <a name="mdisetmenu"></a>  CMDIFrameWnd::MDISetMenu

Ersetzt das Menü mit einem MDI-Rahmenfenster, das Popup-Menü Fenster oder beides.

```
CMenu* MDISetMenu(
    CMenu* pFrameMenu,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>Parameter

*pFrameMenu*<br/>
Gibt an, klicken Sie im Menü des neuen Menüs Rahmenfenster. Wenn der Wert NULL ist, wird das Menü nicht geändert werden.

*pWindowMenu*<br/>
Gibt an, das Menü mit dem neuen Fenster Popupmenü. Wenn der Wert NULL ist, wird das Menü nicht geändert werden.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das Rahmenfenster-Menü, das durch diese Meldung ersetzt. Der Zeiger kann temporär sein und sollte nicht für eine spätere Verwendung gespeichert werden.

### <a name="remarks"></a>Hinweise

Nach dem Aufruf `MDISetMenu`, eine Anwendung aufrufen muss die [DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar) Memberfunktion `CWnd` auf die Menüleiste zu aktualisieren.

Wenn dieser Aufruf im Fenster Popupmenü ersetzt, sind MDI untergeordneten Fensters Menüelemente aus dem vorherigen Fenster-Menü entfernt und das neue Fenster Popup-Menü hinzugefügt.

Wenn eine untergeordnete MDI-Fenster maximiert wird und dieser Aufruf ersetzt, die im MDI-Rahmenfenster Menü, werden die Steuerelemente des Steuerelements im Menü und die Wiederherstellung aus dem vorherigen Rahmenfenster Menü entfernt und das neue Menü hinzugefügt.

Rufen Sie diese Memberfunktion nicht, wenn Sie das Framework verwenden, um Ihre untergeordneten MDI-Fenster zu verwalten.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#19](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_7.cpp)]

[!code-cpp[NVC_MFCWindowing#20](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_8.cpp)]

##  <a name="mditile"></a>  CMDIFrameWnd::MDITile

Ordnet alle untergeordneten Fenster in einem gekachelten Format an.

```
void MDITile();
void MDITile(int nType);
```

### <a name="parameters"></a>Parameter

*nType*<br/>
Gibt ein Flag Tiling. Dieser Parameter kann eine der folgenden Flags sein:

- MDITILE_HORIZONTAL Kacheln untergeordnete MDI-Fenster, sodass diese ein Fenster über eine andere angezeigt wird.

- MDITILE_SKIPDISABLED wird verhindert, dass deaktiviert untergeordnete MDI-Fenster aus gekachelt wird.

- MDITILE_VERTICAL Kacheln untergeordnete MDI-Fenster und diese einem Fenster neben einem anderen angezeigt.

### <a name="remarks"></a>Hinweise

Die erste Version des `MDITile`, ohne Parameter werden die Fenster vertikal unter Windows-Versionen 3.1 und höher angeordnet. Die zweite Version Kacheln Windows vertikal oder horizontal, abhängig vom Wert der *nType* Parameter.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CMDIFrameWnd::MDICascade](#mdicascade).

## <a name="see-also"></a>Siehe auch

[MDI MFC-Beispiel](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[CMDIChildWnd-Klasse](../../mfc/reference/cmdichildwnd-class.md)
