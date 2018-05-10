---
title: CMFCRibbonEdit Klasse | Microsoft Docs
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
ms.openlocfilehash: daa6a5976f4f20ba067eed047a4ff83b30550ea9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcribbonedit-class"></a>CMFCRibbonEdit-Klasse
Implementiert ein Bearbeitungssteuerelement, das befindet, ist auf eine menübandleiste.  
  
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
|[CMFCRibbonEdit::CanBeStretched](#canbestretched)|Gibt an, ob die Höhe der `CMFCRibbonEdit` Steuerelement vertikal an die Höhe einer Zeile Menüband erhöhen kann.|  
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|Erstellt ein `CMFCRibbonEdit`-Objekt.|  
|[CMFCRibbonEdit::CopyFrom](#copyfrom)|Kopiert den Status des angegebenen `CMFCRibbonEdit` Objekt mit dem aktuellen `CMFCRibbonEdit` Objekt.|  
|[CMFCRibbonEdit::CreateEdit](#createedit)|Erstellt ein neues Textfeld für die `CMFCRibbonEdit` Objekt.|  
|[CMFCRibbonEdit::DestroyCtrl](#destroyctrl)|Zerstört das `CMFCRibbonEdit`-Objekt.|  
|[CMFCRibbonEdit::DropDownList](#dropdownlist)|Löscht ein Listenfeld.|  
|[CMFCRibbonEdit::EnableSpinButtons](#enablespinbuttons)|Aktiviert, und legt den Bereich von der Drehfeld für das Textfeld fest.|  
|[CMFCRibbonEdit::GetCompactSize](#getcompactsize)|Ruft die komprimierte Größe des der `CFMCRibbonEdit` Objekt.|  
|[CMFCRibbonEdit::GetEditText](#getedittext)|Ruft den Text im Textfeld ab.|  
|[CMFCRibbonEdit::GetIntermediateSize](#getintermediatesize)|Ruft die intermediate Größe ab, die `CMFCRibbonEdit` Objekt.|  
|[CMFCRibbonEdit::GetTextAlign](#gettextalign)|Ruft die Ausrichtung des Texts im Textfeld ab.|  
|[CMFCRibbonEdit::GetWidth](#getwidth)|Ruft die Breite in Pixel ab, der die `CMFCRibbonEdit` Steuerelement.|  
|[CMFCRibbonEdit::HasCompactMode](#hascompactmode)|Gibt an, ob die Anzeige für die Größe der `CMFCRibbonEdit` Steuerelement compact sein kann.|  
|[CMFCRibbonEdit::HasFocus](#hasfocus)|Gibt an, ob die `CMFCRIbbonEdit` Steuerelement den Fokus besitzt.|  
|[CMFCRibbonEdit::HasLargeMode](#haslargemode)|Gibt an, ob die Anzeige für die Größe der `CMFCRibbonEdit` Steuerelement groß sein kann.|  
|[CMFCRibbonEdit::HasSpinButtons](#hasspinbuttons)|Gibt an, ob das Textfeld ein Drehfeld verfügt.|  
|[CMFCRibbonEdit::IsHighlighted](#ishighlighted)|Gibt an, ob die `CMFCRibbonEdit` Steuerelement hervorgehoben ist.|  
|[CMFCRibbonEdit::OnAfterChangeRect](#onafterchangerect)|Vom Framework aufgerufen, wenn die Dimensionen der für das Anzeigerechteck der `CMFCRibbonEdit` Änderungen steuern.|  
|[CMFCRibbonEdit::OnDraw](#ondraw)|Wird aufgerufen, durch das Framework zum Zeichnen der `CMFCRibbonEdit` Steuerelement.|  
|[CMFCRibbonEdit::OnDrawLabelAndImage](#ondrawlabelandimage)|Wird aufgerufen, durch das Framework das Zeichnen der Bezeichnungsfelds und das Abbild für die `CMFCRibbonEdit` Steuerelement.|  
|[CMFCRibbonEdit::OnDrawOnList](#ondrawonlist)|Wird aufgerufen, durch das Framework zum Zeichnen der `CMFCRibbonEdit` Steuerelement in einem Listenfeld Befehle.|  
|[CMFCRibbonEdit::OnEnable](#onenable)|Wird aufgerufen, durch das Framework zu aktivieren oder Deaktivieren der `CMFCRibbonEdit` Steuerelement.|  
|[CMFCRibbonEdit::OnHighlight](#onhighlight)|Vom Framework aufgerufen, wenn der Zeiger betritt oder die Grenzen des verlässt dem `CMFCRibbonEdit` Steuerelement.|  
|[CMFCRibbonEdit::OnKey](#onkey)|Vom Framework aufgerufen, wenn der Benutzer eine Zugriffstasteninfo drückt und die `CMFCRibbonEdit` Steuerelement den Fokus besitzt.|  
|[CMFCRibbonEdit::OnLButtonDown](#onlbuttondown)|Wird aufgerufen, durch das Framework beim Aktualisieren der `CMFCRibbonEdit` steuern, wenn der Benutzer die linke Maustaste auf das Steuerelement drückt.|  
|[CMFCRibbonEdit::OnLButtonUp](#onlbuttonup)|Wird vom Framework aufgerufen, wenn der Benutzer die linke Maustaste loslässt.|  
|[CMFCRibbonEdit::OnRTLChanged](#onrtlchanged)|Wird aufgerufen, durch das Framework beim Aktualisieren der `CMFCRibbonEdit` steuern, wenn das Layout Richtung ändert.|  
|[CMFCRibbonEdit::OnShow](#onshow)|Wird aufgerufen, durch das Framework anzeigen oder Ausblenden der `CMFCRibbonEdit` Steuerelement.|  
|[CMFCRibbonEdit::Redraw](#redraw)|Aktualisiert die Anzeige der `CMFCRibbonEdit` Steuerelement.|  
|[CMFCRibbonEdit::SetACCData](#setaccdata)|Legt die barrierefreiheitsdaten für das `CMFCRibbonEdit` Objekt.|  
|[CMFCRibbonEdit::SetEditText](#setedittext)|Legt den Text im Textfeld fest.|  
|[CMFCRibbonEdit::SetTextAlign](#settextalign)|Legt die Ausrichtung des Texts des Textfelds an.|  
|[CMFCRibbonEdit::SetWidth](#setwidth)|Legt die Breite des Textfelds, das für die `CMFCRibbonEdit` Steuerelement.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCRibbonEdit` -Objekt Drehfeld Schaltflächen neben dem Bearbeitungssteuerelement anzeigen und Festlegen des Texts des Edit-Steuerelements. Dieser Codeausschnitt ist Teil der [MS Office 2007 Demobeispiel für](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxRibbonEdit.h  
  
##  <a name="canbestretched"></a>  CMFCRibbonEdit::CanBeStretched  
 Gibt an, ob die Höhe der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement vertikal an die Höhe einer Zeile Menüband erhöhen kann.  
  
```  
virtual BOOL CanBeStretched();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer `FALSE` zurück.  
  
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
 [in] `nID`  
 Befehls-ID für die `CMFCRibbonEdit` Steuerelement.  
  
 [in] `nWidth`  
 Die Breite in Pixel, der im Textfeld für die `CMFCRibbonEdit` Steuerelement.  
  
 [in] `lpszLabel`  
 Die Bezeichnung für die `CMFCRibbonEdit` Steuerelement.  
  
 [in] `nImage`  
 Index für das kleine Bild für die `CMFCRibbonEdit` Steuerelement. Die Auflistung der kleine Bilder wird von der übergeordneten Menübandkategorie verwaltet.  
  
### <a name="remarks"></a>Hinweise  
 Die `CMFCRibbonEdit` Steuerelement ein großes Bild nicht verwendet.  
  
##  <a name="copyfrom"></a>  CMFCRibbonEdit::CopyFrom  
 Kopiert den Status des angegebenen [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Objekt mit dem aktuellen [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Objekt.  
  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `src`  
 Das `CMFCRibbonEdit`-Quellobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Die `src` Parameter muss vom Typ `CMFCRibbonEdit`.  
  
##  <a name="createedit"></a>  CMFCRibbonEdit::CreateEdit  
 Erstellt ein neues Textfeld für die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Objekt.  
  
```  
virtual CMFCRibbonRichEditCtrl* CreateEdit(
    CWnd* pWndParent,  
    DWORD dwEditStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
 Ein Zeiger auf das übergeordnete Fenster eines der `CMFCRibbonEdit` Objekt.  
  
 [in] `dwEditStyle`  
 Gibt die Art des Textfelds. Können Sie die im Abschnitt "Hinweise" mit aufgeführten Fensterstile Kombinieren der [bearbeiten Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb775464) , werden im Windows SDK beschrieben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das neue Textfeld ein, wenn die Methode erfolgreich ausgeführt wurde; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse ein benutzerdefiniertes Textfeld zu erstellen.  
  
 Sie können die folgenden anwenden [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles) zu einem Textfeld:  
  
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
 Löscht ein Listenfeld.  
  
```  
virtual void DropDownList();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird diese Methode keine Aktion ausgeführt. Überschreiben Sie diese Methode, um zur Auswahl eines Listenfelds anzuzeigen.  
  
##  <a name="enablespinbuttons"></a>  CMFCRibbonEdit::EnableSpinButtons  
 Aktiviert, und legt den Bereich von der Drehfeld für das Textfeld fest.  
  
```  
void EnableSpinButtons(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nMin`  
 Der minimale Wert für das Drehfeld.  
  
 [in] `nMax`  
 Der maximale Wert für das Drehfeld.  
  
### <a name="remarks"></a>Hinweise  
 Drehfeld-Schaltflächen anzeigen eine nach-oben und nach unten zeigenden Pfeil und Benutzern ermöglichen, durch einen festen Satz von Werten zu bewegen.  
  
##  <a name="getcompactsize"></a>  CMFCRibbonEdit::GetCompactSize  
 Ruft die komprimierte Größe des der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Objekt.  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext für das `CMFCRibbonEdit` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die komprimierte Größe des der `CMFCRibbonEdit` Objekt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getedittext"></a>  CMFCRibbonEdit::GetEditText  
 Ruft den Text im Textfeld ab.  
  
```  
CString GetEditText() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Text im Textfeld.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getintermediatesize"></a>  CMFCRibbonEdit::GetIntermediateSize  
 Ruft die intermediate Größe ab, die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Objekt.  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext für das `CMFCRibbonEdit` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die intermediate Größe der `CMFCRibbonEdit` Objekt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gettextalign"></a>  CMFCRibbonEdit::GetTextAlign  
 Ruft die Ausrichtung des Texts im Textfeld ab.  
  
```  
int GetTextAlign() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Textwert Ausrichtung aufgelistet. Finden Sie im Abschnitt "Hinweise" Mögliche Werte.  
  
### <a name="remarks"></a>Hinweise  
 Der zurückgegebene Wert ist eine der folgenden bearbeiten-Steuerelementtypen:  
  
- **ES_LEFT** für die linksbündige Ausrichtung  
  
- **ES_CENTER** für zentrierte Ausrichtung  
  
- **ES_RIGHT** für rechtsbündige Ausrichtung  
  
 Weitere Informationen zu diesen Formaten finden Sie unter [Steuerelementtypen bearbeiten](http://msdn.microsoft.com/library/windows/desktop/bb775464).  
  
##  <a name="getwidth"></a>  CMFCRibbonEdit::GetWidth  
 Ruft die Breite in Pixel ab, der die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
int GetWidth(BOOL bInFloatyMode = FALSE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bInFloatyMode`  
 `TRUE` Wenn die `CMFCRibbonEdit` -Steuerelement befindet sich im unverankerten Modus; anderenfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite in Pixel, der die `CMFCRibbonEdit` Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hascompactmode"></a>  CMFCRibbonEdit::HasCompactMode  
 Gibt an, ob die Anzeige für die Größe der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement compact sein kann.  
  
```  
virtual BOOL HasCompactMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig gibt diese Methode immer `TRUE`. Überschreiben Sie diese Methode, um anzugeben, ob die Größe der Anzeige kompakt sein kann.  
  
##  <a name="hasfocus"></a>  CMFCRibbonEdit::HasFocus  
 Gibt an, ob die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement den Fokus besitzt.  
  
```  
virtual BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die `CMFCRibbonEdit` Steuerelement den Fokus besitzt; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="haslargemode"></a>  CMFCRibbonEdit::HasLargeMode  
 Gibt an, ob die Anzeige für die Größe der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement groß sein kann.  
  
```  
virtual BOOL HasLargeMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer `FALSE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig gibt diese Methode immer `FALSE`. Überschreiben Sie diese Methode, um anzugeben, ob die Anzeige groß sein kann.  
  
##  <a name="hasspinbuttons"></a>  CMFCRibbonEdit::HasSpinButtons  
 Gibt an, ob das Textfeld ein Drehfeld verfügt.  
  
```  
virtual BOOL HasSpinButtons() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn das Textfeld ein Drehfeld enthält. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ishighlighted"></a>  CMFCRibbonEdit::IsHighlighted  
 Gibt an, ob die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement hervorgehoben ist.  
  
```  
virtual BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die `CMFCRibbonEdit` Steuerelement wird andernfalls hervorgehobene `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onafterchangerect"></a>  CMFCRibbonEdit::OnAfterChangeRect  
 Vom Framework aufgerufen, wenn die Dimensionen der für das Anzeigerechteck der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) steuern ändern.  
  
```  
virtual void OnAfterChangeRect(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext für das `CMFCRibbonEdit` Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondraw"></a>  CMFCRibbonEdit::OnDraw  
 Wird aufgerufen, durch das Framework zum Zeichnen der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext für das `CMFCRibbonEdit` Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondrawlabelandimage"></a>  CMFCRibbonEdit::OnDrawLabelAndImage  
 Wird aufgerufen, durch das Framework das Zeichnen der Bezeichnungsfelds und das Abbild für die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
virtual void OnDrawLabelAndImage(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext für das `CMFCRibbonEdit` Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondrawonlist"></a>  CMFCRibbonEdit::OnDrawOnList  
 Wird aufgerufen, durch das Framework zum Zeichnen der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement in einem Listenfeld Befehle.  
  
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
 Zeiger zu einem Gerätekontext für das `CMFCRibbonEdit` Steuerelement.  
  
 [in] `strText`  
 Der Anzeigetext [ ] (../../mfc/reference/cmfcribbonedit-class.md "Cmfcribbonedit Klasse").  
  
 [in] `nTextOffset`  
 Abstand vom links neben dem Listenfeld auf den Anzeigetext in Pixel.  
  
 [in] `rect`  
 Das Anzeigerechteck für die `CMFCRibbonEdit` Steuerelement.  
  
 [in] `bIsSelected`  
 Dieser Parameter wird nicht verwendet.  
  
 [in] `bHighlighted`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Im Listenfeld Befehle zeigt die Menübandsteuerelemente, um Benutzern das Anpassen der schnellen zugriffssymbolleiste zu aktivieren.  
  
##  <a name="onenable"></a>  CMFCRibbonEdit::OnEnable  
 Wird aufgerufen, durch das Framework zu aktivieren oder Deaktivieren der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
virtual void OnEnable(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE` um das Steuerelement zu aktivieren; `FALSE` So deaktivieren Sie das Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onhighlight"></a>  CMFCRibbonEdit::OnHighlight  
 Vom Framework aufgerufen, wenn der Zeiger betritt oder die Grenzen des verlässt dem [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
virtual void OnHighlight(BOOL bHighlight);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bHighlight`  
 `TRUE` Wenn der Mauszeiger innerhalb der Grenzen des befindet der `CMFCRibbonEdit` steuern; anderenfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onkey"></a>  CMFCRibbonEdit::OnKey  
 Vom Framework aufgerufen, wenn der Benutzer eine Zugriffstasteninfo drückt und die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement den Fokus besitzt.  
  
```  
virtual BOOL OnKey(BOOL bIsMenuKey);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bIsMenuKey`  
 `TRUE` Wenn der Zugriffstasteninfo ein Popupmenü angezeigt werden; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn das Ereignis behandelt wurde, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onlbuttondown"></a>  CMFCRibbonEdit::OnLButtonDown  
 Wird aufgerufen, durch das Framework beim Aktualisieren der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) steuern, wenn der Benutzer die linke Maustaste auf das Steuerelement drückt.  
  
```  
virtual void OnLButtonDown(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onlbuttonup"></a>  CMFCRibbonEdit::OnLButtonUp  
 Wird vom Framework aufgerufen, wenn der Benutzer die linke Maustaste loslässt.  
  
```  
virtual void OnLButtonUp(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onrtlchanged"></a>  CMFCRibbonEdit::OnRTLChanged  
 Wird aufgerufen, durch das Framework beim Aktualisieren der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) steuern, wenn das Layout Richtung ändert.  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bIsRTL`  
 `TRUE` Wenn das Layout rechts-nach-links wird; `FALSE` ist das Layout links nach rechts.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onshow"></a>  CMFCRibbonEdit::OnShow  
 Wird aufgerufen, durch das Framework anzeigen oder Ausblenden der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShow`  
 `TRUE` um das Steuerelement anzuzeigen; `FALSE` zum Ausblenden des Steuerelements.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="redraw"></a>  CMFCRibbonEdit::Redraw  
 Aktualisiert die Anzeige der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
virtual void Redraw();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode zeichnet das Anzeigerechteck für die `CMFCRibbonEdit` Objekt durch Aufrufen von indirekt [CWnd::RedrawWindow](http://msdn.microsoft.com/library/windows/desktop/dd162911) mit der `RDW_INVALIDATE`, `RDW_ERASE`, und `RDW_UPDATENOW` flags festlegen.  
  
##  <a name="setaccdata"></a>  CMFCRibbonEdit::SetACCData  
 Legt die barrierefreiheitsdaten für das [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Objekt.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parameter  
 `pParent`  
 Zeiger auf das übergeordnete Fenster für die `CMFCRibbonEdit` Objekt.  
  
 `data`  
 Die barrierefreiheitsdaten für das `CMFCRibbonEdit` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setedittext"></a>  CMFCRibbonEdit::SetEditText  
 Legt den Text im Textfeld fest.  
  
```  
void SetEditText(CString strText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strText`  
 Der Text im Textfeld.  
  
##  <a name="settextalign"></a>  CMFCRibbonEdit::SetTextAlign  
 Legt die Ausrichtung des Texts des Textfelds an.  
  
```  
void SetTextAlign(int nAlign);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nAlign`  
 Ein Textwert Ausrichtung aufgelistet. Finden Sie im Abschnitt "Hinweise" Mögliche Werte.  
  
### <a name="remarks"></a>Hinweise  
 Der Parameter `nAlign` ist eine der folgenden Bearbeitung Steuerelementtypen:  
  
- **ES_LEFT** für die linksbündige Ausrichtung  
  
- **ES_CENTER** für zentrierte Ausrichtung  
  
- **ES_RIGHT** für rechtsbündige Ausrichtung  
  
 Weitere Informationen zu diesen Formaten finden Sie unter [Steuerelementtypen bearbeiten](http://msdn.microsoft.com/library/windows/desktop/bb775464).  
  
##  <a name="setwidth"></a>  CMFCRibbonEdit::SetWidth  
 Legt die Breite des Textfelds, das für die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
void SetWidth(
    int nWidth,  
    BOOL bInFloatyMode = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nWidth`  
 Die Breite des Textfelds in Pixel.  
  
 `bInFloatyMode`  
 `TRUE` zum Festlegen der Breite der unverankerten Modus; `FALSE` zum Festlegen der Breite der für den normalen Modus.  
  
### <a name="remarks"></a>Hinweise  
 Die `CMFCRibbonEdit` Steuerelement verfügt über zwei Breite abhängig von dessen Anzeigemodus: Gleitkomma-Modus und dem normalen Modus.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton-Klasse](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonBar-Klasse](../../mfc/reference/cmfcribbonbar-class.md)