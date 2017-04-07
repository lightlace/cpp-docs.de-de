---
title: Klasse CMFCRibbonStatusBar | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonStatusBar
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddDynamicElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddExtendedElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddSeparator
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::Create
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::CreateEx
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::FindByID
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::FindElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetCount
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExCount
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExtendedArea
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetSpace
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsBottomFrame
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsExtendedElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsInformationMode
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RecalcLayout
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RemoveAll
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RemoveElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::SetInformation
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::OnDrawInformation
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonStatusBar class
ms.assetid: 921eb57f-3b40-49fa-a38c-3f2fb6dc2893
caps.latest.revision: 37
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
ms.openlocfilehash: 8fc2ec14c3f6320f45128bf36824ce7f9b8de9c5
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonstatusbar-class"></a>CMFCRibbonStatusBar-Klasse
Die `CMFCRibbonStatusBar` -Klasse implementiert ein Statusleisten-Steuerelement, das Menübandelemente anzeigen kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonStatusBar : public CMFCRibbonBar  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonStatusBar::AddDynamicElement](#adddynamicelement)|Status-Menübands hinzugefügt ein dynamisches Element.|  
|[CMFCRibbonStatusBar::AddElement](#addelement)|Status-Menübands hinzugefügt ein neue Multifunktionsleisten-Element.|  
|[CMFCRibbonStatusBar::AddExtendedElement](#addextendedelement)|Die erweiterten Bereich des Status-Menübands hinzugefügt ein Menübandelement.|  
|[CMFCRibbonStatusBar::AddSeparator](#addseparator)|Status-Menübands hinzugefügt Trennzeichen.|  
|[CMFCRibbonStatusBar::Create](#create)|Erstellt eine Menüband-Statusleiste.|  
|[CMFCRibbonStatusBar::CreateEx](#createex)|Erstellt eine Menüband-Statusleiste mit einem erweiterten Format.|  
|[CMFCRibbonStatusBar::FindByID](#findbyid)||  
|[CMFCRibbonStatusBar::FindElement](#findelement)|Gibt einen Zeiger auf das Element mit der angegebenen Befehls-ID.|  
|[CMFCRibbonStatusBar::GetCount](#getcount)|Gibt die Anzahl der Elemente, die im Hauptbereich des Status-Menübands befinden.|  
|[CMFCRibbonStatusBar::GetElement](#getelement)|Gibt einen Zeiger auf das Element, das sich am angegebenen Index befindet.|  
|[CMFCRibbonStatusBar::GetExCount](#getexcount)|Gibt die Anzahl der Elemente, die im erweiterten Bereich des Menübands Status befinden.|  
|[CMFCRibbonStatusBar::GetExElement](#getexelement)|Gibt einen Zeiger auf das Element zurück, das sich an einem angegebenen Index im erweiterten Bereich des Status-Menübands befindet.|  
|[CMFCRibbonStatusBar::GetExtendedArea](#getextendedarea)||  
|[CMFCRibbonStatusBar::GetSpace](#getspace)||  
|[CMFCRibbonStatusBar::IsBottomFrame](#isbottomframe)||  
|[CMFCRibbonStatusBar::IsExtendedElement](#isextendedelement)||  
|[CMFCRibbonStatusBar::IsInformationMode](#isinformationmode)|Bestimmt, ob die Informationen im Modus für die Status-Menübands aktiviert ist.|  
|[CMFCRibbonStatusBar::RecalcLayout](#recalclayout)|(Überschreibt [CMFCRibbonBar::RecalcLayout](../../mfc/reference/cmfcribbonbar-class.md#recalclayout).)|  
|[CMFCRibbonStatusBar::RemoveAll](#removeall)|Entfernt alle Elemente aus dem Menüband-Statusleiste.|  
|[CMFCRibbonStatusBar::RemoveElement](#removeelement)|Entfernt das Element mit einem angegebenen Befehls-ID aus der Menüband-Statusleiste.|  
|[CMFCRibbonStatusBar::SetInformation](#setinformation)|Aktiviert oder deaktiviert die Informationen im Modus für die Menüband-Statusleiste.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonStatusBar::OnDrawInformation](#ondrawinformation)|Zeigt die Zeichenfolge mit Informationen, die angezeigt wird auf der Menüband-Statusleiste angezeigt, wenn der Informationen-Modus aktiviert ist.|  
  
## <a name="remarks"></a>Hinweise  
 Benutzer können die Sichtbarkeit von Menübandelementen auf einem Menüband-Statusleiste mithilfe der integrierten Kontextmenüs für die Menüband-Statusleiste ändern. Sie können hinzufügen oder Entfernen von Elementen dynamisch.  
  
 Eine Menüband-Statusleiste enthält zwei Bereiche: einen Hauptbereich und einem erweiterten Bereich. Der erweiterte Bereich auf der rechten Seite der Status-Menübands und in einer anderen Farbe angezeigt wird, unterscheidet der wichtigste Bereich.  
  
 In der Regel der wichtigste Bereich der Statusleiste zeigt Status Notifications, sowie des erweiterten Bereichs Steuerelemente. Der erweiterte Bereich bleibt sichtbar so lange als möglich, wenn der Benutzer die Menüband-Statusleiste ändert.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCRibbonStatusBar` Klasse. Veranschaulicht, wie ein neues Menübandelement Status-Menübands hinzufügen, ein Menübandelement zu erweiterten Bereich des Status-Menübands hinzufügen ein Trennzeichen fügen Sie hinzu, und aktivieren Sie den normalen Modus für die Menüband-Statusleiste.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#15;](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_1.cpp)]  
[!code-cpp[NVC_MFC_RibbonApp Nr.&16;](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)  
  
 [CMFCRibbonStatusBar](../../mfc/reference/cmfcribbonstatusbar-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribbonstatusbar.h  
  
##  <a name="adddynamicelement"></a>CMFCRibbonStatusBar::AddDynamicElement  
 Status-Menübands hinzugefügt ein dynamisches Element.  
  
```  
void AddDynamicElement(CMFCRibbonBaseElement* pElement);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pElement`  
 Ein Zeiger auf ein dynamisches Element.  
  
### <a name="remarks"></a>Hinweise  
 Im Gegensatz zu regulären Elementen dynamischen Elemente können nicht angepasst werden, und klicken Sie im Menü Anpassen der Statusleiste nicht angezeigt.  
  
##  <a name="addelement"></a>CMFCRibbonStatusBar::AddElement  
 Status-Menübands hinzugefügt ein neue Multifunktionsleisten-Element.  
  
```  
void AddElement(
    CMFCRibbonBaseElement* pElement,  
    LPCTSTR lpszLabel,  
    BOOL bIsVisible=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pElement`  
 Ein Zeiger auf das Element.  
  
 [in] `lpszLabel`  
 Beschriftung des Elements.  
  
 [in] `bIsVisible`  
 `TRUE`Wenn Sie das Element als sichtbar ist, hinzufügen möchten `FALSE` ausgeblendet, wenn das Element hinzugefügt werden soll.  
  
##  <a name="addextendedelement"></a>CMFCRibbonStatusBar::AddExtendedElement  
 Die erweiterten Bereich des Status-Menübands hinzugefügt ein Menübandelement.  
  
```  
void AddExtendedElement(
    CMFCRibbonBaseElement* pElement,  
    LPCTSTR lpszLabel,  
    BOOL bIsVisible=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pElement`  
 Ein Zeiger auf das Element.  
  
 [in] `lpszLabel`  
 Die Beschriftung des Elements.  
  
 [in] `bIsVisible`  
 `TRUE`Wenn Sie das Element als sichtbar ist, hinzufügen möchten `FALSE` ausgeblendet, wenn das Element hinzugefügt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Der erweiterte Bereich befindet sich rechts vom Statusleisten-Steuerelement.  
  
##  <a name="addseparator"></a>CMFCRibbonStatusBar::AddSeparator  
 Status-Menübands hinzugefügt Trennzeichen.  
  
```  
void AddSeparator();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework Fügt eine Trennlinie nach der Methode [CMFCRibbonStatusBar::AddElement](#addelement). Fügt das letzte Element.  
  
##  <a name="create"></a>CMFCRibbonStatusBar::Create  
 Erstellt eine Menüband-Statusleiste.  
  
```  
BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,  
    UINT nID=AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParentWnd`  
 Ein Zeiger auf das übergeordnete Fenster.  
  
 [in] `dwStyle`  
 Eine logische OR-Kombination von Steuerelementtypen.  
  
 [in] `nID`  
 Die Steuerelement-ID der Statusleiste.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Statusleiste erfolgreich erstellt wurde, `FALSE` andernfalls.  
  
##  <a name="createex"></a>CMFCRibbonStatusBar::CreateEx  
 Erstellt eine Menüband-Statusleiste, die einen erweiterten Stil verfügt.  
  
```  
BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle=0,  
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,  
    UINT nID=AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentWnd`  
 Ein Zeiger auf das übergeordnete Fenster.  
  
 `dwCtrlStyle`  
 Eine logische OR-Kombination Weitere Formate für das Status Bar-Objekt erstellen.  
  
 `dwStyle`  
 Das Format des Steuerelements der Statusleiste.  
  
 `nID`  
 Die Steuerelement-ID der Statusleiste.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Statusleiste erfolgreich erstellt wurde, `FALSE` andernfalls.  
  
##  <a name="findbyid"></a>CMFCRibbonStatusBar::FindByID  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCRibbonBaseElement* FindByID(UINT uiCmdID, BOOL = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdID`  
 [in] `BOOL`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="findelement"></a>CMFCRibbonStatusBar::FindElement  
 Gibt einen Zeiger auf das Element mit der angegebenen Befehls-ID.  
  
```  
CMFCRibbonBaseElement* FindElement(UINT uiID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiID`  
 Die ID des Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Element mit der angegebenen Befehls-ID. `NULL`Wenn kein solches Element vorhanden ist.  
  
##  <a name="getcount"></a>CMFCRibbonStatusBar::GetCount  
 Gibt die Anzahl der Elemente, die im Hauptbereich des Status-Menübands befinden.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente, die im Hauptbereich des Status-Menübands befinden.  
  
##  <a name="getelement"></a>CMFCRibbonStatusBar::GetElement  
 Gibt einen Zeiger auf das Element, das sich am angegebenen Index befindet.  
  
```  
CMFCRibbonBaseElement* GetElement(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Gibt einen nullbasierten Index eines Elements, das im Hauptbereich des Statusleisten-Steuerelements befindet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Element, das sich am angegebenen Index befindet. `NULL`Wenn der Index negativ ist oder größer die Anzahl der Elemente in der Statusleiste angezeigt als.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getexcount"></a>CMFCRibbonStatusBar::GetExCount  
 Gibt die Anzahl der Elemente, die im erweiterten Bereich des Menübands Status befinden.  
  
```  
int GetExCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente, die im erweiterten Bereich des Menübands Status befinden.  
  
##  <a name="getexelement"></a>CMFCRibbonStatusBar::GetExElement  
 Gibt einen Zeiger auf das Element zurück, das sich an einem angegebenen Index im erweiterten Bereich des Status-Menübands befindet. Der erweiterte Bereich befindet sich rechts vom Statusleisten-Steuerelement.  
  
```  
CMFCRibbonBaseElement* GetExElement(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Bestimmt den Null-basierten Index eines Elements, das sich im erweiterten Bereich des Statusleisten-Steuerelements befindet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Element, das sich an einem angegebenen Index im erweiterten Bereich des Status-Menübands befindet. `NULL`Wenn `nIndex` ist negativ oder größer als die Anzahl der Elemente im erweiterten Bereich des Status-Menübands.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getextendedarea"></a>CMFCRibbonStatusBar::GetExtendedArea  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL GetExtendedArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rect`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getspace"></a>CMFCRibbonStatusBar::GetSpace  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetSpace() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isbottomframe"></a>CMFCRibbonStatusBar::IsBottomFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsBottomFrame() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isextendedelement"></a>CMFCRibbonStatusBar::IsExtendedElement  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsExtendedElement(CMFCRibbonBaseElement* pElement) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pElement`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isinformationmode"></a>CMFCRibbonStatusBar::IsInformationMode  
 Bestimmt, ob die Informationen im Modus für die Status-Menübands aktiviert ist.  
  
```  
BOOL IsInformationMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Statusleiste in Informationen-Modus ausgeführt werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Im Modus für Informationen die Statusleiste Blendet alle regulären Bereiche und zeigt eine Meldungszeichenfolge.  
  
##  <a name="ondrawinformation"></a>CMFCRibbonStatusBar::OnDrawInformation  
 Zeigt die Zeichenfolge, die angezeigt wird auf der Menüband-Statusleiste angezeigt, wenn der Informationen-Modus aktiviert ist.  
  
```  
virtual void OnDrawInformation(
    CDC* pDC,  
    CString& strInfo,  
    CRect rectInfo);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `strInfo`  
 Die Informationszeichenfolge.  
  
 [in] `rectInfo`  
 Das umschließende Rechteck.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, wenn Sie die Darstellung der Informationszeichenfolge auf der Statusleiste anpassen möchten. Verwenden der [CMFCRibbonStatusBar::SetInformation](#setinformation) Methode, um die Statusleiste Informationen aktiviert werden. In diesem Modus wird die Statusleiste Blendet alle Bereiche und zeigt die Informationszeichenfolge durch angegebene `strInfo`.  
  
##  <a name="recalclayout"></a>CMFCRibbonStatusBar::RecalcLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="removeall"></a>CMFCRibbonStatusBar::RemoveAll  
 Entfernt alle Elemente aus dem Menüband-Statusleiste.  
  
```  
void RemoveAll();
```  
  
##  <a name="removeelement"></a>CMFCRibbonStatusBar::RemoveElement  
 Entfernt das Element mit einem angegebenen Befehls-ID aus der Menüband-Statusleiste.  
  
```  
BOOL RemoveElement(UINT uiID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiID`  
 Die ID des Elements aus der Statusleiste entfernt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn ein Element mit dem angegebenen `uiID` wird entfernt. Andernfalls `FALSE`.  
  
##  <a name="setinformation"></a>CMFCRibbonStatusBar::SetInformation  
 Aktiviert oder deaktiviert die Informationen im Modus für die Menüband-Statusleiste.  
  
```  
void SetInformation(LPCTSTR lpszInfo);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszInfo`  
 Die Informationszeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die Statusleiste im Modus Informationen einzusetzen. In diesem Modus wird die Statusleiste Blendet alle Bereiche und zeigt die Informationszeichenfolge durch angegebene `lpszInfo`.  
  
 Wenn LpszInfo ist `NULL`, die Statusleiste kehrt zum normalen Modus zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBar-Klasse](../../mfc/reference/cmfcribbonbar-class.md)   
 [CMFCRibbonBaseElement-Klasse](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [CMFCRibbonBar-Klasse](../../mfc/reference/cmfcribbonbar-class.md)

