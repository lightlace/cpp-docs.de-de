---
title: CMFCRibbonStatusBarPane-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 55ef22eec84b4d7e5e4ea27abe611cf2d18f2a1b
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42545817"
---
# <a name="cmfcribbonstatusbarpane-class"></a>CMFCRibbonStatusBarPane-Klasse
Die `CMFCRibbonStatusBarPane` -Klasse implementiert ein Menübandelement, das eine Menüband-Statusleiste hinzugefügt werden können.  
  
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
|[CMFCRibbonStatusBarPane::SetAlmostLargeText](#setalmostlargetext)|Definiert die längste Zeichenfolge, die im Bereich ungekürzt angezeigt werden kann.|  
|[CMFCRibbonStatusBarPane::SetAnimationList](#setanimationlist)|Weist dem Bereich eine Bildliste an, die für die Animation verwendet werden kann.|  
|[CMFCRibbonStatusBarPane::SetTextAlign](#settextalign)|Legt die Ausrichtung des Texts fest.|  
|[CMFCRibbonStatusBarPane::StartAnimation](#startanimation)|Startet die Animation, die im Bereich zugewiesen ist.|  
|[CMFCRibbonStatusBarPane::StopAnimation](#stopanimation)|Beendet die Animation, die in den Bereich zugewiesen ist. sein.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::OnFinishAnimation](#onfinishanimation)|Vom Framework aufgerufen, wenn die Animation, die in den Bereich zugewiesen wird beendet.|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Verwendung der unterschiedlichen Methoden in der `CMFCRibbonStatusBarPane`-Klasse veranschaulicht. Das Beispiel zeigt, wie zum Erstellen einer `CMFCRibbonStatusBarPane` Objekt, das die Ausrichtung des Texts der Bezeichnung für den Statusleistenbereich festlegen, definieren den längsten Text, der im den Statusleistenbereich ungekürzt angezeigt werden kann, fügen Sie an den Statusleistenbereich eine Bildliste an, die für verwendet werden kann ein Nimation, und starten Sie die Animation.  
  
 [!code-cpp[NVC_MFC_RibbonApp#2](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbarpane-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribbonstatusbarpane.h  
  
##  <a name="cmfcribbonstatusbarpane"></a>  CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane  
 Erstellen Sie ein Objekt im Bereich, in der Statusleiste an.  
  
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
 [in] *nCmdID*  
 Gibt die Befehls-ID des Bereichs an.  
  
 [in] *LpszText*  
 Gibt an, Textzeichenfolge, die im Bereich angezeigt werden.  
  
 [in] *bIsStatic*  
 Wenn "true" kann nicht im Statusbereich hervorgehoben oder ausgewählt werden, indem Sie darauf klicken.  
  
 [in] *hIcon*  
 Gibt ein Handle für ein Symbol im Bereich angezeigt werden.  
  
 [in] *LpszAlmostLargeText*  
 Gibt an, die längste Zeichenfolge, die von dem Bereich angezeigt werden kann.  
  
 [in] *hBmpAnimationList*  
 Gibt ein Handle einer Bildliste an, die für die Animation verwendet wird.  
  
 [in] *CxAnimation*  
 Gibt die Breite in Pixel des Symbols in der Bildliste an, die für die Animation verwendet wird.  
  
 [in] *ClrTrnsp*  
 Gibt die transparente Farbe des Images in der Bildliste an, die für die Animation verwendet werden.  
  
 [in] *UiAnimationListResID*  
 Gibt eine Ressourcen-ID, der eine Liste der Bilder, die für die Animation verwendet wird.  
  
##  <a name="getalmostlargetext"></a>  CMFCRibbonStatusBarPane::GetAlmostLargeText  
 Ruft die längste Zeichenfolge, die den Statusleistenbereich anzeigen können.  
  
```  
LPCTSTR GetAlmostLargeText() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die längste Zeichenfolge, die den Statusleistenbereich anzeigen können.  
  
##  <a name="gettextalign"></a>  CMFCRibbonStatusBarPane::GetTextAlign  
 Ruft die aktuelle Einstellung der Ausrichtung des Texts der Bezeichnung für den Statusleistenbereich ab.  
  
```  
int GetTextAlign() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Aktuelle Ausrichtung des Texts, die in der folgenden Werte sind möglich:  
  
-   TA_LEFT  
  
-   TA_CENTER  
  
-   TA_RIGHT.  
  
##  <a name="isanimation"></a>  CMFCRibbonStatusBarPane::IsAnimation  
 Bestimmt, ob die Animation ausgeführt wird.  
  
```  
BOOL IsAnimation() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Animation ausgeführt wird. "False" andernfalls.  
  
##  <a name="isextended"></a>  CMFCRibbonStatusBarPane::IsExtended  
 Bestimmen Sie, ob der Bereich im erweiterten Bereich des Status-Menübands befindet.  
  
```  
BOOL IsExtended() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn der Bereich auf der Statusleiste erweiterten Bereich befindet. "False" andernfalls.  
  
##  <a name="ondrawborder"></a>  CMFCRibbonStatusBarPane::OnDrawBorder  
 Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.  
  
```  
virtual void OnDrawBorder(CDC*);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *CDC**  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onfillbackground"></a>  CMFCRibbonStatusBarPane::OnFillBackground  
 Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.  
  
```  
virtual COLORREF OnFillBackground(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onfinishanimation"></a>  CMFCRibbonStatusBarPane::OnFinishAnimation  
 Framework ruft diese Methode auf, wenn die Animation, die in den Bereich zugewiesen wird beendet.  
  
```  
virtual void OnFinishAnimation();
```  
  
### <a name="remarks"></a>Hinweise  
 `StopAnimation` Methodenaufrufe der `OnFinishAnimation` -Methode, die Sie, zum Bereinigen von Daten verwenden können, wenn die Animation endet.  
  
##  <a name="setalmostlargetext"></a>  CMFCRibbonStatusBarPane::SetAlmostLargeText  
 Definieren des längsten Texts, der in den Statusleistenbereich ungekürzt angezeigt werden kann.  
  
```  
void SetAlmostLargeText(LPCTSTR lpszAlmostLargeText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *LpszAlmostLargeText*  
 Gibt die Länge der Zeichenfolge, die für den Statusleistenbereich ungekürzt angezeigt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Die Bibliothek berechnet die Größe des Texts, *LpszAlmostLargeText* gibt an, und den Bereich entsprechend ändert. Der Text wird abgeschnitten, wenn er noch nicht im Bereich passt.  
  
##  <a name="setanimationlist"></a>  CMFCRibbonStatusBarPane::SetAnimationList  
 Fügt an den Statusleistenbereich an eine Bildliste an, die für die Animation verwendet werden kann.  
  
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
 [in] *hBmpAnimationList*  
 Gibt ein Handle einer Bildliste.  
  
 [in] *CxAnimation*  
 Gibt die Breite in Pixel des Rahmens in der Bildliste an.  
  
 [in] *ClrTransp*  
 Gibt die transparente Farbe in der Liste der Bilder an.  
  
 [in] *UiAnimationListResID*  
 Gibt die Ressourcen-ID der Liste der Bilder an.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Bildliste erfolgreich dem Statusleistenbereich zugeordnet ist. "False" andernfalls.  
  
##  <a name="settextalign"></a>  CMFCRibbonStatusBarPane::SetTextAlign  
 Legt die Ausrichtung des Texts der Bezeichnung für den Statusleistenbereich fest.  
  
```  
void SetTextAlign(int nAlign);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nAlign*  
 Gibt die Ausrichtung des Texts an.  
  
### <a name="remarks"></a>Hinweise  
 *nAlign* kann einen der folgenden Werte aufweisen:  
  
- TA_LEFT: linksbündige Ausrichtung  
  
- TA_CENTER: Ausrichtung zentriert  
  
- TA_RIGHT: rechtsbündige Ausrichtung  
  
##  <a name="startanimation"></a>  CMFCRibbonStatusBarPane::StartAnimation  
 Startet die Animation, die Sie in den Bereich zuweisen.  
  
```  
void StartAnimation(
    UINT nFrameDelay=500,  
    UINT nDuration=-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nFrameDelay*  
 Gibt die Animation Framerate, in Millisekunden an.  
  
 [in] *nDuration*  
 Gibt an, wie lange zur Wiedergabe der Animation, in Millisekunden. Verwenden Sie-1 für eine Endlosschleife.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen ein Handle einer Bildliste angeben, vor dem Aufruf `StartAnimation` mit `SetAnimationList`.  
  
##  <a name="stopanimation"></a>  CMFCRibbonStatusBarPane::StopAnimation  
 Beendet die Animation, die Sie dem Statusleistenbereich zugeordnet.  
  
```  
void StopAnimation();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton-Klasse](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonStatusBar-Klasse](../../mfc/reference/cmfcribbonstatusbar-class.md)
