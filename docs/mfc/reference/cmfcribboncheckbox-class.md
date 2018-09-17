---
title: CMFCRibbonCheckBox-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44ccd0c1625e971fd74e913b9618d7f3ae811be5
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712490"
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
wo *nID* ist die kontrollkästchenbefehls-ID und *LpszText* ist die textbezeichnung des Kontrollkästchens.  
  
 Sie können das Kontrollkästchen zum Menübandbereich hinzufügen, indem Sie mithilfe von [cmfcribbonpanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonCheckBox](../../mfc/reference/cmfcribboncheckbox-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribboncheckbox.h  
  
##  <a name="cmfcribboncheckbox"></a>  CMFCRibbonCheckBox::CMFCRibbonCheckBox  
 Der Konstruktor eines Objekts der Menüband-Kontrollkästchen  
  
```  
CMFCRibbonCheckBox(
    UINT nID,  
    LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parameter  
*nID*<br/>
[in] Gibt die Befehls-ID.  
  
*lpszText*<br/>
[in] Gibt die Bezeichnung.  
  
### <a name="return-value"></a>Rückgabewert  
 Erstellt ein Objekt der Menüband-Kontrollkästchen.  
  
### <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie zum Erstellen eines Objekts von der `CMFCRibbonCheckBox` Klasse.  
  
 [!code-cpp[NVC_MFC_RibbonApp#17](../../mfc/reference/codesnippet/cpp/cmfcribboncheckbox-class_1.cpp)]  
  
##  <a name="getcompactsize"></a>  CMFCRibbonCheckBox::GetCompactSize  
 Ruft beim Überschreiben wird die komprimierte Größe des Kontrollkästchens ab.  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
*pDC*<br/>
[in] Zeiger auf die mit dem Kontrollkästchen Verknüpfte CDC.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine `CSize` Objekt, das die komprimierte Größe des Kontrollkästchens enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie nicht überschrieben wird, gibt die fortgeschrittene Größe des Kontrollkästchens zurück.  
  
##  <a name="getintermediatesize"></a>  CMFCRibbonCheckBox::GetIntermediateSize  
 Ruft die fortgeschrittene Größe des Kontrollkästchens.  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
*pDC*<br/>
[in] Zeiger auf den mit diesem Kontrollkästchen Verknüpfte CDC.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CSize` Objekt mit der intermediate Größe des Kontrollkästchens.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie nicht überschrieben wird, berechnet die fortgeschrittene Größe als die Standardgröße des Kontrollkästchen ( `AFX_CHECK_BOX_DEFAULT_SIZE`) sowie die Textgröße zuzüglich der Ränder.  
  
##  <a name="getregularsize"></a>  CMFCRibbonCheckBox::GetRegularSize  
 Ruft die reguläre Größe des Kontrollkästchens ab.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
*pDC*<br/>
[in] Zeiger auf die CDC-Objekt, das mit diesem Kontrollkästchen verknüpft ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine `CSize` Objekt, das die reguläre Größe des Kontrollkästchens enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie nicht überschrieben wird, gibt die fortgeschrittene Größe des Kontrollkästchens zurück.  
  
##  <a name="isdrawtooltipimage"></a>  CMFCRibbonCheckBox::IsDrawTooltipImage  
 Gibt an, ob ein QuickInfo-Image mit dem Kontrollkästchen Verknüpfte vorhanden ist.  
  
```  
virtual BOOL IsDrawTooltipImage() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, wenn das Kontrollkästchen zugeordnet, oder FALSE, wenn kein QuickInfo-Image ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondraw"></a>  CMFCRibbonCheckBox::OnDraw  
 Wird aufgerufen, durch das Framework, das Kontrollkästchen, die mit einem angegebenen Gerätekontext gezeichnet werden soll.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
*pDC*<br/>
[in] Zeiger auf den CDC, in dem Sie das Kontrollkästchen gezeichnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondrawmenuimage"></a>  CMFCRibbonCheckBox::OnDrawMenuImage  
 Wird aufgerufen, durch das Framework zum Zeichnen eines Bilds im Menü für das Kontrollkästchen.  
  
```  
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *CDC**  
 Zeiger auf die mit dem Kontrollkästchen Verknüpfte CDC.  
  
*CRect*<br/>
[in] Ein `CRect` Objekt, das das Rechteck in der zum Zeichnen des Bilds im Menü angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn das Bild gezeichnet wurde, bzw. FALSE, wenn nicht.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie nicht überschrieben wird, gibt "false" zurück.  
  
##  <a name="ondrawonlist"></a>  CMFCRibbonCheckBox::OnDrawOnList  
 Wird aufgerufen, durch das Framework zum Zeichnen des Kontrollkästchens in einem Listenfeld Befehle.  
  
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
*pDC*<br/>
[in] Zeiger auf den Gerätekontext, in dem Sie das Kontrollkästchen gezeichnet werden soll.  
  
*strText*<br/>
[in] Der Anzeigetext.  
  
*nTextOffset*<br/>
[in] Der Abstand in Pixel von der linken Seite des Listenfelds auf den anzuzeigenden Text.  
  
*Rect*<br/>
[in] Das Anzeigerechteck für das Kontrollkästchen.  
  
*bIsSelected*<br/>
[in] True, wenn Sie das Kontrollkästchen ausgewählten bzw. FALSE, wenn nicht.  
  
*bHighlighted*<br/>
[in] True, wenn Sie das Kontrollkästchen hervorgehobenen bzw. FALSE, wenn nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setaccdata"></a>  CMFCRibbonCheckBox::SetACCData  
 Legt die barrierefreiheitsdaten für das Kontrollkästchen.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parameter  
 *pParent*  
 Das übergeordnete Fenster des Kontrollkästchens.  
  
 *data*  
 Die barrierefreiheitsdaten für das Kontrollkästchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer "true" zurück.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird diese Methode legt die barrierefreiheitsdaten für das Kontrollkästchen fest und gibt immer "true" zurück. Setzen Sie diese Methode außer Kraft, um die Barrierefreiheitsdaten festzulegen und einen Wert zurückzugeben, der den Erfolg oder einen Fehler angibt.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonPanel-Klasse](../../mfc/reference/cmfcribbonpanel-class.md)
