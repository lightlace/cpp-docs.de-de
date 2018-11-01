---
title: CMFCRibbonGalleryMenuButton-Klasse
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
ms.openlocfilehash: 99a48c62b7e47e1c2de1a4d2c473ebde6fc0da22
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50516989"
---
# <a name="cmfcribbongallerymenubutton-class"></a>CMFCRibbonGalleryMenuButton-Klasse

Implementiert eine Menüband-Menüschaltfläche, die Menübandkataloge enthält.
Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonGalleryMenuButton : public CMFCToolBarMenuButton
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCRibbonGalleryMenuButton::CMFCRibbonGalleryMenuButton](#cmfcribbongallerymenubutton)|Erstellt und initialisiert ein `CMFCRibbonGalleryMenuButton`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCRibbonGalleryMenuButton::CopyFrom](#copyfrom)|(Überschreibt [cmfctoolbarmenubutton:: CopyFrom](../../mfc/reference/cmfctoolbarmenubutton-class.md#copyfrom).)|
|[CMFCRibbonGalleryMenuButton::CreatePopupMenu](#createpopupmenu)|(Überschreibt [cmfctoolbarmenubutton:: CreatePopupMenu](../../mfc/reference/cmfctoolbarmenubutton-class.md#createpopupmenu).)|
|[CMFCRibbonGalleryMenuButton::GetPalette](#getpalette)||
|[CMFCRibbonGalleryMenuButton::HasButton](#hasbutton)|(Überschreibt `CMFCToolBarMenuButton::HasButton`.)|
|[CMFCRibbonGalleryMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|(Überschreibt [cmfctoolbarmenubutton:: Isemptymenuallowed](../../mfc/reference/cmfctoolbarmenubutton-class.md#isemptymenuallowed).)|

### <a name="remarks"></a>Hinweise

Die Katalogmenüschaltfläche wird als ein Popupmenü mit einem Pfeil angezeigt. Wenn der Benutzer auf diese Schaltfläche klickt, wird ein Katalog von Bildern angezeigt. Beim Erstellen einer Katalogmenüschaltfläche müssen Sie eine Bildliste angeben, die diese Bilder enthält.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie ein Katalog von Anführungszeichen in einer Menüschaltfläche angezeigt wird.

```
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

[CObject](../../mfc/reference/cobject-class.md) [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md) [CMFCRibbonGalleryMenuButton](../../mfc/reference/cmfcribbongallerymenubutton-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxRibbonPaletteGallery.h

##  <a name="copyfrom"></a>  CMFCRibbonGalleryMenuButton::CopyFrom

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parameter

[in] *Src*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="cmfcribbongallerymenubutton"></a>  CMFCRibbonGalleryMenuButton::CMFCRibbonGalleryMenuButton

Erstellt und initialisiert ein [CMFCRibbonGalleryMenuButton](../../mfc/reference/cmfcribbongallerymenubutton-class.md) Objekt.

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
Die Befehls-ID der Schaltfläche. Dies ist der Wert in die WM_COMMAND-Meldung gesendet wird, wenn der Benutzer diese Schaltfläche klickt.

*iImage*<br/>
Der Index des Bildes, das mit die katalogmenüschaltfläche angezeigt werden soll. Die Images gespeichert sind, der *ImagesPalette* Parameter.

*lpszText*<br/>
Der Text, auf die Menüschaltfläche angezeigt werden sollen.

*imagesPalette*<br/>
Enthält die Liste der Images im Katalog angezeigt.

*uiImagesPaletteResID*<br/>
Die Ressourcen-ID der Liste der Bilder, für die Images im Katalog angezeigt.

*cxPaletteImage*<br/>
Gibt die Breite in Pixel des Bildes, das im Katalog angezeigt.

### <a name="remarks"></a>Hinweise

Die katalogmenüschaltfläche wird als ein Popupmenü angezeigt, die einen Pfeil aufweist. Wenn der Benutzer auf diese Schaltfläche klickt, wird ein Katalog von Bildern angezeigt.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie den Konstruktor, der die `CMFCRibbonGalleryMenuButton` Klasse. Dieser Codeausschnitt ist Teil der [MS Office 2007-Demo-Beispiel](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MSOffice2007Demo#8](../../mfc/reference/codesnippet/cpp/cmfcribbongallerymenubutton-class_1.cpp)]

##  <a name="createpopupmenu"></a>  CMFCRibbonGalleryMenuButton::CreatePopupMenu

```
virtual CMFCPopupMenu* CreatePopupMenu();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getpalette"></a>  CMFCRibbonGalleryMenuButton::GetPalette

```
CMFCRibbonGallery& GetPalette();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="hasbutton"></a>  CMFCRibbonGalleryMenuButton::HasButton

```
virtual BOOL HasButton() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="isemptymenuallowed"></a>  CMFCRibbonGalleryMenuButton::IsEmptyMenuAllowed

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
