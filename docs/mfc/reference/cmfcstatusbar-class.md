---
title: CMFCStatusBar-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar::CalcFixedLayout
- AFXSTATUSBAR/CMFCStatusBar::CommandToIndex
- AFXSTATUSBAR/CMFCStatusBar::Create
- AFXSTATUSBAR/CMFCStatusBar::CreateEx
- AFXSTATUSBAR/CMFCStatusBar::DoesAllowDynInsertBefore
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneDoubleClick
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneProgressBar
- AFXSTATUSBAR/CMFCStatusBar::GetCount
- AFXSTATUSBAR/CMFCStatusBar::GetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetItemID
- AFXSTATUSBAR/CMFCStatusBar::GetItemRect
- AFXSTATUSBAR/CMFCStatusBar::GetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::GetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::GetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::GetPaneText
- AFXSTATUSBAR/CMFCStatusBar::GetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::GetTipText
- AFXSTATUSBAR/CMFCStatusBar::InvalidatePaneContent
- AFXSTATUSBAR/CMFCStatusBar::PreCreateWindow
- AFXSTATUSBAR/CMFCStatusBar::SetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::SetIndicators
- AFXSTATUSBAR/CMFCStatusBar::SetPaneAnimation
- AFXSTATUSBAR/CMFCStatusBar::SetPaneBackgroundColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneIcon
- AFXSTATUSBAR/CMFCStatusBar::SetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::SetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::SetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::SetPaneText
- AFXSTATUSBAR/CMFCStatusBar::SetPaneTextColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::SetTipText
- AFXSTATUSBAR/CMFCStatusBar::OnDrawPane
dev_langs:
- C++
helpviewer_keywords:
- CMFCStatusBar [MFC], CalcFixedLayout
- CMFCStatusBar [MFC], CommandToIndex
- CMFCStatusBar [MFC], Create
- CMFCStatusBar [MFC], CreateEx
- CMFCStatusBar [MFC], DoesAllowDynInsertBefore
- CMFCStatusBar [MFC], EnablePaneDoubleClick
- CMFCStatusBar [MFC], EnablePaneProgressBar
- CMFCStatusBar [MFC], GetCount
- CMFCStatusBar [MFC], GetDrawExtendedArea
- CMFCStatusBar [MFC], GetExtendedArea
- CMFCStatusBar [MFC], GetItemID
- CMFCStatusBar [MFC], GetItemRect
- CMFCStatusBar [MFC], GetPaneInfo
- CMFCStatusBar [MFC], GetPaneProgress
- CMFCStatusBar [MFC], GetPaneStyle
- CMFCStatusBar [MFC], GetPaneText
- CMFCStatusBar [MFC], GetPaneWidth
- CMFCStatusBar [MFC], GetTipText
- CMFCStatusBar [MFC], InvalidatePaneContent
- CMFCStatusBar [MFC], PreCreateWindow
- CMFCStatusBar [MFC], SetDrawExtendedArea
- CMFCStatusBar [MFC], SetIndicators
- CMFCStatusBar [MFC], SetPaneAnimation
- CMFCStatusBar [MFC], SetPaneBackgroundColor
- CMFCStatusBar [MFC], SetPaneIcon
- CMFCStatusBar [MFC], SetPaneInfo
- CMFCStatusBar [MFC], SetPaneProgress
- CMFCStatusBar [MFC], SetPaneStyle
- CMFCStatusBar [MFC], SetPaneText
- CMFCStatusBar [MFC], SetPaneTextColor
- CMFCStatusBar [MFC], SetPaneWidth
- CMFCStatusBar [MFC], SetTipText
- CMFCStatusBar [MFC], OnDrawPane
ms.assetid: f2960d1d-f4ed-41e8-bd99-0382b2f8d88e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c82a73c95c0869f7f5245ef3ddc15c0216b07579
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041725"
---
# <a name="cmfcstatusbar-class"></a>CMFCStatusBar-Klasse
Die `CMFCStatusBar` Klasse implementiert eine Statusleiste ähnelt der `CStatusBar` Klasse. Die `CMFCStatusBar` -Klasse verfügt jedoch über Funktionen, die von der `CStatusBar` -Klasse nicht bereitgestellt werden. Beispielsweise kann die Klasse Bilder, Animationen und Statusanzeigen anzeigen und auf einen Mausdoppelklick reagieren. 

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]   
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCStatusBar : public CPane  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCStatusBar::CalcFixedLayout](#calcfixedlayout)|(Überschreibt [cbasepane:: Calcfixedlayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|  
|[CMFCStatusBar::CommandToIndex](#commandtoindex)||  
|[CMFCStatusBar::Create](#create)|Erstellt eine Steuerleiste und fügt es der [CPane](../../mfc/reference/cpane-class.md) Objekt. (Überschreibt [cpane:: Create](../../mfc/reference/cpane-class.md#create).)|  
|[CMFCStatusBar::CreateEx](#createex)|Erstellt eine Steuerleiste und fügt es der [CPane](../../mfc/reference/cpane-class.md) Objekt. (Überschreibt [cpane:: CreateEx](../../mfc/reference/cpane-class.md#createex).)|  
|[CMFCStatusBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Bestimmt, ob ein weiterer Bereich dynamisch zwischen diesem Bereich und den übergeordneten Frame eingefügt werden kann. (Überschreibt [cbasepane:: Doesallowdyninsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|  
|[CMFCStatusBar::EnablePaneDoubleClick](#enablepanedoubleclick)|Die Behandlung von Maus werden auf der Statusleiste doppelklickt, aktiviert oder deaktiviert.|  
|[CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar)|Zeigt eine Statusanzeige im angegebenen Bereich.|  
|[CMFCStatusBar::GetCount](#getcount)|Gibt die Anzahl der Bereiche auf der Statusleiste an.|  
|[CMFCStatusBar::GetDrawExtendedArea](#getdrawextendedarea)||  
|[CMFCStatusBar::GetExtendedArea](#getextendedarea)||  
|[CMFCStatusBar::GetItemID](#getitemid)||  
|[CMFCStatusBar::GetItemRect](#getitemrect)||  
|[CMFCStatusBar::GetPaneInfo](#getpaneinfo)||  
|[CMFCStatusBar::GetPaneProgress](#getpaneprogress)||  
|[CMFCStatusBar::GetPaneStyle](#getpanestyle)|Gibt den Schriftschnitt Bereich. (Überschreibt [CBasePane::GetPaneStyle](../../mfc/reference/cbasepane-class.md#getpanestyle).)|  
|[CMFCStatusBar::GetPaneText](#getpanetext)||  
|[CMFCStatusBar::GetPaneWidth](#getpanewidth)|Gibt die Breite in Pixel der Statusleiste im angegebenen Bereich zurück.|  
|[CMFCStatusBar::GetTipText](#gettiptext)|Gibt den QuickInfo-Text für den angegebenen Bereich der Statusleiste an.|  
|[CMFCStatusBar::InvalidatePaneContent](#invalidatepanecontent)|Erklärt den angegebenen Bereich, und zeichnet ihre Inhalte neu.|  
|[CMFCStatusBar::PreCreateWindow](#precreatewindow)|Wird aufgerufen, durch das Framework vor der Erstellung des Windows-Fenster, die an diese angefügt `CWnd` Objekt. (Überschreibt [CWnd::PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).)|  
|[CMFCStatusBar::SetDrawExtendedArea](#setdrawextendedarea)||  
|[CMFCStatusBar::SetIndicators](#setindicators)||  
|[CMFCStatusBar::SetPaneAnimation](#setpaneanimation)|Weist eine Animation in den angegebenen Bereich.|  
|[CMFCStatusBar::SetPaneBackgroundColor](#setpanebackgroundcolor)|Legt die Hintergrundfarbe für den angegebenen Bereich der Statusleiste an.|  
|[CMFCStatusBar::SetPaneIcon](#setpaneicon)|Legt das Indikatorsymbol für den angegebenen Bereich der Statusleiste an.|  
|[CMFCStatusBar::SetPaneInfo](#setpaneinfo)||  
|[CMFCStatusBar::SetPaneProgress](#setpaneprogress)|Legt den aktuellen Status der Statusanzeige für den angegebenen Bereich der Statusleiste an.|  
|[CMFCStatusBar::SetPaneStyle](#setpanestyle)|Legt das Format des Bereichs. (Überschreibt [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle).)|  
|[CMFCStatusBar::SetPaneText](#setpanetext)||  
|[CMFCStatusBar::SetPaneTextColor](#setpanetextcolor)|Legt die Textfarbe für den angegebenen Bereich der Statusleiste an.|  
|[CMFCStatusBar::SetPaneWidth](#setpanewidth)|Legt die Breite in Pixel der Statusleiste im angegebenen Bereich fest.|  
|[CMFCStatusBar::SetTipText](#settiptext)|Legt den QuickInfo-Text für den angegebenen Bereich der Statusleiste an.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCStatusBar::OnDrawPane](#ondrawpane)|Vom Framework aufgerufen, wenn sie den Bereich der Statusleiste zeichnet.|  
  
## <a name="remarks"></a>Hinweise  
 Das folgende Diagramm zeigt eine Abbildung der Statusleiste aus [Status Leiste Demobeispiel](../../visual-cpp-samples.md) Anwendung.  
  
 ![Beispiel für CMFCStatusBar](../../mfc/reference/media/cmfcstatusbar.png "Cmfcstatusbar")  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die lokalen Variablen, die die Anwendung in verschiedenen Methoden aufrufen, verwendet die `CMFCStatusBar` Klasse. Diese Variablen werden im StatusBarDemoView.h deklariert. Der Hauptframe in "MainFrm.h" deklariert ist, wird das Dokument in StatusBarDemoDoc.h deklariert und die Ansicht in StatusBarDemoView.h deklariert ist. Dieser Codeausschnitt ist Teil der [Status Leiste Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#9](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_1.h)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Abrufen eines Verweises auf `CMFCStatusBar` Objekt durch die Einführung der `GetStatusBar` Methode in "MainFrm.h" und dem anschließenden Aufrufen dieser Methode aus der `GetStatusBar` Methode in StatusBarDemoView.h. Dieser Codeausschnitt ist Teil der [Status Leiste Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#7](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_2.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#8](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_3.h)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden aufzurufen, der `CMFCStatusBar` Klasse in StatusBarDemoView.cpp. Die Konstanten sind in "MainFrm.h" deklariert. Im Beispiel wird gezeigt, wie auf das Symbol, legen Sie den QuickInfo-Text, der der Status-Leistenbereich, eine Statusleiste angezeigt, auf den angegebenen Bereich, weisen Sie eine Animation in den angegebenen Bereich, legen Sie den Text und die Breite der Balken Statusbereich, und Festlegen der aktuellen Statusanzeige die progr für die Status-Leistenbereich ESS-Leiste. Dieser Codeausschnitt ist Teil der [Status Leiste Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#6](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_4.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#1](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_5.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#2](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_6.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#3](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_7.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#4](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_8.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#5](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_9.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxstatusbar.h  
  
##  <a name="calcfixedlayout"></a>  CMFCStatusBar::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bStretch*  
 [in] *bHorz*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="commandtoindex"></a>  CMFCStatusBar::CommandToIndex  

  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nIDFind*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="create"></a>  CMFCStatusBar::Create  

  
```  
BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pParentWnd*  
 [in] *DwStyle*  
 [in] *nID*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="createex"></a>  CMFCStatusBar::CreateEx  

  
```  
BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = 0,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pParentWnd*  
 [in] *DwCtrlStyle*  
 [in] *DwStyle*  
 [in] *nID*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="doesallowdyninsertbefore"></a>  CMFCStatusBar::DoesAllowDynInsertBefore  

  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enablepanedoubleclick"></a>  CMFCStatusBar::EnablePaneDoubleClick  
 Die Behandlung von Maus werden auf der Statusleiste doppelklickt, aktiviert oder deaktiviert.  
  
```  
void EnablePaneDoubleClick(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bAktivieren*  
 Wenn `TRUE`, doppelklicken Sie die Verarbeitung der Maus auf, aktivieren. Andernfalls deaktivieren Sie die Verarbeitung von der Maus Doppelklick.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Statusleiste Doppelklicks verarbeiten aktiviert ist, sendet Windows die Benachrichtigung WM_COMMAND zusammen mit einer Ressourcen-ID an den Besitzer der Statusleiste an jedes Mal, die der Benutzer auf die Status-Leistenbereich doppelklickt.  
  
##  <a name="enablepaneprogressbar"></a>  CMFCStatusBar::EnablePaneProgressBar  
 Eine Statusleiste angezeigt, auf den angegebenen Bereich.  
  
```  
void EnablePaneProgressBar(
    int nIndex,  
    long nTotal=100,  
    BOOL bDisplayText=FALSE,  
    COLORREF clrBar=-1,  
    COLORREF clrBarDest=-1,  
    COLORREF clrProgressText=-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nIndex*  
 Gibt dem Index des Bereichs, dessen Statusanzeige zu aktivieren.  
  
 [in] *nGesamte*  
 Gibt den Maximalwert für die Statusanzeige an.  
  
 [in] *bDisplayText*  
 Gibt an, ob den aktuelle Wert für die Bearbeitung die Statusanzeige angezeigt werden soll.  
  
 [in] *ClrBar*  
 Gibt die Hintergrundfarbe der Statusleiste an.  
  
 [in] *ClrBarDest*  
 Gibt die Sekundärfarbe der Fortschritt Befehlsleisten-Hintergrund an. Verwenden Sie die anderen Wert als *ClrBar* Ausfüllen durch eine Farbe in einem Farbverlauf gemischt.  
  
 [in] *ClrProgressText*  
 Gibt die Farbe des Texts der Statusanzeige.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie den Fortschritt Leiste Aufruf deaktivieren möchten `EnablePaneProgressBar` mit *nGesamte* auf-1 festgelegt. Standardmäßig *nGesamte* auf 100 festgelegt ist. Aus diesem Grund benötigen Sie keine zusätzlichen Berechnungen zur Anzeige des Fortschritts als Prozentsatz.  
  
 Übergeben Sie unterschiedliche Werte für *ClrBar* und *ClrBarDest* so, dass die Hintergrundfarbe der Statusleiste eine Farbe in einem Farbverlauf gemischt anzeigt. sein.  
  
 Rufen Sie zum Festlegen des aktuellen Status der [CMFCStatusBar::SetPaneProgress](#setpaneprogress) Methode.  
  
##  <a name="getcount"></a>  CMFCStatusBar::GetCount  
 Ruft die Anzahl der Bereiche in der Statusleiste an.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bereiche in der Statusleiste.  
  
##  <a name="getdrawextendedarea"></a>  CMFCStatusBar::GetDrawExtendedArea  

  
```  
BOOL GetDrawExtendedArea() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getextendedarea"></a>  CMFCStatusBar::GetExtendedArea  

  
```  
virtual BOOL GetExtendedArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Rect*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getitemid"></a>  CMFCStatusBar::GetItemID  

  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nIndex*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getitemrect"></a>  CMFCStatusBar::GetItemRect  

  
```  
void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nIndex*  
 [in] *LpRect*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getpaneinfo"></a>  CMFCStatusBar::GetPaneInfo  

  
```  
void GetPaneInfo(
    int nIndex,  
    UINT& nID,  
    UINT& nStyle,  
    int& cxWidth) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nIndex*  
 [in] *nID*  
 [in] *nStyle*  
 [in] *CxWidth*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getpaneprogress"></a>  CMFCStatusBar::GetPaneProgress  

  
```  
long GetPaneProgress(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nIndex*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getpanestyle"></a>  CMFCStatusBar::GetPaneStyle  

  
```  
UINT GetPaneStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nIndex*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getpanetext"></a>  CMFCStatusBar::GetPaneText  

  
```  
void GetPaneText(
    int nIndex,  
    CString& s) const;  
  
CString GetPaneText(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nIndex*  
 [in] *s*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getpanewidth"></a>  CMFCStatusBar::GetPaneWidth  
 Ruft die Breite des Bereichs einer Statusleiste ab.  
  
```  
int GetPaneWidth(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nIndex*  
 Gibt den Index des Status-Leistenbereich an.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite der Balken Statusbereich, *nIndex* angibt; andernfalls, die 0 (null) ist eine Statusleiste ist nicht vorhanden.  
  
##  <a name="gettiptext"></a>  CMFCStatusBar::GetTipText  
 Abgerufen Sie den QuickInfo-Text des Bereichs "eine Statusleiste" werden.  
  
```  
CString GetTipText(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nIndex*  
 Gibt den Index des Bereichs für die QuickInfo-Text abzurufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der QuickInfo-Text der Statusleiste, *nIndex* angibt. Wenn eine Status-Leistenbereich für das angegebene nicht vorhanden ist, andernfalls auf die leere Zeichenfolge *nIndex* oder wenn die QuickInfo-Text leer ist.  
  
##  <a name="invalidatepanecontent"></a>  CMFCStatusBar::InvalidatePaneContent  
 Für ungültig zu erklären die Status-Leistenbereich und seinen Inhalt neu gezeichnet werden.  
  
```  
void InvalidatePaneContent(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nIndex*  
 Gibt den Index des Bereichs zurück, deren Inhalt neu gezeichnet und werden für ungültig erklärt wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Statusleiste ungültig ist, wird er zum Neuzeichnen gekennzeichnet. Windows zeichnet es neu bei der `UpdateWindow` Methode sendet eine WM_PAINT-Meldung an die `OnPaint` Methode.  
  
##  <a name="ondrawpane"></a>  CMFCStatusBar::OnDrawPane  
 Zeichnen Sie den Bereich der Statusleiste neu.  
  
```  
virtual void OnDrawPane(
    CDC* pDC,  
    CMFCStatusBarPaneInfo* pPane);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
 Ein Zeiger zu einem Gerätekontext für das Zeichnen.  
  
 [in] *pPane*  
 Ein Zeiger auf eine `CMFCStatusBarPaneInfo` -Struktur, die die Informationen zum zu zeichnenden Bereich enthält.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig `OnDrawPane` zeichnet den Bereich mit den Gerätekontext *pDC* gemäß der Formatvorlage und den Inhalt des Bereichs.  
  
 Überschreiben Sie diese Methode in einer `CMFCStatusBar`-abgeleitete Klasse, um die Darstellung eines Bereichs anzupassen.  
  
##  <a name="precreatewindow"></a>  CMFCStatusBar::PreCreateWindow  

  
```  
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Cs*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setdrawextendedarea"></a>  CMFCStatusBar::SetDrawExtendedArea  

  
```  
void SetDrawExtendedArea(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bSet*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setindicators"></a>  CMFCStatusBar::SetIndicators  

  
```  
BOOL SetIndicators(
    const UINT* lpIDArray,  
    int nIDCount);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *LpIDArray*  
 [in] *nIDCount*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpaneanimation"></a>  CMFCStatusBar::SetPaneAnimation  
 Weist eine Animation in den angegebenen Bereich.  
  
```  
void SetPaneAnimation(
    int nIndex,  
    HIMAGELIST hImageList,  
    UINT nFrameRate=500,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nIndex*  
 Gibt den Index des Bereichs eine Animation zugewiesen werden soll.  
  
 [in] *hImageList*  
 Gibt ein Handle für die Bildliste, die die Animationsframes enthält.  
  
 [in] *nFrameRate*  
 Gibt die Framerate in Millisekunden, für die Animation an.  
  
 [in] *bUpdate*  
 Wenn `TRUE`, eine unverzügliche Aktualisierung des Inhalts im Bereich. Andernfalls wird der Inhalt im Bereich aktualisiert, wenn für ungültig erklärt wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die aktuelle Animation deaktivieren möchten, rufen Sie `SetPaneAnimation` mit `hImageList` festgelegt `NULL`.  
  
##  <a name="setpanebackgroundcolor"></a>  CMFCStatusBar::SetPaneBackgroundColor  
 Legt die Hintergrundfarbe des Status-Leistenbereich fest.  
  
```  
void SetPaneBackgroundColor(
    int nIndex,  
    COLORREF clrBackground=(COLORREF)-1,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nIndex*  
 Gibt den Index des Bereichs für die neue Hintergrundfarbe festzulegen.  
  
 [in] *ClrBackground*  
 Die neue Hintergrundfarbe angibt.  
  
 [in] *bUpdate*  
 Wenn `TRUE`, eine unverzügliche Aktualisierung des Inhalts im Bereich. Andernfalls werden erst aktualisiert, den Inhalt im Bereich im Bereich durch eine andere Methode ungültig ist.  
  
##  <a name="setpaneicon"></a>  CMFCStatusBar::SetPaneIcon  
 Legen Sie das Symbol des Status-Leistenbereich.  
  
```  
void SetPaneIcon(
    int nIndex,  
    HICON hIcon,  
    BOOL bUpdate=TRUE);

 
void SetPaneIcon(
    int nIndex,  
    HBITMAP hBmp,  
    COLORREF clrTransparent=RGB(255, 0, 255),  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nIndex*  
 Gibt den Index des Bereichs für das Bild festgelegt.  
  
 [in] *hIcon*  
 Gibt ein Handle für das Symbol als Image Bereich festgelegt werden.  
  
 [in] *bUpdate*  
 Gibt an, ob den Bereich Inhalt sofort zu aktualisieren.  
  
 [in] *hBmp*  
 Gibt ein Handle für die Bitmap als Image Bereich festgelegt werden.  
  
 [in] *ClrTransparent*  
 Gibt die transparente Farbe der Bitmap, die die *hBmp* angibt.  
  
### <a name="remarks"></a>Hinweise  
 Übergeben Sie entweder `HICON` oder `HBITMAP` sowie die transparente Farbe des Bereichs Image festgelegt. Wenn Sie nicht möchten, um das Bild nicht mehr angezeigt wird, übergeben die `NULL` Wert als Bild-Handle.  
  
 Es ist eine laufende Animation, [CMFCStatusBar::SetPaneAnimation](#setpaneanimation) wurde festgelegt, wird die Animation beendet.  
  
##  <a name="setpaneinfo"></a>  CMFCStatusBar::SetPaneInfo  

  
```  
void SetPaneInfo(
    int nIndex,  
    UINT nID,  
    UINT nStyle,  
    int cxWidth);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nIndex*  
 [in] *nID*  
 [in] *nStyle*  
 [in] *CxWidth*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpaneprogress"></a>  CMFCStatusBar::SetPaneProgress  
 Legen Sie die aktuellen Statusanzeige der Statusanzeige für den angegebenen Bereich.  
  
```  
void SetPaneProgress(
    int nIndex,  
    long nCurr,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nIndex*  
 Gibt den Index des Bereichs für die Aktualisierung der Statusanzeige.  
  
 [in] *nCurr*  
 Gibt den aktuellen Wert der Statusanzeige.  
  
 [in] *bUpdate*  
 Gibt an, ob der Bereich sofort aktualisiert werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, wenn die Statusanzeige für die Statusanzeige im angegebenen Bereich aktualisiert werden soll.  
  
 Um diese Funktion für den angegebenen Bereich zu verwenden, rufen Sie [CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar) erste.  
  
##  <a name="setpanestyle"></a>  CMFCStatusBar::SetPaneStyle  

  
```  
void SetPaneStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nIndex*  
 [in] *nStyle*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpanetext"></a>  CMFCStatusBar::SetPaneText  

  
```  
virtual BOOL SetPaneText(
    int nIndex,  
    LPCTSTR lpszNewText,  
    BOOL bUpdate = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nIndex*  
 [in] *LpszNewText*  
 [in] *bUpdate*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpanetextcolor"></a>  CMFCStatusBar::SetPaneTextColor  
 Legt die Textfarbe des angegebenen Bereichs fest.  
  
```  
void SetPaneTextColor(
    int nIndex,  
    COLORREF clrText=(COLORREF)-1,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nIndex*  
 Gibt den Index des Bereichs, dem Sie eine neue Farbe zuweisen möchten.  
  
 [in] *ClrText*  
 Gibt die Textfarbe.  
  
 [in] *bUpdate*  
 Wenn `TRUE`, eine unverzügliche Aktualisierung des Inhalts im Bereich. Andernfalls werden erst aktualisiert, den Inhalt im Bereich im Bereich durch eine andere Methode ungültig ist.  
  
##  <a name="setpanewidth"></a>  CMFCStatusBar::SetPaneWidth  
 Legen Sie die Breite der Balken Statusbereich an.  
  
```  
void SetPaneWidth(
    int nIndex,  
    int cx);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nIndex*  
 Der Index des Status-Leistenbereich für die neue Breite festgelegt.  
  
 [in] *Cx*  
 Die neue Breite des Status-Leistenbereich in Pixel.  
  
##  <a name="settiptext"></a>  CMFCStatusBar::SetTipText  
 Legen Sie den QuickInfo-Text, der eine Status-Leistenbereich.  
  
```  
void SetTipText(
    int nIndex,  
    LPCTSTR pszTipText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nIndex*  
 Der Index des Bereichs, dem Sie den QuickInfo-Text zuweisen möchten.  
  
 [in] *PszTipText*  
 Der neue QuickInfo-Text.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CPane-Klasse](../../mfc/reference/cpane-class.md)   
 [CStatusBar-Klasse](../../mfc/reference/cstatusbar-class.md)
