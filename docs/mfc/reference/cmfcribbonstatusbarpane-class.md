---
title: Klasse CMFCRibbonStatusBarPane | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonStatusBarPane
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonStatusBarPane class
ms.assetid: 5d034c3c-ecca-4267-b88c-0f55a2884dd0
caps.latest.revision: 31
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
ms.openlocfilehash: a101e50f55efab44e4cb66d314b2426228dbc5c0
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonstatusbarpane-class"></a>CMFCRibbonStatusBarPane-Klasse
Die `CMFCRibbonStatusBarPane` -Klasse implementiert ein Menübandelement, das eine Menüband-Statusleiste hinzugefügt werden können.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonStatusBarPane : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane](#cmfcribbonstatusbarpane)|Erstellt und initialisiert ein `CMFCRibbonStatusBarPane`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::GetAlmostLargeText](#getalmostlargetext)|Gibt die Zeichenfolge, die die längste Zeichenfolge definiert, die im Bereich ungekürzt angezeigt werden.|  
|[CMFCRibbonStatusBarPane::GetTextAlign](#gettextalign)|Gibt die aktuelle Einstellung der Ausrichtung des Texts zurück.|  
|[CMFCRibbonStatusBarPane::IsAnimation](#isanimation)|Bestimmt, ob die Animation ausgeführt wird.|  
|[CMFCRibbonStatusBarPane::IsExtended](#isextended)|Bestimmt, ob der Bereich im erweiterten Bereich des Status-Menübands befindet.|  
|[CMFCRibbonStatusBarPane::OnDrawBorder](#ondrawborder)|(Überschreibt [CMFCRibbonButton::OnDrawBorder](../../mfc/reference/cmfcribbonbutton-class.md#ondrawborder).)|  
|[CMFCRibbonStatusBarPane::OnFillBackground](#onfillbackground)|(Überschreibt [CMFCRibbonButton::OnFillBackground](../../mfc/reference/cmfcribbonbutton-class.md#onfillbackground).)|  
|[CMFCRibbonStatusBarPane::SetAlmostLargeText](#setalmostlargetext)|Definiert die längste Zeichenfolge, die im Bereich ungekürzt angezeigt werden.|  
|[CMFCRibbonStatusBarPane::SetAnimationList](#setanimationlist)|Weist dem Bereich eine Bildliste, die für eine Animation verwendet werden kann.|  
|[CMFCRibbonStatusBarPane::SetTextAlign](#settextalign)|Legt die Ausrichtung des Texts fest.|  
|[CMFCRibbonStatusBarPane::StartAnimation](#startanimation)|Startet die Animation, die dem Bereich zugeordnet ist.|  
|[CMFCRibbonStatusBarPane::StopAnimation](#stopanimation)|Beendet die Animation, die dem Bereich zugeordnet ist. .|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::OnFinishAnimation](#onfinishanimation)|Wird vom Framework aufgerufen, wenn beendet die Animation, die dem Bereich zugeordnet ist.|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Verwendung der unterschiedlichen Methoden in der `CMFCRibbonStatusBarPane`-Klasse veranschaulicht. Das Beispiel zeigt, wie ein `CMFCRibbonStatusBarPane` Objekt, legen Sie die Ausrichtung des Texts der Bezeichnung des Statusbereich Balken, den längsten Text, der in der Status-Leistenbereich ungekürzt angezeigt werden können, ordnen Sie in den Bereich der Status angezeigt, die für die Animation verwendet werden kann, und starten die Animation definieren.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#2;](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbarpane-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribbonstatusbarpane.h  
  
##  <a name="a-namecmfcribbonstatusbarpanea--cmfcribbonstatusbarpanecmfcribbonstatusbarpane"></a><a name="cmfcribbonstatusbarpane"></a>CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane  
 Erstellen Sie ein Objekt im Bereich in der Statusleiste angezeigt.  
  
```  
CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    BOOL bIsStatic=FALSE,  
    HICON hIcon=NULL,  
    LPCTSTR lpszAlmostLargeText=NULL);

CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    HBITMAP hBmpAnimationList,  
    int cxAnimation=16,  
    COLORREF clrTrnsp=RGB(192,192 1,192) 1,  
    HICON hIcon=NULL,  
    BOOL bIsStatic=FALSE);

CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    UINT uiAnimationListResID,  
    int cxAnimation=16,  
    COLORREF clrTrnsp=RGB(192, 192 1, 192) 1,  
    HICON hIcon=NULL,  
    BOOL bIsStatic=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nCmdID`  
 Gibt die Befehls-ID des Bereichs.  
  
 [in] `lpszText`  
 Gibt die Textzeichenfolge, die im Bereich angezeigt werden.  
  
 [in] `bIsStatic`  
 Wenn `TRUE`, im Statusbereich nicht markiert oder durch Anklicken ausgewählt.  
  
 [in] `hIcon`  
 Gibt ein Handle für ein Symbol im Bereich angezeigt werden.  
  
 [in] `lpszAlmostLargeText`  
 Gibt die längste Zeichenfolge, die im Bereich angezeigt werden können.  
  
 [in] `hBmpAnimationList`  
 Gibt ein Handle für eine Bildliste, die für eine Animation verwendet wird.  
  
 [in] `cxAnimation`  
 Gibt die Breite in Pixel des Symbols in der Bildliste, die für eine Animation verwendet wird.  
  
 [in] `clrTrnsp`  
 Gibt die transparente Farbe des Images in der Bildliste, die für eine Animation verwendet werden.  
  
 [in] `uiAnimationListResID`  
 Gibt die Ressourcen-ID einer Bildliste, die für eine Animation verwendet wird.  
  
##  <a name="a-namegetalmostlargetexta--cmfcribbonstatusbarpanegetalmostlargetext"></a><a name="getalmostlargetext"></a>CMFCRibbonStatusBarPane::GetAlmostLargeText  
 Ruft die längste Zeichenfolge, die im Bereich der Status Leiste anzeigen können.  
  
```  
LPCTSTR GetAlmostLargeText() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die längste Zeichenfolge, die im Bereich der Status Leiste anzeigen können.  
  
##  <a name="a-namegettextaligna--cmfcribbonstatusbarpanegettextalign"></a><a name="gettextalign"></a>CMFCRibbonStatusBarPane::GetTextAlign  
 Ruft die aktuelle Einstellung der Ausrichtung des Texts der Bezeichnung des im Bereich der Status angezeigt.  
  
```  
int GetTextAlign() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Aktuelle Ausrichtung des Texts, die eines der folgenden sein kann:  
  
-   TA_LEFT  
  
-   TA_CENTER  
  
-   TA_RIGHT.  
  
##  <a name="a-nameisanimationa--cmfcribbonstatusbarpaneisanimation"></a><a name="isanimation"></a>CMFCRibbonStatusBarPane::IsAnimation  
 Bestimmt, ob die Animation ausgeführt wird.  
  
```  
BOOL IsAnimation() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Animation ausgeführt wird; `FALSE` andernfalls.  
  
##  <a name="a-nameisextendeda--cmfcribbonstatusbarpaneisextended"></a><a name="isextended"></a>CMFCRibbonStatusBarPane::IsExtended  
 Bestimmen Sie, ob der Bereich im erweiterten Bereich des Status-Menübands befindet.  
  
```  
BOOL IsExtended() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich auf der Statusleiste der erweiterte Bereich befindet. Andernfalls `FALSE`.  
  
##  <a name="a-nameondrawbordera--cmfcribbonstatusbarpaneondrawborder"></a><a name="ondrawborder"></a>CMFCRibbonStatusBarPane::OnDrawBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawBorder(CDC*);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `CDC*`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonfillbackgrounda--cmfcribbonstatusbarpaneonfillbackground"></a><a name="onfillbackground"></a>CMFCRibbonStatusBarPane::OnFillBackground  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnFillBackground(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonfinishanimationa--cmfcribbonstatusbarpaneonfinishanimation"></a><a name="onfinishanimation"></a>CMFCRibbonStatusBarPane::OnFinishAnimation  
 Framework ruft diese Methode am Ende die Animation, die dem Bereich zugeordnet ist.  
  
```  
virtual void OnFinishAnimation();
```  
  
### <a name="remarks"></a>Hinweise  
 `StopAnimation`Methodenaufrufe der `OnFinishAnimation` -Methode, die Sie verwenden können, Daten bereinigen, wenn die Animation endet.  
  
##  <a name="a-namesetalmostlargetexta--cmfcribbonstatusbarpanesetalmostlargetext"></a><a name="setalmostlargetext"></a>CMFCRibbonStatusBarPane::SetAlmostLargeText  
 Definieren Sie den längsten Text, der in der Status-Leistenbereich ungekürzt angezeigt werden kann.  
  
```  
void SetAlmostLargeText(LPCTSTR lpszAlmostLargeText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszAlmostLargeText`  
 Gibt die Länge der Zeichenfolge, die in der Status-Leistenbereich ungekürzt angezeigt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Die Bibliothek berechnet die Größe des Texts, `lpszAlmostLargeText` gibt und Bereich entsprechend ändert. Der Text wird abgeschnitten, wenn es noch nicht in den Bereich passt.  
  
##  <a name="a-namesetanimationlista--cmfcribbonstatusbarpanesetanimationlist"></a><a name="setanimationlist"></a>CMFCRibbonStatusBarPane::SetAnimationList  
 Fügt an der Status-Leistenbereich eine Bildliste, die für eine Animation verwendet werden kann.  
  
```  
void SetAnimationList(
    HBITMAP hBmpAnimationList,  
    int cxAnimation=16,  
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);

BOOL SetAnimationList(
    UINT uiAnimationListResID,  
    int cxAnimation=16,  
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hBmpAnimationList`  
 Gibt ein Handle für eine Bildliste.  
  
 [in] `cxAnimation`  
 Gibt die Breite des Frames, in der Bildliste in Pixel an.  
  
 [in] `clrTransp`  
 Gibt die transparente Farbe der Bildliste.  
  
 [in] `uiAnimationListResID`  
 Gibt die Ressourcen-ID der Bildliste.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Status-Leistenbereich erfolgreich die Bildliste zugeordnet ist; `FALSE` andernfalls.  
  
##  <a name="a-namesettextaligna--cmfcribbonstatusbarpanesettextalign"></a><a name="settextalign"></a>CMFCRibbonStatusBarPane::SetTextAlign  
 Legt die Ausrichtung des Texts der Bezeichnung des im Bereich der Status angezeigt.  
  
```  
void SetTextAlign(int nAlign);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nAlign`  
 Gibt die Ausrichtung des Texts an.  
  
### <a name="remarks"></a>Hinweise  
 `nAlign`Dabei kann es sich um einen der folgenden Werte aufweisen:  
  
- `TA_LEFT`: Ausrichtung links  
  
- `TA_CENTER:`zentrierte Ausrichtung  
  
- `TA_RIGHT:`Rechtsbündig  
  
##  <a name="a-namestartanimationa--cmfcribbonstatusbarpanestartanimation"></a><a name="startanimation"></a>CMFCRibbonStatusBarPane::StartAnimation  
 Startet die Animation, die Sie in den Bereich zuweisen.  
  
```  
void StartAnimation(
    UINT nFrameDelay=500,  
    UINT nDuration=-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nFrameDelay`  
 Gibt die Framerate Animation in Millisekunden.  
  
 [in] `nDuration`  
 Gibt an, wie lange die Animation in Millisekunden zu spielen. Verwenden Sie-1. für eine Endlosschleife.  
  
### <a name="remarks"></a>Hinweise  
 Geben Sie ein Handle für eine Bildliste vor dem Aufruf von `StartAnimation` mit `SetAnimationList`.  
  
##  <a name="a-namestopanimationa--cmfcribbonstatusbarpanestopanimation"></a><a name="stopanimation"></a>CMFCRibbonStatusBarPane::StopAnimation  
 Beendet die Animation, die Sie im Bereich der Leiste Status zugewiesen.  
  
```  
void StopAnimation();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton-Klasse](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonStatusBar-Klasse](../../mfc/reference/cmfcribbonstatusbar-class.md)

