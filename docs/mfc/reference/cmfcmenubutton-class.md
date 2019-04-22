---
title: CMFCMenuButton-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::PreTranslateMessage
- AFXMENUBUTTON/CMFCMenuButton::SizeToContent
- AFXMENUBUTTON/CMFCMenuButton::m_bOSMenu
- AFXMENUBUTTON/CMFCMenuButton::m_bRightArrow
- AFXMENUBUTTON/CMFCMenuButton::m_bStayPressed
- AFXMENUBUTTON/CMFCMenuButton::m_hMenu
- AFXMENUBUTTON/CMFCMenuButton::m_nMenuResult
helpviewer_keywords:
- CMFCMenuButton [MFC], CMFCMenuButton
- CMFCMenuButton [MFC], PreTranslateMessage
- CMFCMenuButton [MFC], SizeToContent
- CMFCMenuButton [MFC], m_bOSMenu
- CMFCMenuButton [MFC], m_bRightArrow
- CMFCMenuButton [MFC], m_bStayPressed
- CMFCMenuButton [MFC], m_hMenu
- CMFCMenuButton [MFC], m_nMenuResult
ms.assetid: 53d3d459-1e5a-47c5-8b7f-2e61f6af5187
ms.openlocfilehash: cbdf4005ee1a0249e7ed2b5f1d50621fb951f64f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58777362"
---
# <a name="cmfcmenubutton-class"></a>CMFCMenuButton-Klasse

Eine Schaltfläche, die ein Popupmenü anzeigt und die vom Benutzer gewählte Menüoption meldet.

## <a name="syntax"></a>Syntax

```
class CMFCMenuButton : public CMFCButton
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCMenuButton::CMFCMenuButton](#cmfcmenubutton)|Erstellt ein `CMFCMenuButton`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCMenuButton::PreTranslateMessage](#pretranslatemessage)|Wird aufgerufen, durch das Framework um fenstermeldungen zu übersetzen, bevor sie gesendet werden. (Überschreibt `CMFCButton::PreTranslateMessage`.)|
|[CMFCMenuButton::SizeToContent](#sizetocontent)|Ändert die Größe der Schaltfläche gemäß seiner Größe für Text- und Bilddateien.|

### <a name="data-members"></a>Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CMFCMenuButton::m_bOSMenu](#m_bosmenu)|Gibt an, ob die Standard-System-Popupmenü angezeigt oder verwendet [CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu).|
|[CMFCMenuButton::m_bRightArrow](#m_brightarrow)|Gibt an, ob das Popupmenü unterhalb und rechts neben der Schaltfläche angezeigt wird.|
|[CMFCMenuButton::m_bStayPressed](#m_bstaypressed)|Gibt an, ob die Menüschaltfläche Zustand wechselt, nachdem der Benutzer die loslässt.|
|[CMFCMenuButton::m_hMenu](#m_hmenu)|Ein Handle für das angefügte Menü "Windows".|
|[CMFCMenuButton::m_nMenuResult](#m_nmenuresult)|Ein Bezeichner, der gibt an, welches Element werden die Benutzer aus dem Popupmenü ausgewählt.|

## <a name="remarks"></a>Hinweise

Die `CMFCMenuButton` abgeleitete Klasse wird die [CMFCButton-Klasse](../../mfc/reference/cmfcbutton-class.md) die wiederum von abgeleitet ist, die [CButton-Klasse](../../mfc/reference/cbutton-class.md). Aus diesem Grund können Sie `CMFCMenuButton` in Ihrem Code die gleiche Weise Sie verwenden `CButton`.

Bei der Erstellung einer `CMFCMenuButton`, Sie müssen ein Handle übergeben, zu dem Popup-Menü verknüpft. Als Nächstes rufen Sie die Funktion `CMFCMenuButton::SizeToContent`. `CMFCMenuButton::SizeToContent` überprüft, ob die Größe der Schaltfläche ist ausreichend, um einen Pfeil enthalten, der auf den Speicherort verweist, in dem das Popup-Fenster - nämlich unter oder rechts neben der Schaltfläche angezeigt wird.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie das Handle des Menüs auf die Schaltfläche mit den angefügten festzulegen, Ändern der Größe der Schaltfläche gemäß seiner Größe für Text- und Bilddateien, und legen Sie im Popupmenü aus, das vom Framework angezeigt wird. Dieser Codeausschnitt ist Teil der [Beispiel neue Steuerelemente](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#38](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#39](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxmenubutton.h

##  <a name="cmfcmenubutton"></a>  CMFCMenuButton::CMFCMenuButton

Erstellt ein neues [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md) Objekt.

```
CMFCMenuButton();
```

##  <a name="m_bosmenu"></a>  CMFCMenuButton::m_bOSMenu

Eine boolesche Membervariable, die Popup-Menü angibt, zeigt das Framework.

```
BOOL m_bOSMenu;
```

### <a name="remarks"></a>Hinweise

Wenn `m_bOSMenu` ist "true", das Framework Ruft die geerbte `TrackPopupMenu` -Standardmethode für dieses Objekt. Andernfalls ruft das Framework [CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu).

##  <a name="m_brightarrow"></a>  CMFCMenuButton::m_bRightArrow

Eine boolesche Membervariable, die den Speicherort des Popupmenüs angibt.

```
BOOL m_bRightArrow;
```

### <a name="remarks"></a>Hinweise

Wenn der Benutzer die Menüschaltfläche drückt, zeigt die Anwendung ein Popup-Menü aus. Das Framework wird die Popup-Menü unter der Schaltfläche oder auf die rechts neben der Schaltfläche angezeigt. Die Schaltfläche mit der verfügt auch über einen kleinen Pfeil, der angibt, wo Sie im Popupmenü angezeigt wird. Wenn `m_bRightArrow` TRUE ist, zeigt das Framework das Popupmenü rechts neben der Schaltfläche. Andernfalls wird die Popup-Menü unter der Schaltfläche angezeigt.

##  <a name="m_bstaypressed"></a>  CMFCMenuButton::m_bStayPressed

Eine boolesche Membervariable, die angibt, ob die Menüschaltfläche angezeigt wird gedrückt, während der Benutzer eine Auswahl aus dem Popupmenü trifft.

```
BOOL m_bStayPressed;
```

### <a name="remarks"></a>Hinweise

Wenn die `m_bStayPressed` Member "false", wird die Schaltfläche wird nicht gedrückt werden, wenn die Verwendungen auf die Schaltfläche klickt. In diesem Fall zeigt das Framework nur im Popupmenü.

Wenn die `m_bStayPressed` Member ist "true", die Menüschaltfläche wird gedrückt, wenn der Benutzer die Schaltfläche klickt. Nachdem der Benutzer die Popup-Menü, indem Sie eine Auswahl treffen oder stornieren schließt bleibt bis gedrückten.

##  <a name="m_hmenu"></a>  CMFCMenuButton::m_hMenu

Das Handle für das angefügte Menü.

```
HMENU m_hMenu;
```

### <a name="remarks"></a>Hinweise

Das Framework zeigt das Menü, das durch diese Membervariable angegeben wird, wenn der Benutzer die Schaltfläche klickt.

##  <a name="m_nmenuresult"></a>  CMFCMenuButton::m_nMenuResult

Eine ganze Zahl, die zeigt, an welches Element wählt der Benutzer aus dem Popupmenü.

```
int m_nMenuResult;
```

### <a name="remarks"></a>Hinweise

Der Wert dieser Variablen Member ist 0 (null), wenn der Benutzer das Menü abbricht, ohne eine Auswahl zu treffen, oder wenn ein Fehler auftritt.

##  <a name="pretranslatemessage"></a>  CMFCMenuButton::PreTranslateMessage

Wird aufgerufen, durch das Framework um fenstermeldungen zu übersetzen, bevor sie gesendet werden.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parameter

*pMsg*<br/>
[in] Verweist auf eine [MSG](/windows/desktop/api/winuser/ns-winuser-tagmsg) -Struktur, die zu verarbeitende Meldung enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Meldung übersetzt wurde, und nicht weitergeleitet werden soll; 0, wenn die Nachricht nicht übersetzt wurde und weitergeleitet werden soll.

### <a name="remarks"></a>Hinweise

##  <a name="sizetocontent"></a>  CMFCMenuButton::SizeToContent

Ändert die Größe der Schaltfläche entsprechend die Textgröße und die Größe des Abbilds.

```
virtual CSize SizeToContent(BOOL bCalcOnly = FALSE);
```

### <a name="parameters"></a>Parameter

*bCalcOnly*<br/>
[in] Ein boolescher Parameter, der angibt, ob diese Methode ändert die Größe der Schaltfläche.

### <a name="return-value"></a>Rückgabewert

Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt, das die neue Größe für die Schaltfläche angibt.

### <a name="remarks"></a>Hinweise

Wenn Sie diese Funktion aufrufen und *bCalcOnly* ist "true", `SizeToContent` wird nur die neue Größe der Schaltfläche "berechnen".

Die neue Größe der Schaltfläche wird berechnet, um den Schaltflächentext, Bild und Pfeil zu passen. Es fügt auch das Framework vordefinierte Rändern 10 Pixel für die horizontale Kante und 5 Pixel für die vertikale Kante hinzu.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCButton-Klasse](../../mfc/reference/cmfcbutton-class.md)
