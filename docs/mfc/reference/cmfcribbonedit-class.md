---
title: CMFCRibbonEdit-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CanBeStretched
- AFXRIBBONEDIT/CMFCRibbonEdit::CopyFrom
- AFXRIBBONEDIT/CMFCRibbonEdit::CreateEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::DestroyCtrl
- AFXRIBBONEDIT/CMFCRibbonEdit::DropDownList
- AFXRIBBONEDIT/CMFCRibbonEdit::EnableSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::GetCompactSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::GetIntermediateSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::GetWidth
- AFXRIBBONEDIT/CMFCRibbonEdit::HasCompactMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasFocus
- AFXRIBBONEDIT/CMFCRibbonEdit::HasLargeMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::IsHighlighted
- AFXRIBBONEDIT/CMFCRibbonEdit::OnAfterChangeRect
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDraw
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawLabelAndImage
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawOnList
- AFXRIBBONEDIT/CMFCRibbonEdit::OnEnable
- AFXRIBBONEDIT/CMFCRibbonEdit::OnHighlight
- AFXRIBBONEDIT/CMFCRibbonEdit::OnKey
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonDown
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonUp
- AFXRIBBONEDIT/CMFCRibbonEdit::OnRTLChanged
- AFXRIBBONEDIT/CMFCRibbonEdit::OnShow
- AFXRIBBONEDIT/CMFCRibbonEdit::Redraw
- AFXRIBBONEDIT/CMFCRibbonEdit::SetACCData
- AFXRIBBONEDIT/CMFCRibbonEdit::SetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::SetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::SetWidth
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonEdit [MFC], CMFCRibbonEdit
- CMFCRibbonEdit [MFC], CanBeStretched
- CMFCRibbonEdit [MFC], CMFCRibbonEdit
- CMFCRibbonEdit [MFC], CopyFrom
- CMFCRibbonEdit [MFC], CreateEdit
- CMFCRibbonEdit [MFC], DestroyCtrl
- CMFCRibbonEdit [MFC], DropDownList
- CMFCRibbonEdit [MFC], EnableSpinButtons
- CMFCRibbonEdit [MFC], GetCompactSize
- CMFCRibbonEdit [MFC], GetEditText
- CMFCRibbonEdit [MFC], GetIntermediateSize
- CMFCRibbonEdit [MFC], GetTextAlign
- CMFCRibbonEdit [MFC], GetWidth
- CMFCRibbonEdit [MFC], HasCompactMode
- CMFCRibbonEdit [MFC], HasFocus
- CMFCRibbonEdit [MFC], HasLargeMode
- CMFCRibbonEdit [MFC], HasSpinButtons
- CMFCRibbonEdit [MFC], IsHighlighted
- CMFCRibbonEdit [MFC], OnAfterChangeRect
- CMFCRibbonEdit [MFC], OnDraw
- CMFCRibbonEdit [MFC], OnDrawLabelAndImage
- CMFCRibbonEdit [MFC], OnDrawOnList
- CMFCRibbonEdit [MFC], OnEnable
- CMFCRibbonEdit [MFC], OnHighlight
- CMFCRibbonEdit [MFC], OnKey
- CMFCRibbonEdit [MFC], OnLButtonDown
- CMFCRibbonEdit [MFC], OnLButtonUp
- CMFCRibbonEdit [MFC], OnRTLChanged
- CMFCRibbonEdit [MFC], OnShow
- CMFCRibbonEdit [MFC], Redraw
- CMFCRibbonEdit [MFC], SetACCData
- CMFCRibbonEdit [MFC], SetEditText
- CMFCRibbonEdit [MFC], SetTextAlign
- CMFCRibbonEdit [MFC], SetWidth
ms.assetid: 9b85f1f2-446b-454e-9af9-104fdad8a897
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c96b5b18530cd9b983e5a4c022883919261cc22c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45701609"
---
# <a name="cmfcribbonedit-class"></a>CMFCRibbonEdit-Klasse
Implementiert ein Bearbeitungssteuerelement, das ist ein Menüband.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonEdit : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|Erstellt ein `CMFCRibbonEdit`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonEdit::CanBeStretched](#canbestretched)|Gibt an, ob die Höhe der `CMFCRibbonEdit` Steuerelement vertikal auf die Höhe einer Zeile Menüband erhöhen kann.|  
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|Erstellt ein `CMFCRibbonEdit`-Objekt.|  
|[CMFCRibbonEdit::CopyFrom](#copyfrom)|Kopiert den Zustand des angegebenen `CMFCRibbonEdit` -Objekt mit dem aktuellen `CMFCRibbonEdit` Objekt.|  
|[CMFCRibbonEdit::CreateEdit](#createedit)|Erstellt ein neues Textfeld für die `CMFCRibbonEdit` Objekt.|  
|[CMFCRibbonEdit::DestroyCtrl](#destroyctrl)|Zerstört das `CMFCRibbonEdit`-Objekt.|  
|[CMFCRibbonEdit::DropDownList](#dropdownlist)|Löscht eine Liste im Dropdownfeld.|  
|[CMFCRibbonEdit::EnableSpinButtons](#enablespinbuttons)|Aktiviert und legt den Wertebereich für die Schaltfläche "starten" für das Textfeld.|  
|[CMFCRibbonEdit::GetCompactSize](#getcompactsize)|Ruft ab, die komprimierte Größe des der `CFMCRibbonEdit` Objekt.|  
|[CMFCRibbonEdit::GetEditText](#getedittext)|Ruft den Text im Textfeld ab.|  
|[CMFCRibbonEdit::GetIntermediateSize](#getintermediatesize)|Ruft die fortgeschrittene Größe ab, der `CMFCRibbonEdit` Objekt.|  
|[CMFCRibbonEdit::GetTextAlign](#gettextalign)|Ruft die Ausrichtung des Texts im Textfeld ab.|  
|[CMFCRibbonEdit::GetWidth](#getwidth)|Ruft die Breite in Pixel ab, der die `CMFCRibbonEdit` Steuerelement.|  
|[CMFCRibbonEdit::HasCompactMode](#hascompactmode)|Gibt an, ob die Größe die Anzeige für die `CMFCRibbonEdit` -Steuerelemente compact werden können.|  
|[CMFCRibbonEdit::HasFocus](#hasfocus)|Gibt an, ob die `CMFCRIbbonEdit` Steuerelement den Fokus hat.|  
|[CMFCRibbonEdit::HasLargeMode](#haslargemode)|Gibt an, ob die Größe die Anzeige für die `CMFCRibbonEdit` Steuerelement groß sein kann.|  
|[CMFCRibbonEdit::HasSpinButtons](#hasspinbuttons)|Gibt an, ob das Textfeld ein Drehfeld verfügt.|  
|[CMFCRibbonEdit::IsHighlighted](#ishighlighted)|Gibt an, ob die `CMFCRibbonEdit` Steuerelement wird hervorgehoben.|  
|[CMFCRibbonEdit::OnAfterChangeRect](#onafterchangerect)|Vom Framework aufgerufen, wenn die Abmessungen des Rechtecks Anzeige für die `CMFCRibbonEdit` -Steuerelements ändert.|  
|[CMFCRibbonEdit::OnDraw](#ondraw)|Wird aufgerufen, durch das Framework zum Zeichnen der `CMFCRibbonEdit` Steuerelement.|  
|[CMFCRibbonEdit::OnDrawLabelAndImage](#ondrawlabelandimage)|Wird aufgerufen, durch das Framework die Bezeichnung und-image für die `CMFCRibbonEdit` Steuerelement.|  
|[CMFCRibbonEdit::OnDrawOnList](#ondrawonlist)|Wird aufgerufen, durch das Framework zum Zeichnen der `CMFCRibbonEdit` -Steuerelement in ein Listenfeld, das Befehle.|  
|[CMFCRibbonEdit::OnEnable](#onenable)|Wird aufgerufen, durch das Framework zu aktivieren oder Deaktivieren der `CMFCRibbonEdit` Steuerelement.|  
|[CMFCRibbonEdit::OnHighlight](#onhighlight)|Vom Framework aufgerufen, wenn der Zeiger betritt oder die Begrenzungen des verlässt der `CMFCRibbonEdit` Steuerelement.|  
|[CMFCRibbonEdit::OnKey](#onkey)|Vom Framework aufgerufen, wenn der Benutzer ein Keytip drückt und die `CMFCRibbonEdit` Steuerelement den Fokus hat.|  
|[CMFCRibbonEdit::OnLButtonDown](#onlbuttondown)|Wird aufgerufen, durch das Framework beim Aktualisieren der `CMFCRibbonEdit` steuern, wenn der Benutzer die linke Maustaste auf das Steuerelement drückt.|  
|[CMFCRibbonEdit::OnLButtonUp](#onlbuttonup)|Wird vom Framework aufgerufen, wenn der Benutzer die linke Maustaste loslässt.|  
|[CMFCRibbonEdit::OnRTLChanged](#onrtlchanged)|Wird aufgerufen, durch das Framework beim Aktualisieren der `CMFCRibbonEdit` steuern, wenn das Layout Richtung ändert.|  
|[CMFCRibbonEdit::OnShow](#onshow)|Wird aufgerufen, durch das Framework anzeigen oder Ausblenden der `CMFCRibbonEdit` Steuerelement.|  
|[CMFCRibbonEdit::Redraw](#redraw)|Aktualisiert die Anzeige der `CMFCRibbonEdit` Steuerelement.|  
|[CMFCRibbonEdit::SetACCData](#setaccdata)|Legt die barrierefreiheitsdaten für das `CMFCRibbonEdit` Objekt.|  
|[CMFCRibbonEdit::SetEditText](#setedittext)|Legt den Text in das Textfeld fest.|  
|[CMFCRibbonEdit::SetTextAlign](#settextalign)|Legt die Ausrichtung des Texts im Textfeld fest.|  
|[CMFCRibbonEdit::SetWidth](#setwidth)|Legt die Breite des Textfelds, das für die `CMFCRibbonEdit` Steuerelement.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCRibbonEdit` Objekt Spin-Schaltflächen neben dem Bearbeitungssteuerelement anzeigen und Festlegen des Texts des Edit-Steuerelements. Dieser Codeausschnitt ist Teil der [MS Office 2007-Demo-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxRibbonEdit.h  
  
##  <a name="canbestretched"></a>  CMFCRibbonEdit::CanBeStretched  
 Gibt an, ob die Höhe der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement vertikal auf die Höhe einer Zeile Menüband erhöhen kann.  
  
```  
virtual BOOL CanBeStretched();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer "false" zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="cmfcribbonedit"></a>  CMFCRibbonEdit::CMFCRibbonEdit  
 Erstellt eine [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Objekt.  
  
```  
CMFCRibbonEdit(
    UINT nID,  
    int nWidth,  
    LPCTSTR lpszLabel = NULL,  
    int nImage = -1);

CMFCRibbonEdit();
```  
  
### <a name="parameters"></a>Parameter  
*nID*<br/>
[in] Befehls-ID für die `CMFCRibbonEdit` Steuerelement.  
  
*nWidth*<br/>
[in] Die Breite in Pixeln, des im Textfeld für die `CMFCRibbonEdit` Steuerelement.  
  
*lpszLabel*<br/>
[in] Die Bezeichnung für die `CMFCRibbonEdit` Steuerelement.  
  
*Nbild*<br/>
[in] Index der kleine Bilder haben die für die Verwendung der `CMFCRibbonEdit` Steuerelement. Die Auflistung der kleinen Bilder wird von der übergeordneten Menübandkategorie verwaltet.  
  
### <a name="remarks"></a>Hinweise  
 Die `CMFCRibbonEdit` Steuerelement ein großes Bild nicht verwendet.  
  
##  <a name="copyfrom"></a>  CMFCRibbonEdit::CopyFrom  
 Kopiert den Zustand des angegebenen [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) -Objekt mit dem aktuellen [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Objekt.  
  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>Parameter  
*src*<br/>
[in] Die Quelle `CMFCRibbonEdit` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die *Src* -Parameter muss vom Typ sein `CMFCRibbonEdit`.  
  
##  <a name="createedit"></a>  CMFCRibbonEdit::CreateEdit  
 Erstellt ein neues Textfeld für die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Objekt.  
  
```  
virtual CMFCRibbonRichEditCtrl* CreateEdit(
    CWnd* pWndParent,  
    DWORD dwEditStyle);
```  
  
### <a name="parameters"></a>Parameter  
*pWndParent*<br/>
[in] Ein Zeiger auf das übergeordnete Fenster der `CMFCRibbonEdit` Objekt.  
  
*dwEditStyle*<br/>
[in] Gibt die Art des Textfelds. Sie können die Window-Stile, die im Abschnitt "Hinweise" mit aufgeführten kombinieren die [Bearbeiten der Stile von Listensteuerelementen](/windows/desktop/Controls/edit-control-styles) , werden im Windows SDK beschrieben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das neue Textfeld ein, wenn die Methode erfolgreich war; andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse ein benutzerdefiniertes Textfeld zu erstellen.  
  
 Sie können die folgenden anwenden [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles) zu einem Textfeld:  
  
- **WS_CHILD**  
  
- **WS_VISIBLE**  
  
- **WS_DISABLED**  
  
- **WS_GROUP**  
  
- **WS_TABSTOP**  
  
##  <a name="destroyctrl"></a>  CMFCRibbonEdit::DestroyCtrl  
 Zerstört die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Objekt.  
  
```  
virtual void DestroyCtrl();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="dropdownlist"></a>  CMFCRibbonEdit::DropDownList  
 Löscht eine Liste im Dropdownfeld.  
  
```  
virtual void DropDownList();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig führt diese Methode keine Aktion. Überschreiben Sie diese Methode Dropdownfeld eine Liste zu löschen.  
  
##  <a name="enablespinbuttons"></a>  CMFCRibbonEdit::EnableSpinButtons  
 Aktiviert und legt den Wertebereich für die Schaltfläche "starten" für das Textfeld.  
  
```  
void EnableSpinButtons(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Parameter  
*nmin.*<br/>
[in] Der kleinste Wert, der die Schaltfläche "starten".  
  
*nmax.*<br/>
[in] Der maximale Wert, der die Schaltfläche "starten".  
  
### <a name="remarks"></a>Hinweise  
 Drehfeld-Schaltflächen eine oben angezeigt und nach-unten-Pfeil und Benutzern ermöglichen, die durch einen festen Satz von Werten zu bewegen.  
  
##  <a name="getcompactsize"></a>  CMFCRibbonEdit::GetCompactSize  
 Ruft ab, die komprimierte Größe des der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Objekt.  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
*pDC*<br/>
[in] Zeiger auf einen Gerätekontext für das `CMFCRibbonEdit` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die komprimierte Größe des der `CMFCRibbonEdit` Objekt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getedittext"></a>  CMFCRibbonEdit::GetEditText  
 Ruft den Text im Textfeld ab.  
  
```  
CString GetEditText() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Text in das Textfeld ein.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getintermediatesize"></a>  CMFCRibbonEdit::GetIntermediateSize  
 Ruft die fortgeschrittene Größe ab, der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Objekt.  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
*pDC*<br/>
[in] Zeiger auf einen Gerätekontext für das `CMFCRibbonEdit` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Zwischenergebnisse Größe der `CMFCRibbonEdit` Objekt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gettextalign"></a>  CMFCRibbonEdit::GetTextAlign  
 Ruft die Ausrichtung des Texts im Textfeld ab.  
  
```  
int GetTextAlign() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Textwert Ausrichtung aufgelistet. Finden Sie im Abschnitt "Hinweise" Mögliche Werte.  
  
### <a name="remarks"></a>Hinweise  
 Der zurückgegebene Wert ist eine der folgenden Stile bearbeiten-Steuerelement:  
  
- **ES_LEFT** für die linksbündige Ausrichtung  
  
- **ES_CENTER** für Ausrichtung zentriert  
  
- **ES_RIGHT** für Rechts-Ausrichtung  
  
 Weitere Informationen zu dieser Stile, finden Sie unter [Bearbeiten der Stile von Listensteuerelementen](/windows/desktop/Controls/edit-control-styles).  
  
##  <a name="getwidth"></a>  CMFCRibbonEdit::GetWidth  
 Ruft die Breite in Pixel ab, der die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
int GetWidth(BOOL bInFloatyMode = FALSE) const;  
```  
  
### <a name="parameters"></a>Parameter  
*bInFloatyMode*<br/>
[in] TRUE, wenn die `CMFCRibbonEdit` Steuerelement befindet sich im unverankerten Modus; andernfalls "false".  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite in Pixel, der die `CMFCRibbonEdit` Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hascompactmode"></a>  CMFCRibbonEdit::HasCompactMode  
 Gibt an, ob die Größe die Anzeige für die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) -Steuerelemente compact werden können.  
  
```  
virtual BOOL HasCompactMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer "true" zurück.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig gibt diese Methode immer "true" zurück. Überschreiben Sie diese Methode, um anzugeben, ob die Größe der Anzeige kompakt sein kann.  
  
##  <a name="hasfocus"></a>  CMFCRibbonEdit::HasFocus  
 Gibt an, ob die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement den Fokus hat.  
  
```  
virtual BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn die `CMFCRibbonEdit` Steuerelement den Fokus hat; andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="haslargemode"></a>  CMFCRibbonEdit::HasLargeMode  
 Gibt an, ob die Größe die Anzeige für die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement groß sein kann.  
  
```  
virtual BOOL HasLargeMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer "false" zurück.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig gibt diese Methode immer "false" zurück. Überschreiben Sie diese Methode, um anzugeben, ob die Größe der Anzeige groß sein kann.  
  
##  <a name="hasspinbuttons"></a>  CMFCRibbonEdit::HasSpinButtons  
 Gibt an, ob das Textfeld ein Drehfeld verfügt.  
  
```  
virtual BOOL HasSpinButtons() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das Textfeld ein Drehfeld hat. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ishighlighted"></a>  CMFCRibbonEdit::IsHighlighted  
 Gibt an, ob die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement wird hervorgehoben.  
  
```  
virtual BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn die `CMFCRibbonEdit` Steuerelement markiert ist; andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onafterchangerect"></a>  CMFCRibbonEdit::OnAfterChangeRect  
 Vom Framework aufgerufen, wenn die Abmessungen des Rechtecks Anzeige für die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuern von Änderungen.  
  
```  
virtual void OnAfterChangeRect(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
*pDC*<br/>
[in] Zeiger auf einen Gerätekontext für das `CMFCRibbonEdit` Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondraw"></a>  CMFCRibbonEdit::OnDraw  
 Wird aufgerufen, durch das Framework zum Zeichnen der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
*pDC*<br/>
[in] Zeiger auf einen Gerätekontext für das `CMFCRibbonEdit` Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondrawlabelandimage"></a>  CMFCRibbonEdit::OnDrawLabelAndImage  
 Wird aufgerufen, durch das Framework die Bezeichnung und-image für die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
virtual void OnDrawLabelAndImage(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
*pDC*<br/>
[in] Zeiger auf einen Gerätekontext für das `CMFCRibbonEdit` Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondrawonlist"></a>  CMFCRibbonEdit::OnDrawOnList  
 Wird aufgerufen, durch das Framework zum Zeichnen der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) -Steuerelement in ein Listenfeld, das Befehle.  
  
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
[in] Zeiger auf einen Gerätekontext für das `CMFCRibbonEdit` Steuerelement.  
  
*strText*<br/>
[in] Der Anzeigetext [ ] (../../mfc/reference/cmfcribbonedit-class.md "Cmfcribbonedit-Klasse").  
  
*nTextOffset*<br/>
[in] Abstand in Pixel von der linken Seite des Listenfelds auf den anzuzeigenden Text.  
  
*Rect*<br/>
[in] Das Anzeigerechteck für die `CMFCRibbonEdit` Steuerelement.  
  
*bIsSelected*<br/>
[in] Dieser Parameter wird nicht verwendet.  
  
*bHighlighted*<br/>
[in] Dieser Parameter wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Im Listenfeld "Befehle" zeigt die Menübandsteuerelemente, damit Benutzer die Schnellzugriff-Symbolleiste angepasst werden können.  
  
##  <a name="onenable"></a>  CMFCRibbonEdit::OnEnable  
 Wird aufgerufen, durch das Framework zu aktivieren oder Deaktivieren der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
virtual void OnEnable(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
*bAktivieren*<br/>
[in] True, um das Steuerelement zu aktivieren. So deaktivieren Sie das Steuerelement wird false ZURÜCKGEGEBEN.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onhighlight"></a>  CMFCRibbonEdit::OnHighlight  
 Vom Framework aufgerufen, wenn der Zeiger betritt oder die Begrenzungen des verlässt der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
virtual void OnHighlight(BOOL bHighlight);
```  
  
### <a name="parameters"></a>Parameter  
*bHighlight*<br/>
[in] TRUE, wenn der Mauszeiger innerhalb der Grenzen des befindet der `CMFCRibbonEdit` steuern; andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onkey"></a>  CMFCRibbonEdit::OnKey  
 Vom Framework aufgerufen, wenn der Benutzer ein Keytip drückt und die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement den Fokus hat.  
  
```  
virtual BOOL OnKey(BOOL bIsMenuKey);
```  
  
### <a name="parameters"></a>Parameter  
*bIsMenuKey*<br/>
[in] True, wenn der Keytip ein Popupmenü angezeigt. andernfalls "false".  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das Ereignis behandelt wurde. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onlbuttondown"></a>  CMFCRibbonEdit::OnLButtonDown  
 Wird aufgerufen, durch das Framework beim Aktualisieren der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) steuern, wenn der Benutzer die linke Maustaste auf das Steuerelement drückt.  
  
```  
virtual void OnLButtonDown(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
*Zeigen Sie*<br/>
[in] Dieser Parameter wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onlbuttonup"></a>  CMFCRibbonEdit::OnLButtonUp  
 Wird vom Framework aufgerufen, wenn der Benutzer die linke Maustaste loslässt.  
  
```  
virtual void OnLButtonUp(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
*Zeigen Sie*<br/>
[in] Dieser Parameter wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onrtlchanged"></a>  CMFCRibbonEdit::OnRTLChanged  
 Wird aufgerufen, durch das Framework beim Aktualisieren der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) steuern, wenn das Layout Richtung ändert.  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>Parameter  
*bIsRTL*<br/>
[in] True, wenn das Layout befindet sich rechts-nach-links. FALSE, wenn das Layout befindet sich links-nach-rechts.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onshow"></a>  CMFCRibbonEdit::OnShow  
 Wird aufgerufen, durch das Framework anzeigen oder Ausblenden der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
*bShow*<br/>
[in] True, um das Steuerelement anzeigen. "False" zum Ausblenden des Steuerelements.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="redraw"></a>  CMFCRibbonEdit::Redraw  
 Aktualisiert die Anzeige der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
virtual void Redraw();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode zeichnet das Anzeigerechteck für die `CMFCRibbonEdit` Objekt, indem Sie indirekt aufrufen [CWnd::RedrawWindow](/windows/desktop/api/winuser/nf-winuser-redrawwindow) mit RDW_INVALIDATE RDW_ERASE und RDW_UPDATENOW Flags festgelegt.  
  
##  <a name="setaccdata"></a>  CMFCRibbonEdit::SetACCData  
 Legt die barrierefreiheitsdaten für das [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Objekt.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parameter  
 *pParent*  
 Zeiger auf das übergeordnete Fenster für die `CMFCRibbonEdit` Objekt.  
  
 *data*  
 Die barrierefreiheitsdaten für das `CMFCRibbonEdit` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer "true" zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setedittext"></a>  CMFCRibbonEdit::SetEditText  
 Legt den Text in das Textfeld fest.  
  
```  
void SetEditText(CString strText);
```  
  
### <a name="parameters"></a>Parameter  
*strText*<br/>
[in] Der Text für das Textfeld ein.  
  
##  <a name="settextalign"></a>  CMFCRibbonEdit::SetTextAlign  
 Legt die Ausrichtung des Texts im Textfeld fest.  
  
```  
void SetTextAlign(int nAlign);
```  
  
### <a name="parameters"></a>Parameter  
*nAlign*<br/>
[in] Ein Textwert Ausrichtung aufgelistet. Finden Sie im Abschnitt "Hinweise" Mögliche Werte.  
  
### <a name="remarks"></a>Hinweise  
 Der Parameter *nAlign* ist eine der folgenden Bearbeitung Stile von Listensteuerelementen:  
  
- ES_LEFT für die linksbündige Ausrichtung  
  
- ES_CENTER für Ausrichtung zentriert  
  
- ES_RIGHT für Rechts-Ausrichtung  
  
 Weitere Informationen zu dieser Stile, finden Sie unter [Bearbeiten der Stile von Listensteuerelementen](/windows/desktop/Controls/edit-control-styles).  
  
##  <a name="setwidth"></a>  CMFCRibbonEdit::SetWidth  
 Legt die Breite des Textfelds, das für die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
void SetWidth(
    int nWidth,  
    BOOL bInFloatyMode = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
*nWidth*<br/>
[in] Die Breite in Pixel des Textfelds.  
  
 *bInFloatyMode*  
 True, um die Breite für den unverankerten Modus festgelegt. "False", um die Breite des für den normalen Modus festzulegen.  
  
### <a name="remarks"></a>Hinweise  
 Die `CMFCRibbonEdit` Steuerelement verfügt über zwei Breite abhängig von der Anzeigemodus: floating-Modus und dem normalen Modus.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton-Klasse](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonBar-Klasse](../../mfc/reference/cmfcribbonbar-class.md)