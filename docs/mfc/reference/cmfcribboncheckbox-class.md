---
title: CMFCRibbonCheckBox Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetCompactSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetIntermediateSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetRegularSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::IsDrawTooltipImage
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDraw
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDrawMenuImage
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDrawOnList
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::SetACCData
dev_langs: C++
helpviewer_keywords:
- CMFCRibbonCheckBox [MFC], CMFCRibbonCheckBox
- CMFCRibbonCheckBox [MFC], GetCompactSize
- CMFCRibbonCheckBox [MFC], GetIntermediateSize
- CMFCRibbonCheckBox [MFC], GetRegularSize
- CMFCRibbonCheckBox [MFC], IsDrawTooltipImage
- CMFCRibbonCheckBox [MFC], OnDraw
- CMFCRibbonCheckBox [MFC], OnDrawMenuImage
- CMFCRibbonCheckBox [MFC], OnDrawOnList
- CMFCRibbonCheckBox [MFC], SetACCData
ms.assetid: 3a6c3891-c8d1-4af0-b954-7b9ab048782a
caps.latest.revision: "30"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bc46d934c99e24b63ef314ef1f63402893c6bb18
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcribboncheckbox-class"></a>CMFCRibbonCheckBox-Klasse
Die `CMFCRibbonCheckBox`-Klasse implementiert ein Kontrollkästchen, das einem Menübandbereich, einer Symbolleiste für den Schnellzugriff oder einem Popupmenü hinzugefügt werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonCheckBox : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonCheckBox::CMFCRibbonCheckBox](#cmfcribboncheckbox)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonCheckBox::GetCompactSize](#getcompactsize)|(Überschreibt [cmfcribbonbutton:: Getcompactsize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).)|  
|[CMFCRibbonCheckBox::GetIntermediateSize](#getintermediatesize)|(Überschreibt [cmfcribbonbutton:: Getintermediatesize](../../mfc/reference/cmfcribbonbutton-class.md#getintermediatesize).)|  
|[CMFCRibbonCheckBox::GetRegularSize](#getregularsize)|(Überschreibt [cmfcribbonbutton:: Getregularsize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).)|  
|[CMFCRibbonCheckBox::IsDrawTooltipImage](#isdrawtooltipimage)|(Überschreibt `CMFCRibbonButton::IsDrawTooltipImage`.)|  
|[CMFCRibbonCheckBox::OnDraw](#ondraw)|(Überschreibt [cmfcribbonbutton:: OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw).)|  
|[CMFCRibbonCheckBox::OnDrawMenuImage](#ondrawmenuimage)|(Überschreibt [cmfcribbonbaseelement:: Ondrawmenuimage](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage).)|  
|[CMFCRibbonCheckBox::OnDrawOnList](#ondrawonlist)|(Überschreibt `CMFCRibbonButton::OnDrawOnList`.)|  
|[CMFCRibbonCheckBox::SetACCData](#setaccdata)|(Überschreibt [cmfcribbonbutton:: Setaccdata](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|  
  
## <a name="remarks"></a>Hinweise  
 Fügen Sie zum Verwenden von `CMFCRibbonCheckBox` in Ihrer Anwendung Ihrem Code den folgenden Konstruktor hinzu:  
  
```  
CMFCRibbonCheckBox (UINT nID, LPCTSTR lpszText)  
```  
`nID` ist hierbei die Kontrollkästchenbefehls-ID, und `lpszText` ist die Textbezeichnung des Kontrollkästchens.  
  
 Sie können mithilfe ein Kontrollkästchens zu einem Menübandbereich hinzufügen [cmfcribbonpanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonCheckBox](../../mfc/reference/cmfcribboncheckbox-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribboncheckbox.h  
  
##  <a name="cmfcribboncheckbox"></a>CMFCRibbonCheckBox::CMFCRibbonCheckBox  
 Konstruktor des Objekts eine Menüband-Kontrollkästchen  
  
```  
CMFCRibbonCheckBox(
    UINT nID,  
    LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Gibt die Befehls-ID.  
  
 [in] `lpszText`  
 Gibt die Beschriftung an.  
  
### <a name="return-value"></a>Rückgabewert  
 Erstellt ein Menüband-Kontrollkästchen-Objekt.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen von ein Objekt von der `CMFCRibbonCheckBox` Klasse.  
  
 [!code-cpp[NVC_MFC_RibbonApp#17](../../mfc/reference/codesnippet/cpp/cmfcribboncheckbox-class_1.cpp)]  
  
##  <a name="getcompactsize"></a>CMFCRibbonCheckBox::GetCompactSize  
 Ruft beim Überschreiben Ruft die komprimierte Größe des Kontrollkästchens auf.  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger auf die `CDC` das Kontrollkästchen zugeordnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine `CSize` Objekt, das die komprimierte Größe des Kontrollkästchens enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn nicht überschrieben wird, gibt die intermediate Größe das Kontrollkästchen zurück.  
  
##  <a name="getintermediatesize"></a>CMFCRibbonCheckBox::GetIntermediateSize  
 Ruft die intermediate Größe des Kontrollkästchens.  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger auf die `CDC` dieses Kontrollkästchen zugeordnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CSize` Objekt, das die intermediate Größe des Kontrollkästchens enthält.  
  
### <a name="remarks"></a>Hinweise  
 Nicht überschrieben wird, berechnet die intermediate Größe als die Standardgröße des Kontrollkästchen ( `AFX_CHECK_BOX_DEFAULT_SIZE`) sowie die Textgröße zuzüglich der Ränder.  
  
##  <a name="getregularsize"></a>CMFCRibbonCheckBox::GetRegularSize  
 Ruft die reguläre Größe des Kontrollkästchens.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger auf die `CDC` mit diesem Kontrollkästchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine `CSize` Objekt, das die reguläre Größe des Kontrollkästchens enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn nicht überschrieben wird, gibt die intermediate Größe das Kontrollkästchen zurück.  
  
##  <a name="isdrawtooltipimage"></a>CMFCRibbonCheckBox::IsDrawTooltipImage  
 Gibt an, ob ein QuickInfo-Image, das Kontrollkästchen zugeordnet ist.  
  
```  
virtual BOOL IsDrawTooltipImage() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` , wenn ein QuickInfo-Image, das Kontrollkästchen zugeordnet ist oder `FALSE` Wenn dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondraw"></a>CMFCRibbonCheckBox::OnDraw  
 Wird aufgerufen, durch das Framework das Kontrollkästchen mit einem angegebenen Gerätekontext gezeichnet werden soll.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger auf die `CDC` in der das Kontrollkästchen gezeichnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondrawmenuimage"></a>CMFCRibbonCheckBox::OnDrawMenuImage  
 Wird aufgerufen, durch das Framework ein Bild im Menü für das Kontrollkästchen gezeichnet werden soll.  
  
```  
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `CDC*`  
 Zeiger auf die `CDC` das Kontrollkästchen zugeordnet.  
  
 [in] `CRect`  
 Ein `CRect` Objekt, das Rechteck in der das Bild gezeichnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` , wenn das Bild gezeichnet wurde, oder `FALSE` Wenn dies nicht.  
  
### <a name="remarks"></a>Hinweise  
 Gibt zurück, wenn nicht außer Kraft gesetzt, `FALSE`.  
  
##  <a name="ondrawonlist"></a>CMFCRibbonCheckBox::OnDrawOnList  
 Wird aufgerufen, durch das Framework das Kontrollkästchen in einem Listenfeld Befehle gezeichnet werden soll.  
  
```  
virtual void OnDrawOnList(
    CDC* pDC,  
    CString strText,  
    int nTextOffset,  
    CRect rect,  
    BOOL bIsSelected,  
    BOOL bHighlighted);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext, in dem das Kontrollkästchen gezeichnet werden soll.  
  
 [in] `strText`  
 Der Anzeigetext.  
  
 [in] `nTextOffset`  
 Der Abstand vom links neben dem Listenfeld auf den Anzeigetext in Pixel.  
  
 [in] `rect`  
 Das Anzeigerechteck für das Kontrollkästchen.  
  
 [in] `bIsSelected`  
 `TRUE`Wenn das Kontrollkästchen aktiviert ist, oder `FALSE` Wenn dies nicht.  
  
 [in] `bHighlighted`  
 `TRUE`Wenn das Kontrollkästchen markiert ist, oder `FALSE` Wenn dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setaccdata"></a>CMFCRibbonCheckBox::SetACCData  
 Legt die barrierefreiheitsdaten für das Kontrollkästchen.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parameter  
 `pParent`  
 Das übergeordnete Fenster des Kontrollkästchens.  
  
 `data`  
 Die barrierefreiheitsdaten für das Kontrollkästchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig legt diese Methode die barrierefreiheitsdaten für das Kontrollkästchen und immer gibt `TRUE`. Setzen Sie diese Methode außer Kraft, um die Barrierefreiheitsdaten festzulegen und einen Wert zurückzugeben, der den Erfolg oder einen Fehler angibt.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonPanel-Klasse](../../mfc/reference/cmfcribbonpanel-class.md)
