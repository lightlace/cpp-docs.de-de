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
ms.openlocfilehash: 09a9846cc3d242ef7d812cb31b4dcdd515d5f6ef
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506076"
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
|[CMDIChildWnd:: CMDIChildWnd](#cmdichildwnd)|Erstellt ein `CMDIChildWnd`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMDIChildWnd:: Create](#create)|Erstellt das untergeordnete Windows MDI-Fenster, `CMDIChildWnd` das dem-Objekt zugeordnet ist.|
|[CMDIChildWnd::GetMDIFrame](#getmdiframe)|Gibt den übergeordneten MDI-Frame des MDI-Client Fensters zurück.|
|[CMDIChildWnd:: mdiaktivierungs](#mdiactivate)|Aktiviert dieses untergeordnete MDI-Fenster.|
|[CMDIChildWnd:: mdidestroy](#mdidestroy)|Zerstört dieses untergeordnete MDI-Fenster.|
|[CMDIChildWnd:: mdimaximi](#mdimaximize)|Maximiert dieses untergeordnete MDI-Fenster.|
|[CMDIChildWnd:: mumgeleitet Store](#mdirestore)|Stellt dieses untergeordnete MDI-Fenster von der maximierten oder minimierten Größe wieder her.|
|[CMDIChildWnd:: Sekunden](#sethandles)|Legt die Handles für Menü-und Beschleunigungs Ressourcen fest.|

## <a name="remarks"></a>Hinweise

Ein untergeordnetes MDI-Fenster ähnelt einem typischen Rahmen Fenster, mit dem Unterschied, dass das untergeordnete MDI-Fenster in einem MDI-Rahmen Fenster statt auf dem Desktop angezeigt wird. Ein untergeordnetes MDI-Fenster verfügt nicht über eine eigene Menüleiste, sondern verwendet stattdessen das Menü des MDI-Rahmen Fensters. Das Framework ändert das MDI-Frame Menü automatisch so, dass es das momentan aktive untergeordnete MDI-Fenster darstellt.

Um ein nützliches untergeordnetes MDI-Fenster für die Anwendung zu erstellen, leiten `CMDIChildWnd`Sie eine Klasse von ab. Fügen Sie der abgeleiteten Klasse Element Variablen hinzu, um Daten zu speichern, die für Ihre Anwendung spezifisch sind. Implementieren Sie Meldungshandler-Memberfunktionen und eine Meldungszuordnung in der abgeleiteten Klasse, um anzugeben, was passiert, wenn Meldungen an das Fenster weitergeleitet werden.

Es gibt drei Möglichkeiten, ein untergeordnetes MDI-Fenster zu erstellen:

- Erstellen Sie es direkt `Create`mithilfe von.

- Erstellen Sie es direkt `LoadFrame`mithilfe von.

- Erstellen Sie es indirekt über eine Dokument Vorlage.

Bevor Sie oder `Create` `LoadFrame`aufruft, müssen Sie das Rahmen Fenster Objekt auf dem Heap mit dem C++ **New** -Operator erstellen. Vor dem `Create` Aufrufen von können Sie auch eine Fenster Klasse mit der globalen Funktion [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) registrieren, um das Symbol und die Klassen Stile für den Frame festzulegen.

Verwenden Sie `Create` die Member-Funktion, um die Erstellungs Parameter des Frames als unmittelbare Argumente zu übergeben.

`LoadFrame`erfordert weniger Argumente als `Create`und ruft stattdessen die meisten Standardwerte aus Ressourcen ab, einschließlich der Beschriftung, des Symbols, der Zugriffstasten Tabelle und des Menüs des Frames. Um auf zugreifen zu `LoadFrame`können, müssen alle diese Ressourcen dieselbe Ressourcen-ID aufweisen (z. b. IDR_MAINFRAME).

Wenn ein `CMDIChildWnd` -Objekt Sichten und Dokumente enthält, werden diese indirekt durch das Framework anstatt direkt vom Programmierer erstellt. Das `CDocTemplate` -Objekt orchestriert die Erstellung des Frames, die Erstellung der enthaltenden Sichten und die Verbindung der Ansichten mit dem entsprechenden Dokument. Die Parameter des `CDocTemplate` -Konstruktors geben den `CRuntimeClass` der drei beteiligten Klassen an (Dokument, Rahmen und Ansicht). Ein `CRuntimeClass` -Objekt wird vom Framework verwendet, um neue Frames dynamisch zu erstellen, wenn Sie vom Benutzer angegeben werden (z. b. mit dem Befehl "Datei neu" oder dem MDI-Fenster "neu").

Eine von `CMDIChildWnd` abgeleitete Frame-Window-Klasse muss mit DECLARE_DYNCREATE deklariert werden, damit der obige RUNTIME_CLASS-Mechanismus ordnungsgemäß funktioniert.

Die `CMDIChildWnd` -Klasse erbt einen Großteil der Standard Implementierung `CFrameWnd`von. Eine ausführliche Liste dieser Features finden Sie in der Beschreibung der [CFrameWnd](../../mfc/reference/cframewnd-class.md) -Klasse. Die `CMDIChildWnd` -Klasse verfügt über die folgenden zusätzlichen Funktionen:

- In Verbindung mit der `CMultiDocTemplate` -Klasse verwenden `CMDIChildWnd` mehrere Objekte aus derselben Dokument Vorlage dasselbe Menü, das Windows-Systemressourcen speichert.

- Das momentan aktive untergeordnete MDI-Fenstermenü ersetzt vollständig das Menü Fenster des MDI-Frame Fensters, und die Beschriftung des momentan aktiven untergeordneten MDI-Fensters wird der Beschriftung des MDI-Frame Fensters hinzugefügt. Weitere Beispiele für untergeordnete MDI-Fenster Funktionen, die in Verbindung mit einem MDI-Rahmen Fenster implementiert werden `CMDIFrameWnd` , finden Sie in der Beschreibung der-Klasse.

Verwenden Sie nicht den C++ **Delete** -Operator, um ein Rahmen Fenster zu zerstören. Verwenden Sie stattdessen `CWnd::DestroyWindow`. Die `CFrameWnd` Implementierung von `PostNcDestroy` löscht das C++ -Objekt, wenn das Fenster zerstört wird. Wenn der Benutzer das Rahmen Fenster schließt, ruft `OnClose` `DestroyWindow`der Standard Handler auf.

Weitere Informationen zu `CMDIChildWnd`finden Sie unter [Rahmen Fenster](../../mfc/frame-windows.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIChildWnd`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="cmdichildwnd"></a>CMDIChildWnd:: CMDIChildWnd

Ruft auf, um `CMDIChildWnd` ein-Objekt zu erstellen.

```
CMDIChildWnd();
```

### <a name="remarks"></a>Hinweise

Rufen `Create` Sie auf, um das sichtbare Fenster zu erstellen.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CMDIChildWnd:: Create](#create).

##  <a name="create"></a>CMDIChildWnd:: Create

Rufen Sie diese Member-Funktion auf, um ein untergeordnetes Windows MDI-Fenster `CMDIChildWnd` zu erstellen und an das-Objekt anzufügen.

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

*lpszClassName*<br/>
Verweist auf eine mit NULL endenden Zeichenfolge, die die Windows-Klasse benennt (eine [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) -Struktur). Der Klassenname kann ein beliebiger Name sein, der bei der globalen Funktion [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) registriert ist. Muss für einen Standard `CMDIChildWnd`Wert NULL sein.

*lpszWindowName*<br/>
Verweist auf eine mit NULL endenden Zeichenfolge, die den Fensternamen darstellt. Wird als Text für die Titelleiste verwendet.

*dwStyle*<br/>
Gibt die Fenster [Stil](../../mfc/reference/styles-used-by-mfc.md#window-styles) Attribute an. Der WS_CHILD-Stil ist erforderlich.

*Rect*<br/>
Enthält die Größe und Position des Fensters. Der `rectDefault` -Wert ermöglicht es Windows, die Größe und Position der neuen `CMDIChildWnd`anzugeben.

*pParentWnd*<br/>
Gibt das übergeordnete Fenster des Fensters an. Wenn der Wert NULL ist, wird das Hauptanwendungsfenster verwendet.

*pContext*<br/>
Gibt eine [ckreatecontext](../../mfc/reference/ccreatecontext-structure.md) -Struktur an. Dieser Parameter kann NULL sein.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Das momentan aktive untergeordnete MDI-Rahmen Fenster kann die Beschriftung des übergeordneten Rahmen Fensters bestimmen. Diese Funktion wird deaktiviert, indem das FWS_ADDTOTITLE-Stilbit des untergeordneten Rahmen Fensters ausgeschaltet wird.

Das Framework ruft diese Member-Funktion als Reaktion auf einen Benutzer Befehl auf, um ein untergeordnetes Fenster zu erstellen, und das Framework verwendet den *pContext* -Parameter, um das untergeordnete Fenster ordnungsgemäß mit der Anwendung zu verbinden. Wenn Sie aufzurufen `Create`, kann *pContext* NULL sein.

### <a name="example"></a>Beispiel

Beispiel 1:

[!code-cpp[NVC_MFCWindowing#7](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]

### <a name="example"></a>Beispiel

Beispiel 2:

[!code-cpp[NVC_MFCWindowing#8](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]

[!code-cpp[NVC_MFCWindowing#9](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]

##  <a name="getmdiframe"></a>CMDIChildWnd:: getmdiframe

Mit dieser Funktion wird der übergeordnete MDI-Frame zurückgegeben.

```
CMDIFrameWnd* GetMDIFrame();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das übergeordnete MDI-Rahmen Fenster.

### <a name="remarks"></a>Hinweise

Der zurückgegebene Frame besteht aus zwei übergeordneten `CMDIChildWnd` Elementen, die aus dem entfernt werden, und ist das übergeordnete Element des `CMDIChildWnd` Windows-Typs, das das Objekt verwaltet. Aufrufen der [GetParent](../../mfc/reference/cwnd-class.md#getparent) -Member-Funktion, `CMDIChildWnd` um das unmittelbare MdiClient-übergeordnete Element `CWnd` des Objekts als temporären Zeiger zurückzugeben.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CMDIFrameWnd:: mdisetmenu](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu).

##  <a name="mdiactivate"></a>CMDIChildWnd:: mdiaktivierungs

Diese Member-Funktion wird aufgerufen, um ein untergeordnetes MDI-Fenster unabhängig vom MDI-Rahmen Fenster zu aktivieren.

```
void MDIActivate();
```

### <a name="remarks"></a>Hinweise

Wenn der Frame aktiv wird, wird auch das untergeordnete Fenster aktiviert, das zuletzt aktiviert wurde.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CMDIFrameWnd:: getwindowmenupopup](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup).

##  <a name="mdidestroy"></a>CMDIChildWnd:: mdidestroy

Diese Member-Funktion zum Zerstören eines untergeordneten MDI-Fensters aufzurufen.

```
void MDIDestroy();
```

### <a name="remarks"></a>Hinweise

Die Member-Funktion entfernt den Titel des untergeordneten Fensters aus dem Rahmen Fenster und deaktiviert das untergeordnete Fenster.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#10](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]

##  <a name="mdimaximize"></a>CMDIChildWnd:: mdimaximi

Diese Member-Funktion zum Maximieren eines untergeordneten MDI-Fensters aufzurufen.

```
void MDIMaximize();
```

### <a name="remarks"></a>Hinweise

Wenn ein untergeordnetes Fenster maximiert ist, ändert Windows seine Größe, damit der Client Bereich den Client Bereich des Rahmen Fensters auffüllen kann. Windows legt das Steuerelement Menü des untergeordneten Fensters in der Menüleiste des Frames ab, sodass der Benutzer das untergeordnete Fenster wiederherstellen oder schließen und dem Rahmen Fenstertitel den Titel des untergeordneten Fensters hinzufügen kann.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#11](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]

##  <a name="mdirestore"></a>CMDIChildWnd:: mumgeleitet Store

Diese Member-Funktion wird aufgerufen, um ein untergeordnetes MDI-Fenster von maximierter oder minimierter Größe wiederherzustellen.

```
void MDIRestore();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#12](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]

##  <a name="sethandles"></a>CMDIChildWnd:: Sekunden

Legt die Handles für Menü-und Beschleunigungs Ressourcen fest.

```
void SetHandles(
    HMENU hMenu,
    HACCEL hAccel);
```

### <a name="parameters"></a>Parameter

*hMenu*<br/>
Das Handle einer Menü Ressource.

*hAccel*<br/>
Das Handle einer Zugriffstasten-Ressource.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion werden die Menü-und Zugriffstasten Ressourcen festgelegt, die vom untergeordneten MDI-Fenster Objekt verwendet werden.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel-MDI](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[CMDIFrameWnd-Klasse](../../mfc/reference/cmdiframewnd-class.md)
