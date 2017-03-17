---
title: Klasse CMFCRibbonCheckBox | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCheckBox class
ms.assetid: 3a6c3891-c8d1-4af0-b954-7b9ab048782a
caps.latest.revision: 30
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
ms.openlocfilehash: 9efe04a8e79835b8e51b7045cb86ab2dba68b675
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribboncheckbox-class"></a>CMFCRibbonCheckBox-Klasse
Die `CMFCRibbonCheckBox`-Klasse implementiert ein Kontrollkästchen, das einem Menübandbereich, einer Symbolleiste für den Schnellzugriff oder einem Popupmenü hinzugefügt werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonCheckBox : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonCheckBox::CMFCRibbonCheckBox](#cmfcribboncheckbox)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonCheckBox::GetCompactSize](#getcompactsize)|(Überschreibt [CMFCRibbonButton::GetCompactSize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).)|  
|[CMFCRibbonCheckBox::GetIntermediateSize](#getintermediatesize)|(Überschreibt [CMFCRibbonButton::GetIntermediateSize](../../mfc/reference/cmfcribbonbutton-class.md#getintermediatesize).)|  
|[CMFCRibbonCheckBox::GetRegularSize](#getregularsize)|(Überschreibt [CMFCRibbonButton::GetRegularSize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).)|  
|[CMFCRibbonCheckBox::IsDrawTooltipImage](#isdrawtooltipimage)|(Überschreibt `CMFCRibbonButton::IsDrawTooltipImage`.)|  
|[CMFCRibbonCheckBox::OnDraw](#ondraw)|(Überschreibt [CMFCRibbonButton::OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw).)|  
|[CMFCRibbonCheckBox::OnDrawMenuImage](#ondrawmenuimage)|(Überschreibt [CMFCRibbonBaseElement::OnDrawMenuImage](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage).)|  
|[CMFCRibbonCheckBox::OnDrawOnList](#ondrawonlist)|(Überschreibt `CMFCRibbonButton::OnDrawOnList`.)|  
|[CMFCRibbonCheckBox::SetACCData](#setaccdata)|(Überschreibt [CMFCRibbonButton::SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|  
  
## <a name="remarks"></a>Hinweise  
 Fügen Sie zum Verwenden von `CMFCRibbonCheckBox` in Ihrer Anwendung Ihrem Code den folgenden Konstruktor hinzu:  
  
```  
CMFCRibbonCheckBox (UINT nID, LPCTSTR lpszText)  
```  
`nID` ist hierbei die Kontrollkästchenbefehls-ID, und `lpszText` ist die Textbezeichnung des Kontrollkästchens.  
  
 Sie können ein Kontrollkästchen an einem Menübandbereich hinzufügen, mit [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
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
 Erstellt ein Objekt der Menüband-Kontrollkästchen.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt vom Erstellen der `CMFCRibbonCheckBox` Klasse.  
  
 [!code-cpp[NVC_MFC_RibbonApp&17;](../../mfc/reference/codesnippet/cpp/cmfcribboncheckbox-class_1.cpp)]  
  
##  <a name="getcompactsize"></a>CMFCRibbonCheckBox::GetCompactSize  
 Ruft beim Überschreiben die komprimierte Größe des Kontrollkästchens.  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger auf die `CDC` das Kontrollkästchen zugeordnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein `CSize` -Objekt, das die komprimierte Größe des Kontrollkästchens enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie nicht überschrieben wird, gibt die intermediate Größe des Kontrollkästchens zurück.  
  
##  <a name="getintermediatesize"></a>CMFCRibbonCheckBox::GetIntermediateSize  
 Ruft die intermediate Größe des Kontrollkästchens.  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger auf die `CDC` dieses Kontrollkästchen zugeordnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CSize` Objekt, das die intermediate Größe des Kontrollkästchens.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie nicht überschrieben wird, berechnet die intermediate Größe als die Standardgröße des Kontrollkästchen ( `AFX_CHECK_BOX_DEFAULT_SIZE`) sowie die Textgröße zuzüglich der Ränder.  
  
##  <a name="getregularsize"></a>CMFCRibbonCheckBox::GetRegularSize  
 Ruft die reguläre Größe des Kontrollkästchens.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger auf die `CDC` dieses Kontrollkästchen zugeordnete Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein `CSize` -Objekt, das die reguläre Größe des Kontrollkästchens enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie nicht überschrieben wird, gibt die intermediate Größe des Kontrollkästchens zurück.  
  
##  <a name="isdrawtooltipimage"></a>CMFCRibbonCheckBox::IsDrawTooltipImage  
 Gibt an, ob ein QuickInfo-Image, das Kontrollkästchen zugeordnet ist.  
  
```  
virtual BOOL IsDrawTooltipImage() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` wird ein QuickInfo-Image, das Kontrollkästchen zugeordnet oder `FALSE` ist dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondraw"></a>CMFCRibbonCheckBox::OnDraw  
 Aufgerufen, um das Kontrollkästchen mit einem angegebenen Gerätekontext zu zeichnen.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger auf die `CDC` in dem das Kontrollkästchen gezeichnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondrawmenuimage"></a>CMFCRibbonCheckBox::OnDrawMenuImage  
 Vom Framework aufgerufen wird zum Zeichnen eines Bilds im Menü für das Kontrollkästchen.  
  
```  
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `CDC*`  
 Zeiger auf die `CDC` das Kontrollkästchen zugeordnet.  
  
 [in] `CRect`  
 Ein `CRect` Objekt angeben des Rechtecks, in dem das Bild gezeichnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` das Bild gezeichnet wurde, oder `FALSE` ist dies nicht.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie nicht überschrieben wird, gibt `FALSE`.  
  
##  <a name="ondrawonlist"></a>CMFCRibbonCheckBox::OnDrawOnList  
 Aufgerufen, um das Kontrollkästchen in einem Listenfeld Befehle zu zeichnen.  
  
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
 Der Abstand in Pixel von der linken Seite des Listenfelds an den Anzeigetext.  
  
 [in] `rect`  
 Das Anzeigerechteck für das Kontrollkästchen.  
  
 [in] `bIsSelected`  
 `TRUE`Wenn das Kontrollkästchen aktiviert ist, oder `FALSE` ist dies nicht.  
  
 [in] `bHighlighted`  
 `TRUE`Wenn das Kontrollkästchen markiert ist, oder `FALSE` ist dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setaccdata"></a>CMFCRibbonCheckBox::SetACCData  
 Legt die Eingabehilfen für das Kontrollkästchen fest.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parameter  
 `pParent`  
 Das übergeordnete Fenster des Kontrollkästchens.  
  
 `data`  
 Der Zugriff auf Daten für das Kontrollkästchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig legt diese Methode die Daten zu Eingabehilfen für das Kontrollkästchen und immer gibt `TRUE`. Setzen Sie diese Methode außer Kraft, um die Barrierefreiheitsdaten festzulegen und einen Wert zurückzugeben, der den Erfolg oder einen Fehler angibt.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonPanel-Klasse](../../mfc/reference/cmfcribbonpanel-class.md)

