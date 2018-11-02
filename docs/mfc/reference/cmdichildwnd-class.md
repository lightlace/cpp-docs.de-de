---
title: CMDIChildWnd-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMDIChildWnd
- AFXWIN/CMDIChildWnd
- AFXWIN/CMDIChildWnd::CMDIChildWnd
- AFXWIN/CMDIChildWnd::Create
- AFXWIN/CMDIChildWnd::GetMDIFrame
- AFXWIN/CMDIChildWnd::MDIActivate
- AFXWIN/CMDIChildWnd::MDIDestroy
- AFXWIN/CMDIChildWnd::MDIMaximize
- AFXWIN/CMDIChildWnd::MDIRestore
- AFXWIN/CMDIChildWnd::SetHandles
helpviewer_keywords:
- CMDIChildWnd [MFC], CMDIChildWnd
- CMDIChildWnd [MFC], Create
- CMDIChildWnd [MFC], GetMDIFrame
- CMDIChildWnd [MFC], MDIActivate
- CMDIChildWnd [MFC], MDIDestroy
- CMDIChildWnd [MFC], MDIMaximize
- CMDIChildWnd [MFC], MDIRestore
- CMDIChildWnd [MFC], SetHandles
ms.assetid: 6d07f5d4-9a3e-4723-9fa5-e65bb669fdd5
ms.openlocfilehash: ffe7b975443b8bdc050bcb19af4f990b2e5ffafa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50576630"
---
# <a name="cmdichildwnd-class"></a>CMDIChildWnd-Klasse

Stellt die Funktionalität eines untergeordneten Windows-MDI-Fensters (Multiple Document Interface) bereit, zusammen mit Membern zum Verwalten des Fensters.

## <a name="syntax"></a>Syntax

```
class CMDIChildWnd : public CFrameWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMDIChildWnd::CMDIChildWnd](#cmdichildwnd)|Erstellt ein `CMDIChildWnd`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMDIChildWnd::Create](#create)|Erstellt die zugeordneten untergeordneten Windows-MDI-Fensters der `CMDIChildWnd` Objekt.|
|[CMDIChildWnd::GetMDIFrame](#getmdiframe)|Gibt das übergeordnete MDI-Frame, der das MDI-Clientfenster zurück.|
|[CMDIChildWnd::MDIActivate](#mdiactivate)|Aktiviert dieses untergeordneten MDI-Fensters.|
|[CMDIChildWnd::MDIDestroy](#mdidestroy)|Löscht dieses untergeordneten MDI-Fensters.|
|[CMDIChildWnd::MDIMaximize](#mdimaximize)|Wird diese untergeordnete MDI-Fenster maximiert.|
|[CMDIChildWnd::MDIRestore](#mdirestore)|Diese untergeordneten MDI-Fensters wiederhergestellt von maximierte oder minimierte Größe.|
|[CMDIChildWnd::SetHandles](#sethandles)|Legt fest, die Handles für Menüs und Accelerator-Ressourcen.|

## <a name="remarks"></a>Hinweise

Untergeordnete MDI-Fensters sieht ähnlich wie einem typischen Rahmenfenster, mit dem Unterschied, dass die untergeordneten MDI-Fensters in ein MDI-Rahmenfenster und nicht auf dem Desktop angezeigt wird. Ein untergeordneten MDI-Fensters verfügt nicht über eine eigene Menüleiste, aber stattdessen teilt das Menü des MDI-Rahmenfenster. Das Framework ändert sich automatisch im MDI-Frame-Menü das momentan aktive untergeordnete MDI-Fenster darstellt.

Um eine nützliche untergeordneten MDI-Fensters für Ihre Anwendung zu erstellen, leiten Sie eine Klasse von `CMDIChildWnd`. Hinzufügen von Membervariablen des Typs der abgeleiteten Klasse zum Speichern von Daten, die spezifisch für Ihre Anwendung. Implementieren Sie Meldungshandler-Memberfunktionen und eine Meldungszuordnung in der abgeleiteten Klasse, um anzugeben, was passiert, wenn Meldungen an das Fenster weitergeleitet werden.

Es gibt drei Möglichkeiten zum Erstellen eines untergeordneten MDI-Fensters aus:

- Erstellen Sie direkt mit `Create`.

- Erstellen Sie direkt mit `LoadFrame`.

- Erstellen Sie sie indirekt über eine Dokumentvorlage ein.

Vor dem Aufruf `Create` oder `LoadFrame`, müssen Sie die Frame-Window-Objekt, auf dem Heap mit C++ erstellen **neue** Operator. Vor dem Aufruf `Create` können Sie auch eine Fensterklasse mit Registrieren der [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) -Funktion verwenden, um die Stile-Symbol und die Klasse für den Frame festgelegt.

Verwenden der `Create` Member-Funktion, Parameter zum Erstellen des Frames als sofortige Argumente übergeben.

`LoadFrame` erfordert weniger Argumente als `Create`, und ruft stattdessen die meisten von den Standardwerten aus Ressourcen, einschließlich der Beschriftung, Symbol, Zugriffstastentabelle und im Menü des Frames. Zugänglich sein `LoadFrame`, alle diese Ressourcen müssen die Ressourcen-ID (z. B. IDR_MAINFRAME).

Wenn eine `CMDIChildWnd` Objekt enthält Ansichten und Dokumente, indirekt vom Framework nicht direkt vom Programmierer erstellt werden. Die `CDocTemplate` Objekt orchestriert die Erstellung des Frames, die Erstellung der Ansichten enthält und die Verbindung der Ansichten für das entsprechende Dokument. Die Parameter der `CDocTemplate` Konstruktor Festlegen der `CRuntimeClass` der drei Klassen beteiligt (Dokument, Rahmen und Ansicht). Ein `CRuntimeClass` Objekt wird durch das Framework verwendet, um neue Frames an, wenn vom Benutzer angegeben (z. B. mithilfe der neuen Datei Befehl oder den MDI-Fensters neuen Befehl) dynamisch zu erstellen.

Eine Rahmenfenster abgeleitete Klasse `CMDIChildWnd` muss mit DECLARE_DYNCREATE deklariert werden, in der Reihenfolge für die oben genannten RUNTIME_CLASS-Mechanismus ordnungsgemäß funktioniert.

Die `CMDIChildWnd` Klasse erbt einen Großteil von der Standardimplementierung von `CFrameWnd`. Eine ausführliche Liste dieser Funktionen, finden Sie in der [CFrameWnd](../../mfc/reference/cframewnd-class.md) klassenbeschreibung. Die `CMDIChildWnd` -Klasse verfügt über die folgenden zusätzlichen Funktionen:

- In Verbindung mit der `CMultiDocTemplate` -Klasse, die mehrere `CMDIChildWnd` Objekte mit der gleichen Dokumentvorlage nutzen dasselbe Menü, speichern die Windows-Systemressourcen.

- Die derzeit aktive untergeordneten MDI-Fenstermenü vollständig ersetzt des MDI-Frame-Fensters im Menü und die Beschriftung der derzeit aktiven untergeordneten MDI-Fensters wird die Beschriftung für das MDI-Rahmenfenster hinzugefügt. Weitere Beispiele für MDI-untergeordneten Fensterfunktionen, die in Verbindung mit einem MDI-Rahmenfenster implementiert werden, finden Sie unter den `CMDIFrameWnd` klassenbeschreibung.

Verwenden Sie nicht die C++ **löschen** Operator, um ein Rahmenfenster zu zerstören. Verwenden Sie stattdessen `CWnd::DestroyWindow`. Die `CFrameWnd` Implementierung `PostNcDestroy` löscht das C++-Objekt aus, wenn das Fenster zerstört wird. Der Benutzer schließt das Rahmenfenster, der Standardwert `OnClose` Handler ruft `DestroyWindow`.

Weitere Informationen zu `CMDIChildWnd`, finden Sie unter [Frame Windows](../../mfc/frame-windows.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIChildWnd`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="cmdichildwnd"></a>  CMDIChildWnd::CMDIChildWnd

Aufruf zum Erstellen einer `CMDIChildWnd` Objekt.

```
CMDIChildWnd();
```

### <a name="remarks"></a>Hinweise

Rufen Sie `Create` zum Erstellen des Fensters sichtbar.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMDIChildWnd::Create](#create).

##  <a name="create"></a>  CMDIChildWnd::Create

Diese Memberfunktion zum Erstellen eines untergeordneten Windows-MDI-Fensters, und fügen Sie ihn zum Aufrufen der `CMDIChildWnd` Objekt.

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    LPCTSTR lpszWindowName,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_OVERLAPPEDWINDOW,
    const RECT& rect = rectDefault,
    CMDIFrameWnd* pParentWnd = NULL,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Parameter

*"lpszclassname"*<br/>
Verweist auf eine Null-terminierte Zeichenfolge, die Namen die Windows-Klasse (ein [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576) Struktur). Der Klassenname kann einen beliebigen Namen registriert werden die [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) globale Funktion. Sollte NULL sein, für die Standard `CMDIChildWnd`.

*lpszWindowName*<br/>
Verweist auf eine Null-terminierte Zeichenfolge, die den Fensternamen darstellt. Als Text verwendet der Titelleiste.

*dwStyle*<br/>
Gibt das Zeitfenster [Stil](../../mfc/reference/styles-used-by-mfc.md#window-styles) Attribute. Das Format WS_CHILD ist erforderlich.

*Rect*<br/>
Enthält die Größe und Position des Fensters. Die `rectDefault` Wert ermöglicht Windows zum Angeben der Größe und Position des neuen `CMDIChildWnd`.

*pParentWnd*<br/>
Gibt an, das Fenster des übergeordneten. Wenn der Wert NULL ist, wird das Hauptanwendungsfenster verwendet.

*pContext*<br/>
Gibt an, eine [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) Struktur. Dieser Parameter kann NULL sein.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Der derzeit aktive untergeordneten-MDI-Rahmenfenster kann die Beschriftung des übergeordneten Rahmenfensters bestimmen. Dieses Feature ist deaktiviert, durch das FWS_ADDTOTITLE-Formatbit auf, von dem untergeordneten Rahmenfenster deaktivieren.

Das Framework ruft diese Memberfunktion als Reaktion auf einen Benutzerbefehl zum Erstellen eines untergeordneten Fensters, und das Framework verwendet die *"pContext"* Parameter, um das untergeordnete Fenster ordnungsgemäß mit der Anwendung herzustellen. Beim Aufruf `Create`, *"pContext"* kann NULL sein.

### <a name="example"></a>Beispiel

Beispiel 1:

[!code-cpp[NVC_MFCWindowing#7](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]

### <a name="example"></a>Beispiel

Beispiel 2:

[!code-cpp[NVC_MFCWindowing#8](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]

[!code-cpp[NVC_MFCWindowing#9](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]

##  <a name="getmdiframe"></a>  CMDIChildWnd::GetMDIFrame

Rufen Sie diese Funktion zum Zurückgeben von übergeordneten MDI-Rahmens.

```
CMDIFrameWnd* GetMDIFrame();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das übergeordnete MDI-Rahmenfenster.

### <a name="remarks"></a>Hinweise

Der Frame, der zurückgegeben wird zwei übergeordnete Elemente daraus die `CMDIChildWnd` und das übergeordnete Element des Fensters des Typs MDICLIENT, die verwaltet die `CMDIChildWnd` Objekt. Rufen Sie die [GetParent](../../mfc/reference/cwnd-class.md#getparent) Memberfunktion zurückgegeben der `CMDIChildWnd` unmittelbar übergeordnete Objekt im MDICLIENT als vorübergehende `CWnd` Zeiger.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMDIFrameWnd::MDISetMenu](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu).

##  <a name="mdiactivate"></a>  CMDIChildWnd::MDIActivate

Rufen Sie diese Memberfunktion, um einen untergeordneten MDI-Fensters, unabhängig von der MDI-Rahmenfenster zu aktivieren.

```
void MDIActivate();
```

### <a name="remarks"></a>Hinweise

Wenn der Frame aktiv wird, wird das untergeordnete Fenster, das zuletzt aktiviert war ebenfalls aktiviert.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMDIFrameWnd::GetWindowMenuPopup](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup).

##  <a name="mdidestroy"></a>  CMDIChildWnd::MDIDestroy

Rufen Sie diese Memberfunktion zum Zerstören eines untergeordneten MDI-Fensters.

```
void MDIDestroy();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion entfernt den Titel des untergeordneten Fensters aus dem Rahmenfenster und das untergeordnete Fenster deaktiviert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#10](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]

##  <a name="mdimaximize"></a>  CMDIChildWnd::MDIMaximize

Rufen Sie diese Memberfunktion, um einen untergeordneten MDI-Fensters zu maximieren.

```
void MDIMaximize();
```

### <a name="remarks"></a>Hinweise

Wenn ein untergeordnetes Fenster maximiert ist, wird Windows, um seinen Clientbereich, geben Sie den Clientbereich des Rahmenfensters zu machen. Windows Steuerelementmenü des untergeordneten Fensters in der Menüleiste des Frames so anordnet, dass der Benutzer die Wiederherstellung oder das untergeordnete Fenster zu schließen und den Titel des untergeordneten Fensters auf den Titel des Rahmenfensters hinzugefügt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#11](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]

##  <a name="mdirestore"></a>  CMDIChildWnd::MDIRestore

Rufen Sie diese Memberfunktion zum Wiederherstellen eines untergeordneten MDI-Fensters von maximierte oder minimierte Größe an.

```
void MDIRestore();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#12](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]

##  <a name="sethandles"></a>  CMDIChildWnd::SetHandles

Legt fest, die Handles für Menüs und Accelerator-Ressourcen.

```
void SetHandles(
    HMENU hMenu,
    HACCEL hAccel);
```

### <a name="parameters"></a>Parameter

*hMenu*<br/>
Das Handle einer Ressource im Menü.

*hAccel*<br/>
Das Handle einer Ressource für die Zugriffstaste.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion zum Festlegen von Menüs und Accelerator das MDI-untergeordnete Fenster-Objekt verwendeten Ressourcen.

## <a name="see-also"></a>Siehe auch

[MDI MFC-Beispiel](../../visual-cpp-samples.md)<br/>
[MFC-Beispiel MDIDOCVW](../../visual-cpp-samples.md)<br/>
[MFC-Beispiel SNAPVW](../../visual-cpp-samples.md)<br/>
[CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[CMDIFrameWnd-Klasse](../../mfc/reference/cmdiframewnd-class.md)
