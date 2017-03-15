---
title: Klasse CMFCRibbonGalleryMenuButton | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonGalleryMenuButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonGalleryMenuButton class
ms.assetid: 4d459d9b-8b1a-4371-92f6-dc4ce6cc42c8
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: dce01ac22db0ff28e8f07b6d30f6418a61ad68d5
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbongallerymenubutton-class"></a>CMFCRibbonGalleryMenuButton-Klasse
Implementiert eine Menüband-Menüschaltfläche, die Menübandkataloge enthält.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonGalleryMenuButton : public CMFCToolBarMenuButton  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonGalleryMenuButton::CMFCRibbonGalleryMenuButton](#cmfcribbongallerymenubutton)|Erstellt und initialisiert ein `CMFCRibbonGalleryMenuButton`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonGalleryMenuButton::CopyFrom](#copyfrom)|(Überschreibt [CMFCToolBarMenuButton::CopyFrom](../../mfc/reference/cmfctoolbarmenubutton-class.md#copyfrom).)|  
|[CMFCRibbonGalleryMenuButton::CreatePopupMenu](#createpopupmenu)|(Überschreibt [CMFCToolBarMenuButton::CreatePopupMenu](../../mfc/reference/cmfctoolbarmenubutton-class.md#createpopupmenu).)|  
|[CMFCRibbonGalleryMenuButton::GetPalette](#getpalette)||  
|[CMFCRibbonGalleryMenuButton::HasButton](#hasbutton)|(Überschreibt `CMFCToolBarMenuButton::HasButton`.)|  
|[CMFCRibbonGalleryMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|(Überschreibt [CMFCToolBarMenuButton::IsEmptyMenuAllowed](../../mfc/reference/cmfctoolbarmenubutton-class.md#isemptymenuallowed).)|  
  
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
  
##  <a name="a-namecopyfroma--cmfcribbongallerymenubuttoncopyfrom"></a><a name="copyfrom"></a>CMFCRibbonGalleryMenuButton::CopyFrom  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `src`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namecmfcribbongallerymenubuttona--cmfcribbongallerymenubuttoncmfcribbongallerymenubutton"></a><a name="cmfcribbongallerymenubutton"></a>CMFCRibbonGalleryMenuButton::CMFCRibbonGalleryMenuButton  
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
 `uiID`  
 Die Befehls-ID der Schaltfläche. Dies ist der Wert gesendet, der **WM_COMMAND** angezeigt wird, wenn der Benutzer auf diese Schaltfläche klickt.  
  
 `iImage`  
 Der Index des Bilds, das mit der Galerie Menüschaltfläche angezeigt. Die Bilder befinden sich der `imagesPalette` Parameter.  
  
 `lpszText`  
 Der Text, der auf die Schaltfläche angezeigt werden soll.  
  
 `imagesPalette`  
 Enthält die Liste der Images im Katalog angezeigt.  
  
 `uiImagesPaletteResID`  
 Die Ressourcen-ID der Bildliste für die Bilder in der Sammlung angezeigt.  
  
 `cxPaletteImage`  
 Gibt die Breite in Pixel des Bilds in der Sammlung angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Die Katalog-Schaltfläche wird als Popupmenü angezeigt, ein Pfeils enthält. Wenn der Benutzer auf diese Schaltfläche klickt, wird ein Katalog von Bildern angezeigt.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie mithilfe des Konstruktors, der die `CMFCRibbonGalleryMenuButton` Klasse. Dieser Codeausschnitt ist Teil der [MS Office 2007-Demo-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo&#8;](../../mfc/reference/codesnippet/cpp/cmfcribbongallerymenubutton-class_1.cpp)]  
  
##  <a name="a-namecreatepopupmenua--cmfcribbongallerymenubuttoncreatepopupmenu"></a><a name="createpopupmenu"></a>CMFCRibbonGalleryMenuButton::CreatePopupMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CMFCPopupMenu* CreatePopupMenu();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetpalettea--cmfcribbongallerymenubuttongetpalette"></a><a name="getpalette"></a>CMFCRibbonGalleryMenuButton::GetPalette  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCRibbonGallery& GetPalette();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namehasbuttona--cmfcribbongallerymenubuttonhasbutton"></a><a name="hasbutton"></a>CMFCRibbonGalleryMenuButton::HasButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasButton() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameisemptymenualloweda--cmfcribbongallerymenubuttonisemptymenuallowed"></a><a name="isemptymenuallowed"></a>CMFCRibbonGalleryMenuButton::IsEmptyMenuAllowed  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsEmptyMenuAllowed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarMenuButton-Klasse](../../mfc/reference/cmfctoolbarmenubutton-class.md)   
 [CMFCRibbonGallery-Klasse](../../mfc/reference/cmfcribbongallery-class.md)

