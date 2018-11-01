---
title: CDialogEx-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDialogEx
- AFXDIALOGEX/CDialogEx
- AFXDIALOGEX/CDialogEx::CDialogEx
- AFXDIALOGEX/CDialogEx::SetBackgroundColor
- AFXDIALOGEX/CDialogEx::SetBackgroundImage
dev_langs:
- C++
helpviewer_keywords:
- CDialogEx [MFC], CDialogEx
- CDialogEx [MFC], SetBackgroundColor
- CDialogEx [MFC], SetBackgroundImage
ms.assetid: a6ed3b1f-aef8-4b66-ac78-2160faf63c13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 22da29fa98985d00cad9f53c0b80f05a699ead88
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50081684"
---
# <a name="cdialogex-class"></a>CDialogEx-Klasse

Die `CDialogEx`-Klasse gibt die Hintergrundfarbe und das Hintergrundbild eines Dialogfelds an.

## <a name="syntax"></a>Syntax

```
class CDialogEx : public CDialog
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDialogEx::CDialogEx](#cdialogex)|Erstellt ein `CDialogEx`-Objekt.|
|`CDialogEx::~CDialogEx`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDialogEx::SetBackgroundColor](#setbackgroundcolor)|Legt die Hintergrundfarbe des Dialogfelds fest.|
|[CDialogEx::SetBackgroundImage](#setbackgroundimage)|Legt das Hintergrundbild des Dialogfelds fest.|

## <a name="remarks"></a>Hinweise

Zum Verwenden der `CDialogEx`-Klasse müssen Sie Ihre Dialogfeldklasse von der `CDialogEx`-Klasse statt der `CDialog`-Klasse ableiten.

Dialogfeldbilder werden in einer Ressourcendatei gespeichert. Das Framework löscht automatisch jedes Bild, das aus der Ressourcendatei geladen wird. Um das aktuelle Hintergrundbild programmgesteuert zu löschen, rufen die [CDialogEx::SetBackgroundImage](#setbackgroundimage) -Methode auf, oder Implementieren einer `OnDestroy` -Ereignishandler. Beim Aufrufen der [CDialogEx::SetBackgroundImage](#setbackgroundimage) -Methode, übergeben Sie ein `HBITMAP` -Parameter als Bild-Handle. Das `CDialogEx`-Objekt übernimmt den Besitz des Bilds und löscht es, wenn das `m_bAutoDestroyBmp` -Flag `TRUE` ist.

Ein `CDialogEx` Objekt kann es sich um ein übergeordnetes Element von einem [CMFCPopupMenu-Klasse](../../mfc/reference/cmfcpopupmenu-class.md) Objekt. Die [CMFCPopupMenu-Klasse](../../mfc/reference/cmfcpopupmenu-class.md) -Objekt ruft die `CDialogEx::SetActiveMenu` Methode bei der [CMFCPopupMenu-Klasse](../../mfc/reference/cmfcpopupmenu-class.md) -Objekt geöffnet wird. Danach die `CDialogEx` Objekt verarbeitet alle Menüereignisse, bis die [CMFCPopupMenu-Klasse](../../mfc/reference/cmfcpopupmenu-class.md) -Objekt ist geschlossen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxdialogex.h

##  <a name="cdialogex"></a>  CDialogEx::CDialogEx

Erstellt ein `CDialogEx`-Objekt.

```
CDialogEx(
    UINT nIDTemplate,
    CWnd* pParent=NULL);

CDialogEx(
    LPCTSTR lpszTemplateName,
    CWnd* pParentWnd=NULL);
```

### <a name="parameters"></a>Parameter

*nIDTemplate*<br/>
[in] Die Ressourcen-ID, der eine Dialogfeldvorlage.

*lpszTemplateName*<br/>
[in] Der Ressourcenname, der eine Dialogfeldvorlage.

*pParent*<br/>
[in] Ein Zeiger auf das übergeordnete Fenster. Der Standardwert ist NULL.

*pParentWnd*<br/>
[in] Ein Zeiger auf das übergeordnete Fenster. Der Standardwert ist NULL.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="setbackgroundcolor"></a>  CDialogEx::SetBackgroundColor

Legt die Hintergrundfarbe des Dialogfelds fest.

```
void SetBackgroundColor(
    COLORREF color,
    BOOL bRepaint=TRUE);
```

### <a name="parameters"></a>Parameter

*Farbe*<br/>
[in] Ein RGB-Farbwert.

*bRepaint*<br/>
[in] "True", um den Bildschirm sofort zu aktualisieren; andernfalls "false". Der Standardwert ist "true".

### <a name="remarks"></a>Hinweise

##  <a name="setbackgroundimage"></a>  CDialogEx::SetBackgroundImage

Legt das Hintergrundbild des Dialogfelds fest.

```
void SetBackgroundImage(
    HBITMAP hBitmap,
    BackgroundLocation location=BACKGR_TILE,
    BOOL bAutoDestroy=TRUE,
    BOOL bRepaint=TRUE);

BOOL SetBackgroundImage(
    UINT uiBmpResId,
    BackgroundLocation location=BACKGR_TILE,
    BOOL bRepaint=TRUE);
```

### <a name="parameters"></a>Parameter

*hBitmap*<br/>
[in] Ein Handle für das Hintergrundbild.

*uiBmpResId*<br/>
[in] Die Ressourcen-ID des Hintergrundbilds.

*location*<br/>
[in] Eines der `CDialogEx::BackgroundLocation` Werte, die den Speicherort des Bilds angeben. Gültige Werte sind BACKGR_TILE, BACKGR_TOPLEFT, BACKGR_TOPRIGHT, BACKGR_BOTTOMLEFT und BACKGR_BOTTOMRIGHT. Der Standardwert ist BACKGR_TILE.

*bAutoDestroy*<br/>
[in] True, um das Hintergrundbild automatisch zerstört. andernfalls "false".

*bRepaint*<br/>
[in] TRUE, um das Dialogfeld sofort neu zu zeichnen, andernfalls "false".

### <a name="return-value"></a>Rückgabewert

Überladen Sie bei der zweiten Methode Syntax "true", wenn die Methode erfolgreich ist; andernfalls "false".

### <a name="remarks"></a>Hinweise

Das Bild, das Sie angeben, nicht gestreckt, um den Innenbereich des Dialogfelds zu passen.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPopupMenu-Klasse](../../mfc/reference/cmfcpopupmenu-class.md)<br/>
[CContextMenuManager-Klasse](../../mfc/reference/ccontextmenumanager-class.md)
