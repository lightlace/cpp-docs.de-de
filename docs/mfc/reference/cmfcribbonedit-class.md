---
title: Klasse CMFCRibbonEdit | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonEdit
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonEdit class
ms.assetid: 9b85f1f2-446b-454e-9af9-104fdad8a897
caps.latest.revision: 25
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
ms.openlocfilehash: 03eb96bf971b53a2100e6f93bac2f0641f0298e1
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonedit-class"></a>CMFCRibbonEdit-Klasse
Implementiert ein Bearbeitungssteuerelement, die befinden sich auf einer menübandleiste.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonEdit : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|Erstellt ein `CMFCRibbonEdit`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonEdit::CanBeStretched](#canbestretched)|Gibt an, ob die Höhe der `CMFCRibbonEdit` Steuerelement vertikal auf die Höhe einer Zeile Menüband erhöhen kann.|  
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|Erstellt ein `CMFCRibbonEdit`-Objekt.|  
|[CMFCRibbonEdit::CopyFrom](#copyfrom)|Kopiert den Zustand des angegebenen `CMFCRibbonEdit` Objekt mit dem aktuellen `CMFCRibbonEdit` Objekt.|  
|[CMFCRibbonEdit::CreateEdit](#createedit)|Erstellt ein neues Textfeld für den `CMFCRibbonEdit` Objekt.|  
|[CMFCRibbonEdit::DestroyCtrl](#destroyctrl)|Zerstört das `CMFCRibbonEdit`-Objekt.|  
|[CMFCRibbonEdit::DropDownList](#dropdownlist)|Löscht ein Listenfeld.|  
|[CMFCRibbonEdit::EnableSpinButtons](#enablespinbuttons)|Aktiviert, und der Bereich festgelegt, der das Drehfeld für das Textfeld.|  
|[CMFCRibbonEdit::GetCompactSize](#getcompactsize)|Ruft die komprimierte Größe des dem `CFMCRibbonEdit` Objekt.|  
|[CMFCRibbonEdit::GetEditText](#getedittext)|Ruft den Text im Textfeld.|  
|[CMFCRibbonEdit::GetIntermediateSize](#getintermediatesize)|Ruft die intermediate Größe ab, die `CMFCRibbonEdit` Objekt.|  
|[CMFCRibbonEdit::GetTextAlign](#gettextalign)|Ruft die Ausrichtung des Texts im Textfeld ab.|  
|[CMFCRibbonEdit::GetWidth](#getwidth)|Ruft die Breite in Pixel ab, der die `CMFCRibbonEdit` Steuerelement.|  
|[CMFCRibbonEdit::HasCompactMode](#hascompactmode)|Gibt an, ob die Anzeige für die Größe der `CMFCRibbonEdit` Steuerelement compact sein kann.|  
|[CMFCRibbonEdit::HasFocus](#hasfocus)|Gibt an, ob die `CMFCRIbbonEdit` Steuerelement den Fokus hat.|  
|[CMFCRibbonEdit::HasLargeMode](#haslargemode)|Gibt an, ob die Anzeige für die Größe der `CMFCRibbonEdit` Steuerelement groß sein kann.|  
|[CMFCRibbonEdit::HasSpinButtons](#hasspinbuttons)|Gibt an, ob das Textfeld ein Drehfeld verfügt.|  
|[CMFCRibbonEdit::IsHighlighted](#ishighlighted)|Gibt an, ob die `CMFCRibbonEdit` Steuerelement hervorgehoben ist.|  
|[CMFCRibbonEdit::OnAfterChangeRect](#onafterchangerect)|Aufgerufen, wenn die Dimensionen des Rechtecks Anzeige für die `CMFCRibbonEdit` -Steuerelements ändert.|  
|[CMFCRibbonEdit::OnDraw](#ondraw)|Aufgerufen, zum Zeichnen der `CMFCRibbonEdit` Steuerelement.|  
|[CMFCRibbonEdit::OnDrawLabelAndImage](#ondrawlabelandimage)|Aufgerufen, zeichnen die Bezeichnung und das Abbild für die `CMFCRibbonEdit` Steuerelement.|  
|[CMFCRibbonEdit::OnDrawOnList](#ondrawonlist)|Aufgerufen, zum Zeichnen der `CMFCRibbonEdit` Steuerelement in einem Listenfeld Befehle.|  
|[CMFCRibbonEdit::OnEnable](#onenable)|Aufgerufen, aktivieren oder Deaktivieren der `CMFCRibbonEdit` Steuerelement.|  
|[CMFCRibbonEdit::OnHighlight](#onhighlight)|Vom Framework aufgerufen, wenn der Zeiger eingibt oder die Begrenzung des verlässt die `CMFCRibbonEdit` Steuerelement.|  
|[CMFCRibbonEdit::OnKey](#onkey)|Vom Framework aufgerufen, wenn der Benutzer eine Zugriffstasteninfo drückt und die `CMFCRibbonEdit` Steuerelement den Fokus hat.|  
|[CMFCRibbonEdit::OnLButtonDown](#onlbuttondown)|Aufgerufen, zum Aktualisieren der `CMFCRibbonEdit` steuern, wenn der Benutzer die linke Maustaste auf das Steuerelement drückt.|  
|[CMFCRibbonEdit::OnLButtonUp](#onlbuttonup)|Vom Framework aufgerufen, wenn der Benutzer die linke Maustaste loslässt.|  
|[CMFCRibbonEdit::OnRTLChanged](#onrtlchanged)|Aufgerufen, zum Aktualisieren der `CMFCRibbonEdit` steuern, wenn das Layout Richtung ändert.|  
|[CMFCRibbonEdit::OnShow](#onshow)|Aufgerufen, um ein- oder Ausblenden der `CMFCRibbonEdit` Steuerelement.|  
|[CMFCRibbonEdit::Redraw](#redraw)|Aktualisiert die Anzeige der `CMFCRibbonEdit` Steuerelement.|  
|[CMFCRibbonEdit::SetACCData](#setaccdata)|Legt den Zugriff auf Daten für das `CMFCRibbonEdit` Objekt.|  
|[CMFCRibbonEdit::SetEditText](#setedittext)|Legt den Text im Textfeld.|  
|[CMFCRibbonEdit::SetTextAlign](#settextalign)|Legt die Ausrichtung des Texts im Textfeld fest.|  
|[CMFCRibbonEdit::SetWidth](#setwidth)|Legt die Breite des Textfelds für die `CMFCRibbonEdit` Steuerelement.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCRibbonEdit` Objekt, Drehfeld Schaltflächen neben dem Bearbeitungssteuerelement anzeigen, und legen Sie den Text des Bearbeitungssteuerelements. Dieser Codeausschnitt ist Teil der [MS Office 2007-Demo-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo&#7;](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxRibbonEdit.h  
  
##  <a name="a-namecanbestretcheda--cmfcribboneditcanbestretched"></a><a name="canbestretched"></a>CMFCRibbonEdit::CanBeStretched  
 Gibt an, ob die Höhe der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement vertikal auf die Höhe einer Zeile Menüband erhöhen kann.  
  
```  
virtual BOOL CanBeStretched();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer `FALSE` zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namecmfcribbonedita--cmfcribboneditcmfcribbonedit"></a><a name="cmfcribbonedit"></a>CMFCRibbonEdit::CMFCRibbonEdit  
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
 Index des kleinen Bilds, der für die `CMFCRibbonEdit` Steuerelement. Die Auflistung von kleinen Bildern wird von der übergeordneten Menübandkategorie verwaltet.  
  
### <a name="remarks"></a>Hinweise  
 Die `CMFCRibbonEdit` -Steuerelement verwendet kein großes Bild.  
  
##  <a name="a-namecopyfroma--cmfcribboneditcopyfrom"></a><a name="copyfrom"></a>CMFCRibbonEdit::CopyFrom  
 Kopiert den Zustand des angegebenen [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Objekt mit dem aktuellen [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Objekt.  
  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `src`  
 Das `CMFCRibbonEdit`-Quellobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Die `src` Parameter muss vom Typ `CMFCRibbonEdit`.  
  
##  <a name="a-namecreateedita--cmfcribboneditcreateedit"></a><a name="createedit"></a>CMFCRibbonEdit::CreateEdit  
 Erstellt ein neues Textfeld für den [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Objekt.  
  
```  
virtual CMFCRibbonRichEditCtrl* CreateEdit(
    CWnd* pWndParent,  
    DWORD dwEditStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
 Ein Zeiger auf das übergeordnete Fenster von der `CMFCRibbonEdit` Objekt.  
  
 [in] `dwEditStyle`  
 Gibt das Format des Textfelds. Können Sie die Fensterstile finden Sie im Abschnitt "Hinweise" mit Kombinieren der [Steuerelementtypen bearbeiten](http://msdn.microsoft.com/library/windows/desktop/bb775464) die im Windows SDK beschrieben werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das neue Textfeld ein, wenn die Methode erfolgreich war; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse ein benutzerdefiniertes Textfeld zu erstellen.  
  
 Sie können die folgenden anwenden [Fensterstile](../../mfc/reference/window-styles.md) in einem Textfeld:  
  
- **WS_CHILD**  
  
- **WS_VISIBLE**  
  
- **WS_DISABLED**  
  
- **WS_GROUP**  
  
- **WS_TABSTOP**  
  
##  <a name="a-namedestroyctrla--cmfcribboneditdestroyctrl"></a><a name="destroyctrl"></a>CMFCRibbonEdit::DestroyCtrl  
 Zerstört die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Objekt.  
  
```  
virtual void DestroyCtrl();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namedropdownlista--cmfcribboneditdropdownlist"></a><a name="dropdownlist"></a>CMFCRibbonEdit::DropDownList  
 Löscht ein Listenfeld.  
  
```  
virtual void DropDownList();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig bewirkt diese Methode nichts. Überschreiben Sie diese Methode, um ein Listenfeld zu löschen.  
  
##  <a name="a-nameenablespinbuttonsa--cmfcribboneditenablespinbuttons"></a><a name="enablespinbuttons"></a>CMFCRibbonEdit::EnableSpinButtons  
 Aktiviert, und der Bereich festgelegt, der das Drehfeld für das Textfeld.  
  
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
 Drehfeld Schaltflächen zeigt eine nach-oben und Pfeil nach unten und ermöglichen Benutzern, über einen festen Satz von Werten zu verschieben.  
  
##  <a name="a-namegetcompactsizea--cmfcribboneditgetcompactsize"></a><a name="getcompactsize"></a>CMFCRibbonEdit::GetCompactSize  
 Ruft die komprimierte Größe des der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Objekt.  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger auf einen Gerätekontext für das `CMFCRibbonEdit` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die komprimierte Größe des dem `CMFCRibbonEdit` Objekt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetedittexta--cmfcribboneditgetedittext"></a><a name="getedittext"></a>CMFCRibbonEdit::GetEditText  
 Ruft den Text im Textfeld.  
  
```  
CString GetEditText() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Text im Textfeld.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetintermediatesizea--cmfcribboneditgetintermediatesize"></a><a name="getintermediatesize"></a>CMFCRibbonEdit::GetIntermediateSize  
 Ruft die intermediate Größe ab, die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Objekt.  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger auf einen Gerätekontext für das `CMFCRibbonEdit` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Zwischenergebnisse Größe der `CMFCRibbonEdit` Objekt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegettextaligna--cmfcribboneditgettextalign"></a><a name="gettextalign"></a>CMFCRibbonEdit::GetTextAlign  
 Ruft die Ausrichtung des Texts im Textfeld ab.  
  
```  
int GetTextAlign() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Textwert Ausrichtung aufgelistet. Finden Sie im Abschnitt "Hinweise" für die möglichen Werte.  
  
### <a name="remarks"></a>Hinweise  
 Der zurückgegebene Wert ist einer der folgenden Steuerelementtypen für die Bearbeitung:  
  
- **ES_LEFT** für linksbündige Ausrichtung  
  
- **ES_CENTER** für zentriert  
  
- **ES_RIGHT** für rechtsbündige Ausrichtung  
  
 Weitere Informationen über diese Formate finden Sie unter [Steuerelementtypen bearbeiten](http://msdn.microsoft.com/library/windows/desktop/bb775464).  
  
##  <a name="a-namegetwidtha--cmfcribboneditgetwidth"></a><a name="getwidth"></a>CMFCRibbonEdit::GetWidth  
 Ruft die Breite in Pixel ab, der die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
int GetWidth(BOOL bInFloatyMode = FALSE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bInFloatyMode`  
 `TRUE`Wenn die `CMFCRibbonEdit` Steuerelement ist im unverankerten Modus; anderenfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite in Pixel, der die `CMFCRibbonEdit` Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namehascompactmodea--cmfcribbonedithascompactmode"></a><a name="hascompactmode"></a>CMFCRibbonEdit::HasCompactMode  
 Gibt an, ob die Anzeige für die Größe der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement compact sein kann.  
  
```  
virtual BOOL HasCompactMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig gibt diese Methode immer `TRUE`. Überschreiben Sie diese Methode, um anzugeben, ob die Größe der Anzeige kompakt sein kann.  
  
##  <a name="a-namehasfocusa--cmfcribbonedithasfocus"></a><a name="hasfocus"></a>CMFCRibbonEdit::HasFocus  
 Gibt an, ob die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement den Fokus hat.  
  
```  
virtual BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die `CMFCRibbonEdit` Steuerelement den Fokus hat, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namehaslargemodea--cmfcribbonedithaslargemode"></a><a name="haslargemode"></a>CMFCRibbonEdit::HasLargeMode  
 Gibt an, ob die Anzeige für die Größe der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement groß sein kann.  
  
```  
virtual BOOL HasLargeMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer `FALSE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig gibt diese Methode immer `FALSE`. Überschreiben Sie diese Methode, um anzugeben, ob die Größe der Anzeige groß sein kann.  
  
##  <a name="a-namehasspinbuttonsa--cmfcribbonedithasspinbuttons"></a><a name="hasspinbuttons"></a>CMFCRibbonEdit::HasSpinButtons  
 Gibt an, ob das Textfeld ein Drehfeld verfügt.  
  
```  
virtual BOOL HasSpinButtons() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Textfeld ein Drehfeld enthält. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameishighlighteda--cmfcribboneditishighlighted"></a><a name="ishighlighted"></a>CMFCRibbonEdit::IsHighlighted  
 Gibt an, ob die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement hervorgehoben ist.  
  
```  
virtual BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die `CMFCRibbonEdit` -Steuerelement ist, andernfalls markierten `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonafterchangerecta--cmfcribboneditonafterchangerect"></a><a name="onafterchangerect"></a>CMFCRibbonEdit::OnAfterChangeRect  
 Aufgerufen, wenn die Dimensionen des Rechtecks Anzeige für die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) steuern möchten.  
  
```  
virtual void OnAfterChangeRect(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger auf einen Gerätekontext für das `CMFCRibbonEdit` Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameondrawa--cmfcribboneditondraw"></a><a name="ondraw"></a>CMFCRibbonEdit::OnDraw  
 Aufgerufen, zum Zeichnen der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger auf einen Gerätekontext für das `CMFCRibbonEdit` Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameondrawlabelandimagea--cmfcribboneditondrawlabelandimage"></a><a name="ondrawlabelandimage"></a>CMFCRibbonEdit::OnDrawLabelAndImage  
 Aufgerufen, zeichnen die Bezeichnung und das Abbild für die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
virtual void OnDrawLabelAndImage(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger auf einen Gerätekontext für das `CMFCRibbonEdit` Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameondrawonlista--cmfcribboneditondrawonlist"></a><a name="ondrawonlist"></a>CMFCRibbonEdit::OnDrawOnList  
 Aufgerufen, zum Zeichnen der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) -Steuerelement in einem Listenfeld Befehle.  
  
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
 Zeiger auf einen Gerätekontext für das `CMFCRibbonEdit` Steuerelement.  
  
 [in] `strText`  
 Der Anzeigetext [ ](../../mfc/reference/cmfcribbonedit-class.md "cmfcribbonedit class").  
  
 [in] `nTextOffset`  
 Abstand in Pixel von der linken Seite des Listenfelds an den Anzeigetext.  
  
 [in] `rect`  
 Das Anzeigerechteck für die `CMFCRibbonEdit` Steuerelement.  
  
 [in] `bIsSelected`  
 Dieser Parameter wird nicht verwendet.  
  
 [in] `bHighlighted`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Im Listenfeld Befehle zeigt Menübandsteuerelemente, damit Benutzer die Symbolleiste für den Schnellzugriff anpassen können.  
  
##  <a name="a-nameonenablea--cmfcribboneditonenable"></a><a name="onenable"></a>CMFCRibbonEdit::OnEnable  
 Aufgerufen, aktivieren oder Deaktivieren der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
virtual void OnEnable(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`um das Steuerelement zu aktivieren. `FALSE` das Steuerelement deaktivieren.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonhighlighta--cmfcribboneditonhighlight"></a><a name="onhighlight"></a>CMFCRibbonEdit::OnHighlight  
 Vom Framework aufgerufen, wenn der Zeiger eingibt oder die Begrenzung des verlässt die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
virtual void OnHighlight(BOOL bHighlight);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bHighlight`  
 `TRUE`Wenn der Zeiger innerhalb der Grenzen von der `CMFCRibbonEdit` steuern; anderenfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonkeya--cmfcribboneditonkey"></a><a name="onkey"></a>CMFCRibbonEdit::OnKey  
 Vom Framework aufgerufen, wenn der Benutzer eine Zugriffstasteninfo drückt und die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement den Fokus hat.  
  
```  
virtual BOOL OnKey(BOOL bIsMenuKey);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bIsMenuKey`  
 `TRUE`Wenn der Zugriffstasteninfo ein Popupmenü angezeigt werden; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn das Ereignis behandelt wurde, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonlbuttondowna--cmfcribboneditonlbuttondown"></a><a name="onlbuttondown"></a>CMFCRibbonEdit::OnLButtonDown  
 Aufgerufen, zum Aktualisieren der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) steuern, wenn der Benutzer die linke Maustaste auf das Steuerelement drückt.  
  
```  
virtual void OnLButtonDown(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonlbuttonupa--cmfcribboneditonlbuttonup"></a><a name="onlbuttonup"></a>CMFCRibbonEdit::OnLButtonUp  
 Vom Framework aufgerufen, wenn der Benutzer die linke Maustaste loslässt.  
  
```  
virtual void OnLButtonUp(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonrtlchangeda--cmfcribboneditonrtlchanged"></a><a name="onrtlchanged"></a>CMFCRibbonEdit::OnRTLChanged  
 Aufgerufen, zum Aktualisieren der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) steuern, wenn das Layout Richtung ändert.  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bIsRTL`  
 `TRUE`Wenn der rechts-nach-links wird; `FALSE` ist das Layout links nach rechts.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonshowa--cmfcribboneditonshow"></a><a name="onshow"></a>CMFCRibbonEdit::OnShow  
 Aufgerufen, um ein- oder Ausblenden der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShow`  
 `TRUE`zum Anzeigen der; `FALSE` zum Ausblenden des Steuerelements.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameredrawa--cmfcribboneditredraw"></a><a name="redraw"></a>CMFCRibbonEdit::Redraw  
 Aktualisiert die Anzeige der [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
virtual void Redraw();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode zeichnet das Anzeigerechteck für die `CMFCRibbonEdit` durch indirekt aufrufen [CWnd::RedrawWindow](http://msdn.microsoft.com/library/windows/desktop/dd162911) mit der `RDW_INVALIDATE`, `RDW_ERASE`, und `RDW_UPDATENOW` flags festlegen.  
  
##  <a name="a-namesetaccdataa--cmfcribboneditsetaccdata"></a><a name="setaccdata"></a>CMFCRibbonEdit::SetACCData  
 Legt den Zugriff auf Daten für die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Objekt.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parameter  
 `pParent`  
 Zeiger auf das übergeordnete Fenster für die `CMFCRibbonEdit` Objekt.  
  
 `data`  
 Der Zugriff auf Daten für das `CMFCRibbonEdit` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetedittexta--cmfcribboneditsetedittext"></a><a name="setedittext"></a>CMFCRibbonEdit::SetEditText  
 Legt den Text im Textfeld.  
  
```  
void SetEditText(CString strText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strText`  
 Der Text für das Textfeld.  
  
##  <a name="a-namesettextaligna--cmfcribboneditsettextalign"></a><a name="settextalign"></a>CMFCRibbonEdit::SetTextAlign  
 Legt die Ausrichtung des Texts im Textfeld fest.  
  
```  
void SetTextAlign(int nAlign);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nAlign`  
 Ein Textwert Ausrichtung aufgelistet. Finden Sie im Abschnitt "Hinweise" für die möglichen Werte.  
  
### <a name="remarks"></a>Hinweise  
 Der Parameter `nAlign` ist einer der folgenden Bearbeitung Steuerelementtypen:  
  
- **ES_LEFT** für linksbündige Ausrichtung  
  
- **ES_CENTER** für zentriert  
  
- **ES_RIGHT** für rechtsbündige Ausrichtung  
  
 Weitere Informationen über diese Formate finden Sie unter [Steuerelementtypen bearbeiten](http://msdn.microsoft.com/library/windows/desktop/bb775464).  
  
##  <a name="a-namesetwidtha--cmfcribboneditsetwidth"></a><a name="setwidth"></a>CMFCRibbonEdit::SetWidth  
 Legt die Breite des Textfelds für die [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Steuerelement.  
  
```  
void SetWidth(
    int nWidth,  
    BOOL bInFloatyMode = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nWidth`  
 Die Breite in Pixel des Textfelds.  
  
 `bInFloatyMode`  
 `TRUE`um die Breite für Gleitkomma-Modus festgelegt. `FALSE` die Breite für den normalen Modus festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Die `CMFCRibbonEdit` Steuerelement hat zwei Breite abhängig von dessen Anzeigemodus: Gleitkomma-Modus und dem normalen Modus.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton-Klasse](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonBar-Klasse](../../mfc/reference/cmfcribbonbar-class.md)
