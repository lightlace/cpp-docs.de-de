---
title: Cmfcribbongallerymenubutton-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonGalleryMenuButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::CMFCRibbonGalleryMenuButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::CopyFrom
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::CreatePopupMenu
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::GetPalette
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::HasButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::IsEmptyMenuAllowed
helpviewer_keywords:
- CMFCRibbonGalleryMenuButton [MFC], CMFCRibbonGalleryMenuButton
- CMFCRibbonGalleryMenuButton [MFC], CopyFrom
- CMFCRibbonGalleryMenuButton [MFC], CreatePopupMenu
- CMFCRibbonGalleryMenuButton [MFC], GetPalette
- CMFCRibbonGalleryMenuButton [MFC], HasButton
- CMFCRibbonGalleryMenuButton [MFC], IsEmptyMenuAllowed
ms.assetid: 4d459d9b-8b1a-4371-92f6-dc4ce6cc42c8
ms.openlocfilehash: 0ec295fa64b835064435992a398d4292ccf26f38
ms.sourcegitcommit: bd7ddc044f9083246614b602ef6a758775313214
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68866169"
---
# <a name="cmfcribbongallerymenubutton-class"></a>Cmfcribbongallerymenubutton-Klasse

Implementiert eine Menüband-Menüschaltfläche, die Menübandkataloge enthält.
Weitere Informationen finden Sie im Quellcode, der sich im **Ordner\\VC atlmfc\\\\src MFC** Ihrer Visual Studio-Installation befindet.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonGalleryMenuButton : public CMFCToolBarMenuButton
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Cmfcribbongallerymenubutton:: cmfcribbongallerymenubutton](#cmfcribbongallerymenubutton)|Erstellt und initialisiert ein `CMFCRibbonGalleryMenuButton`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[Cmfcribbongallerymenubutton:: CopyFrom](#copyfrom)|(Überschreibt [cmfctoolbarmenubutton:: CopyFrom](../../mfc/reference/cmfctoolbarmenubutton-class.md#copyfrom).)|
|[CMFCRibbonGalleryMenuButton::CreatePopupMenu](#createpopupmenu)|(Überschreibt [cmfctoolbarmenubutton:: kreatepopupmenu](../../mfc/reference/cmfctoolbarmenubutton-class.md#createpopupmenu).)|
|[CMFCRibbonGalleryMenuButton::GetPalette](#getpalette)||
|[CMFCRibbonGalleryMenuButton::HasButton](#hasbutton)|(Überschreibt `CMFCToolBarMenuButton::HasButton`.)|
|[Cmfcribbongallerymenubutton:: isemptymenuallowed](#isemptymenuallowed)|(Überschreibt [cmfctoolbarmenubutton:: isemptymenuallowed](../../mfc/reference/cmfctoolbarmenubutton-class.md#isemptymenuallowed).)|

### <a name="remarks"></a>Hinweise

Die Katalogmenüschaltfläche wird als ein Popupmenü mit einem Pfeil angezeigt. Wenn der Benutzer auf diese Schaltfläche klickt, wird ein Katalog von Bildern angezeigt. Beim Erstellen einer Katalogmenüschaltfläche müssen Sie eine Bildliste angeben, die diese Bilder enthält.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie ein Katalog von Anführungszeichen in einer Menüschaltfläche angezeigt wird.

```cpp
BOOL CMainFrame::OnShowPopupMenu (CMFCPopupMenu* pMenuPopup)
{
    int nBulletIndex = pMenuBar->CommandToIndex (ID_PARA_BULLETS);

    if (nBulletIndex>= 0)
    {
        CMFCToolBarButton* pExButton =
        pMenuBar->GetButton(nBulletIndex);
        ASSERT_VALID (pExButton);

        CMFCRibbonGalleryMenuButton paletteBullet (
        pExButton->m_nID,
        pExButton->GetImage (),
        pExButton->m_strText);

        InitBulletPalette (&paletteBullet.GetPalette ());

        pMenuBar->ReplaceButton (ID_PARA_BULLETS,
        paletteBullet);
    }
}
```

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)\
└&nbsp;[Cmfctoolbarbutton](../../mfc/reference/cmfctoolbarbutton-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[Cmfctoolbarmenubutton](../../mfc/reference/cmfctoolbarmenubutton-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[Cmfcribbongallerymenubutton](../../mfc/reference/cmfcribbongallerymenubutton-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxribbonpalettegallery. h

##  <a name="copyfrom"></a>Cmfcribbongallerymenubutton:: CopyFrom

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parameter

[in] *src*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="cmfcribbongallerymenubutton"></a>Cmfcribbongallerymenubutton:: cmfcribbongallerymenubutton

Erstellt und initialisiert ein [cmfcribbongallerymenubutton](../../mfc/reference/cmfcribbongallerymenubutton-class.md) -Objekt.

```
CMFCRibbonGalleryMenuButton(
    UINT uiID,
    int iImage,
    LPCTSTR lpszText,
    CMFCToolBarImages& imagesPalette);

CMFCRibbonGalleryMenuButton(
    UINT uiID,
    int iImage,
    LPCTSTR lpszText,
    UINT uiImagesPaletteResID = 0,
    int cxPaletteImage = 0);
```

### <a name="parameters"></a>Parameter

*uiID*<br/>
Die Befehls-ID der Schaltfläche. Dies ist der Wert, der in der WM_COMMAND-Nachricht gesendet wird, wenn der Benutzer auf diese Schaltfläche klickt.

*iImage*<br/>
Der Index des Bilds, das mit der Menü Schaltfläche des Katalogs angezeigt werden soll. Die Bilder werden im *imagespalette* -Parameter gespeichert.

*lpszText*<br/>
Der Text, der auf der Menü Schaltfläche angezeigt werden soll.

*imagesPalette*<br/>
Enthält die Liste der Bilder, die im Katalog angezeigt werden sollen.

*uiImagesPaletteResID*<br/>
Die Ressourcen-ID der Bildliste für die Bilder, die im Katalog angezeigt werden sollen.

*cxPaletteImage*<br/>
Gibt die Breite des Bilds in Pixel an, das im Katalog angezeigt werden soll.

### <a name="remarks"></a>Hinweise

Die Menü Schaltfläche "Katalog" wird als Popup Menü mit einem Pfeil angezeigt. Wenn der Benutzer auf diese Schaltfläche klickt, wird ein Katalog von Bildern angezeigt.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie der Konstruktor der `CMFCRibbonGalleryMenuButton` -Klasse verwendet wird. Dieser Code Ausschnitt ist Teil des Beispiel- [Demo Beispiels von MS Office 2007](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MSOffice2007Demo#8](../../mfc/reference/codesnippet/cpp/cmfcribbongallerymenubutton-class_1.cpp)]

##  <a name="createpopupmenu"></a>Cmfcribbongallerymenubutton:: kreatepopupmenu

```
virtual CMFCPopupMenu* CreatePopupMenu();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getpalette"></a>Cmfcribbongallerymenubutton:: getpalette

```
CMFCRibbonGallery& GetPalette();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="hasbutton"></a>Cmfcribbongallerymenubutton:: hasbutton

```
virtual BOOL HasButton() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="isemptymenuallowed"></a>Cmfcribbongallerymenubutton:: isemptymenuallowed

```
virtual BOOL IsEmptyMenuAllowed() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarMenuButton-Klasse](../../mfc/reference/cmfctoolbarmenubutton-class.md)<br/>
[CMFCRibbonGallery-Klasse](../../mfc/reference/cmfcribbongallery-class.md)
