---
title: CMFCRibbonStatusBarPane Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsExtended
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnDrawBorder
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFillBackground
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAnimationList
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StartAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StopAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFinishAnimation
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonStatusBarPane [MFC], CMFCRibbonStatusBarPane
- CMFCRibbonStatusBarPane [MFC], GetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], GetTextAlign
- CMFCRibbonStatusBarPane [MFC], IsAnimation
- CMFCRibbonStatusBarPane [MFC], IsExtended
- CMFCRibbonStatusBarPane [MFC], OnDrawBorder
- CMFCRibbonStatusBarPane [MFC], OnFillBackground
- CMFCRibbonStatusBarPane [MFC], SetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], SetAnimationList
- CMFCRibbonStatusBarPane [MFC], SetTextAlign
- CMFCRibbonStatusBarPane [MFC], StartAnimation
- CMFCRibbonStatusBarPane [MFC], StopAnimation
- CMFCRibbonStatusBarPane [MFC], OnFinishAnimation
ms.assetid: 5d034c3c-ecca-4267-b88c-0f55a2884dd0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e3d5059adf0ebbd1ed651d57354ae73beadb919f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcribbonstatusbarpane-class"></a>CMFCRibbonStatusBarPane-Klasse
Die `CMFCRibbonStatusBarPane` Klasse implementiert ein Menübandelement, das einer Menüband-Statusleiste hinzugefügt werden können.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonStatusBarPane : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane](#cmfcribbonstatusbarpane)|Erstellt und initialisiert ein `CMFCRibbonStatusBarPane`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::GetAlmostLargeText](#getalmostlargetext)|Gibt die Zeichenfolge, die die längste Zeichenfolge definiert, die im Bereich ungekürzt angezeigt werden können.|  
|[CMFCRibbonStatusBarPane::GetTextAlign](#gettextalign)|Gibt die aktuelle Einstellung der Ausrichtung des Texts zurück.|  
|[CMFCRibbonStatusBarPane::IsAnimation](#isanimation)|Bestimmt, ob die Animation ausgeführt wird.|  
|[CMFCRibbonStatusBarPane::IsExtended](#isextended)|Bestimmt, ob der Bereich im erweiterten Bereich des Status-Menübands befindet.|  
|[CMFCRibbonStatusBarPane::OnDrawBorder](#ondrawborder)|(Überschreibt [CMFCRibbonButton::OnDrawBorder](../../mfc/reference/cmfcribbonbutton-class.md#ondrawborder).)|  
|[CMFCRibbonStatusBarPane::OnFillBackground](#onfillbackground)|(Überschreibt [CMFCRibbonButton::OnFillBackground](../../mfc/reference/cmfcribbonbutton-class.md#onfillbackground).)|  
|[CMFCRibbonStatusBarPane::SetAlmostLargeText](#setalmostlargetext)|Definiert die längste Zeichenfolge, die im Bereich ungekürzt angezeigt werden können.|  
|[CMFCRibbonStatusBarPane::SetAnimationList](#setanimationlist)|Weist dem Bereich eine Bildliste, die für die Animation verwendet werden kann.|  
|[CMFCRibbonStatusBarPane::SetTextAlign](#settextalign)|Legt die Ausrichtung des Texts an.|  
|[CMFCRibbonStatusBarPane::StartAnimation](#startanimation)|Startet die Animation, die in den Bereich zugewiesen wird.|  
|[CMFCRibbonStatusBarPane::StopAnimation](#stopanimation)|Beendet die Animation, die in den Bereich zugewiesen wird. sein.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::OnFinishAnimation](#onfinishanimation)|Vom Framework aufgerufen, wenn die Animation, die in den Bereich zugewiesen wird beendet.|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Verwendung der unterschiedlichen Methoden in der `CMFCRibbonStatusBarPane`-Klasse veranschaulicht. Im Beispiel wird gezeigt, wie zum Erstellen einer `CMFCRibbonStatusBarPane` Objekt, das die Ausrichtung des Texts der Bezeichnung des Status-Leistenbereich festlegen, definieren den längsten Text, der im Statusbereich Leiste ungekürzt angezeigt werden können, zum Anschließen Statusbereich Leiste einer Bildliste für die verwendeten ein Nimation, und starten Sie die Animation.  
  
 [!code-cpp[NVC_MFC_RibbonApp#2](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbarpane-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribbonstatusbarpane.h  
  
##  <a name="cmfcribbonstatusbarpane"></a>CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane  
 Erstellen Sie ein Objekt in der Statusleiste an.  
  
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
 Gibt die Befehls-ID des Bereichs an.  
  
 [in] `lpszText`  
 Gibt die Textzeichenfolge, die im Bereich angezeigt werden.  
  
 [in] `bIsStatic`  
 Wenn `TRUE`, Statusbereich nicht hervorgehoben oder markiert, indem Sie darauf klicken.  
  
 [in] `hIcon`  
 Gibt ein Handle für ein Symbol, um im Bereich angezeigt werden.  
  
 [in] `lpszAlmostLargeText`  
 Gibt die längste Zeichenfolge, die im Bereich angezeigt werden können.  
  
 [in] `hBmpAnimationList`  
 Gibt ein Handle für eine Bildliste, die für die Animation verwendet wird.  
  
 [in] `cxAnimation`  
 Gibt die Breite in Pixel des Symbols in der Bildliste, die für die Animation verwendet wird.  
  
 [in] `clrTrnsp`  
 Gibt die transparente Farbe des Bilder in der Bildliste, die für die Animation verwendet werden.  
  
 [in] `uiAnimationListResID`  
 Gibt eine Ressourcen-ID von einer Bildliste, die für die Animation verwendet wird.  
  
##  <a name="getalmostlargetext"></a>CMFCRibbonStatusBarPane::GetAlmostLargeText  
 Ruft die längste Textzeichenfolge, die die Status-Leistenbereich anzeigen können.  
  
```  
LPCTSTR GetAlmostLargeText() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die längste Textzeichenfolge, die die Status-Leistenbereich anzeigen können.  
  
##  <a name="gettextalign"></a>CMFCRibbonStatusBarPane::GetTextAlign  
 Ruft die aktuelle Einstellung der Ausrichtung des Texts, der die Bezeichnung des Status-Leistenbereich ab.  
  
```  
int GetTextAlign() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Aktuelle Ausrichtung des Texts, die in der folgenden Werte sind möglich:  
  
-   TA_LEFT  
  
-   TA_CENTER  
  
-   TA_RIGHT.  
  
##  <a name="isanimation"></a>CMFCRibbonStatusBarPane::IsAnimation  
 Bestimmt, ob die Animation ausgeführt wird.  
  
```  
BOOL IsAnimation() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Animation ausgeführt wird; `FALSE` andernfalls.  
  
##  <a name="isextended"></a>CMFCRibbonStatusBarPane::IsExtended  
 Bestimmen Sie, ob der Bereich im erweiterten Bereich des Status-Menübands befindet.  
  
```  
BOOL IsExtended() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich auf der Statusleiste der erweiterte Bereich befindet. Andernfalls `FALSE`.  
  
##  <a name="ondrawborder"></a>CMFCRibbonStatusBarPane::OnDrawBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawBorder(CDC*);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `CDC*`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onfillbackground"></a>CMFCRibbonStatusBarPane::OnFillBackground  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnFillBackground(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onfinishanimation"></a>CMFCRibbonStatusBarPane::OnFinishAnimation  
 Framework ruft diese Methode auf, wenn die Animation, die in den Bereich zugewiesen wird beendet.  
  
```  
virtual void OnFinishAnimation();
```  
  
### <a name="remarks"></a>Hinweise  
 `StopAnimation`Ruft die `OnFinishAnimation` -Methode, die Sie, zum Bereinigen von Daten verwenden können, wenn die Animation beendet.  
  
##  <a name="setalmostlargetext"></a>CMFCRibbonStatusBarPane::SetAlmostLargeText  
 Definieren Sie die längsten Text, der im Statusbereich Leiste ungekürzt angezeigt werden kann.  
  
```  
void SetAlmostLargeText(LPCTSTR lpszAlmostLargeText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszAlmostLargeText`  
 Gibt die längste Zeichenfolge, die auf den Status-Leistenbereich ungekürzt angezeigt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Die Bibliothek berechnet die Größe des Texts, `lpszAlmostLargeText` gibt an, und der Bereich entsprechend ändert. Der Text wird abgeschnitten, wenn er noch nicht im Bereich passt.  
  
##  <a name="setanimationlist"></a>CMFCRibbonStatusBarPane::SetAnimationList  
 Fügt an die Status-Leistenbereich eine Bildliste, die für die Animation verwendet werden kann.  
  
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
 Gibt ein Handle für eine Bildliste an.  
  
 [in] `cxAnimation`  
 Gibt die Breite des Frames, in der Bildliste in Pixel an.  
  
 [in] `clrTransp`  
 Gibt die transparente Farbe des der Bildliste an.  
  
 [in] `uiAnimationListResID`  
 Gibt die Ressourcen-ID der Bildliste an.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Bildliste erfolgreich an den Status-Leistenbereich angefügt wird; `FALSE` andernfalls.  
  
##  <a name="settextalign"></a>CMFCRibbonStatusBarPane::SetTextAlign  
 Legt die Ausrichtung des Texts der Bezeichnung des Status-Leistenbereich fest.  
  
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
  
- `TA_RIGHT:`rechtsbündige Ausrichtung  
  
##  <a name="startanimation"></a>CMFCRibbonStatusBarPane::StartAnimation  
 Startet die Animation, die Sie in den Bereich zuweisen.  
  
```  
void StartAnimation(
    UINT nFrameDelay=500,  
    UINT nDuration=-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nFrameDelay`  
 Gibt die Framerate Animation in Millisekunden an.  
  
 [in] `nDuration`  
 Gibt an, wie lange die Animation im Millisekunden wiedergegeben. Verwenden Sie-1. für eine Endlosschleife.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen ein Handle für eine Bildliste angeben, vor dem Aufruf `StartAnimation` mit `SetAnimationList`.  
  
##  <a name="stopanimation"></a>CMFCRibbonStatusBarPane::StopAnimation  
 Beendet die Animation, die die Status-Leistenbereich zugewiesen.  
  
```  
void StopAnimation();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton-Klasse](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonStatusBar-Klasse](../../mfc/reference/cmfcribbonstatusbar-class.md)
