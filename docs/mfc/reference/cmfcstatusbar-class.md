---
title: CMFCStatusBar-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCStatusBar
dev_langs:
- C++
helpviewer_keywords:
- CMFCStatusBar class
ms.assetid: f2960d1d-f4ed-41e8-bd99-0382b2f8d88e
caps.latest.revision: 36
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
ms.openlocfilehash: 20881637d74bafffbcf2e0c3dcd1cc98e173aa07
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcstatusbar-class"></a>CMFCStatusBar-Klasse
Die `CMFCStatusBar` -Klasse implementiert eine Statusleiste ähnelt der `CStatusBar` Klasse. Die `CMFCStatusBar` -Klasse verfügt jedoch über Funktionen, die von der `CStatusBar` -Klasse nicht bereitgestellt werden. Beispielsweise kann die Klasse Bilder, Animationen und Statusanzeigen anzeigen und auf einen Mausdoppelklick reagieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCStatusBar : public CPane  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCStatusBar::CalcFixedLayout](#calcfixedlayout)|(Überschreibt [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|  
|[CMFCStatusBar::CommandToIndex](#commandtoindex)||  
|[CMFCStatusBar::Create](#create)|Erstellt eine Steuerleiste und fügt es der [CPane](../../mfc/reference/cpane-class.md) Objekt. (Überschreibt [CPane::Create](../../mfc/reference/cpane-class.md#create).)|  
|[CMFCStatusBar::CreateEx](#createex)|Erstellt eine Steuerleiste und fügt es der [CPane](../../mfc/reference/cpane-class.md) Objekt. (Überschreibt [cpane:: CreateEx](../../mfc/reference/cpane-class.md#createex).)|  
|[CMFCStatusBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Bestimmt, ob ein weiterer Bereich dynamisch zwischen diesem und den übergeordneten Frame eingefügt werden kann. (Überschreibt [CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|  
|[CMFCStatusBar::EnablePaneDoubleClick](#enablepanedoubleclick)|Aktiviert oder deaktiviert, die der Umgang mit der Maus auf der Statusleiste doppelklickt.|  
|[CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar)|Zeigt eine Statusanzeige im angegebenen Bereich.|  
|[CMFCStatusBar::GetCount](#getcount)|Gibt die Anzahl der Bereiche in der Statusleiste angezeigt.|  
|[CMFCStatusBar::GetDrawExtendedArea](#getdrawextendedarea)||  
|[CMFCStatusBar::GetExtendedArea](#getextendedarea)||  
|[CMFCStatusBar::GetItemID](#getitemid)||  
|[CMFCStatusBar::GetItemRect](#getitemrect)||  
|[CMFCStatusBar::GetPaneInfo](#getpaneinfo)||  
|[CMFCStatusBar::GetPaneProgress](#getpaneprogress)||  
|[CMFCStatusBar::GetPaneStyle](#getpanestyle)|Gibt den Bereichsformat zurück. (Überschreibt [CBasePane::GetPaneStyle](../../mfc/reference/cbasepane-class.md#getpanestyle).)|  
|[CMFCStatusBar::GetPaneText](#getpanetext)||  
|[CMFCStatusBar::GetPaneWidth](#getpanewidth)|Gibt die Breite in Pixel der Statusleiste im angegebenen Bereich zurück.|  
|[CMFCStatusBar::GetTipText](#gettiptext)|Gibt den QuickInfo-Text für den angegebenen Bereich der Statusleiste an.|  
|[CMFCStatusBar::InvalidatePaneContent](#invalidatepanecontent)|Erklärt den angegebenen Bereich und seine Inhalte aktualisiert.|  
|[CMFCStatusBar::PreCreateWindow](#precreatewindow)|Vor dem Erstellen des Fensters Windows beigefügten aufgerufen `CWnd` Objekt. (Überschreibt [CWnd::PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).)|  
|[CMFCStatusBar::SetDrawExtendedArea](#setdrawextendedarea)||  
|[CMFCStatusBar::SetIndicators](#setindicators)||  
|[CMFCStatusBar::SetPaneAnimation](#setpaneanimation)|Weist eine Animation in den angegebenen Bereich.|  
|[CMFCStatusBar::SetPaneBackgroundColor](#setpanebackgroundcolor)|Legt die Hintergrundfarbe für den angegebenen Bereich der Statusleiste fest.|  
|[CMFCStatusBar::SetPaneIcon](#setpaneicon)|Legt das Indikatorsymbol für den angegebenen Bereich der Statusleiste an.|  
|[CMFCStatusBar::SetPaneInfo](#setpaneinfo)||  
|[CMFCStatusBar::SetPaneProgress](#setpaneprogress)|Legt den aktuellen Status der Statusanzeige für den angegebenen Bereich der Statusleiste an.|  
|[CMFCStatusBar::SetPaneStyle](#setpanestyle)|Legt den Stil des Bereichs. (Überschreibt [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle).)|  
|[CMFCStatusBar::SetPaneText](#setpanetext)||  
|[CMFCStatusBar::SetPaneTextColor](#setpanetextcolor)|Legt die Textfarbe für den angegebenen Bereich der Statusleiste fest.|  
|[CMFCStatusBar::SetPaneWidth](#setpanewidth)|Legt die Breite in Pixel im angegebenen Bereich der Statusleiste an.|  
|[CMFCStatusBar::SetTipText](#settiptext)|Legt den QuickInfo-Text für den angegebenen Bereich der Statusleiste an.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCStatusBar::OnDrawPane](#ondrawpane)|Wird vom Framework aufgerufen, wenn es im Bereich der Statusleiste zeichnet.|  
  
## <a name="remarks"></a>Hinweise  
 Das folgende Diagramm zeigt eine Abbildung der Statusleiste aus [Status Leiste Demobeispiel](../../visual-cpp-samples.md) Anwendung.  
  
 ![Beispiel für CMFCStatusBar](../../mfc/reference/media/cmfcstatusbar.png "Cmfcstatusbar")  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die lokalen Variablen, die die Anwendung in verschiedenen Methoden aufrufen, verwendet die `CMFCStatusBar` Klasse. Diese Variablen werden in StatusBarDemoView.h deklariert. Der Hauptframe in "MainFrm.h" deklariert ist, das Dokument wird im StatusBarDemoDoc.h deklariert und die Ansicht wird im StatusBarDemoView.h deklariert. Dieser Codeausschnitt ist Teil der [Status Leiste Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo&#9;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_1.h)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Abrufen eines Verweises auf `CMFCStatusBar` Objekt durch die Einführung der `GetStatusBar` -Methode in "MainFrm.h" und das Aufrufen dieser Methode aus der `GetStatusBar` -Methode in StatusBarDemoView.h. Dieser Codeausschnitt ist Teil der [Status Leiste Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo&#7;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_2.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo&#8;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_3.h)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden, die in Aufrufen der `CMFCStatusBar` -Klasse in StatusBarDemoView.cpp. Die Konstanten werden in "MainFrm.h" deklariert. Das Beispiel zeigt, wie Sie auf das Symbol, den QuickInfo-Text, der der Statusleistenbereich festgelegt, eine Statusanzeige im angegebenen Bereich angezeigt, weisen Sie eine Animation in den angegebenen Bereich, legen Sie den Text und die Breite der Balken Statusbereich und Festlegen der aktuellen Statusanzeige die Statusanzeige für die Status-Leistenbereich. Dieser Codeausschnitt ist Teil der [Status Leiste Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo&6;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_4.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo&#1;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_5.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo&#2;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_6.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo&3;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_7.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo&4;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_8.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo&5;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_9.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxstatusbar.h  
  
##  <a name="a-namecalcfixedlayouta--cmfcstatusbarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CMFCStatusBar::CalcFixedLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bStretch`  
 [in] `bHorz`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namecommandtoindexa--cmfcstatusbarcommandtoindex"></a><a name="commandtoindex"></a>CMFCStatusBar::CommandToIndex  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIDFind`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namecreatea--cmfcstatusbarcreate"></a><a name="create"></a>CMFCStatusBar::Create  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParentWnd`  
 [in] `dwStyle`  
 [in] `nID`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namecreateexa--cmfcstatusbarcreateex"></a><a name="createex"></a>CMFCStatusBar::CreateEx  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = 0,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParentWnd`  
 [in] `dwCtrlStyle`  
 [in] `dwStyle`  
 [in] `nID`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namedoesallowdyninsertbeforea--cmfcstatusbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>CMFCStatusBar::DoesAllowDynInsertBefore  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameenablepanedoubleclicka--cmfcstatusbarenablepanedoubleclick"></a><a name="enablepanedoubleclick"></a>CMFCStatusBar::EnablePaneDoubleClick  
 Aktiviert oder deaktiviert, die der Umgang mit der Maus auf der Statusleiste doppelklickt.  
  
```  
void EnablePaneDoubleClick(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 Wenn `TRUE`, die Verarbeitung der Maus doppelklicken Sie auf, aktivieren. Andernfalls deaktivieren Sie die Verarbeitung der Maus doppelklicken.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Statusleiste Doppelklicks verarbeiten aktiviert ist, sendet Windows die `WM_COMMAND` Benachrichtigung zusammen mit einer Ressourcen-ID, der Besitzer der Statusleiste jedes Mal, die der Benutzer auf die Leiste Statusbereich doppelklickt.  
  
##  <a name="a-nameenablepaneprogressbara--cmfcstatusbarenablepaneprogressbar"></a><a name="enablepaneprogressbar"></a>CMFCStatusBar::EnablePaneProgressBar  
 Anzeigen einer Statusanzeige im angegebenen Bereich.  
  
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
 [in] `nIndex`  
 Gibt dem Index des Bereichs, dessen Statusanzeige zu aktivieren.  
  
 [in] `nTotal`  
 Gibt den maximalen Wert für die Statusanzeige zu bewegen.  
  
 [in] `bDisplayText`  
 Gibt an, ob den aktuelle Statuswert die Statusanzeige angezeigt werden soll.  
  
 [in] `clrBar`  
 Gibt die Hintergrundfarbe der Statusanzeige.  
  
 [in] `clrBarDest`  
 Gibt die sekundäre Farbe des Hintergrunds Leiste ausgeführt. Anderer Wert als `clrBar` zum Ausfüllen von einer Farbe in einem Farbverlauf gemischt.  
  
 [in] `clrProgressText`  
 Gibt die Farbe des Texts der Statusanzeige.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie den Fortschritt Leiste Aufruf deaktivieren möchten `EnablePaneProgressBar` mit `nTotal` auf-1 festgelegt. In der Standardeinstellung `nTotal` auf 100 festgelegt ist. Daher brauchen Sie keine zusätzlichen Berechnungen Status als Prozentsatz angezeigt.  
  
 Übergeben Sie unterschiedliche Werte für `clrBar` und `clrBarDest` , damit die Hintergrundfarbe der Statusleiste eine Farbe in einem Farbverlauf gemischt angezeigt. .  
  
 Rufen Sie zum Festlegen des aktuellen Status der [CMFCStatusBar::SetPaneProgress](#setpaneprogress) Methode.  
  
##  <a name="a-namegetcounta--cmfcstatusbargetcount"></a><a name="getcount"></a>CMFCStatusBar::GetCount  
 Ruft die Anzahl der Bereiche in der Statusleiste angezeigt.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bereiche in der Statusleiste angezeigt.  
  
##  <a name="a-namegetdrawextendedareaa--cmfcstatusbargetdrawextendedarea"></a><a name="getdrawextendedarea"></a>CMFCStatusBar::GetDrawExtendedArea  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL GetDrawExtendedArea() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetextendedareaa--cmfcstatusbargetextendedarea"></a><a name="getextendedarea"></a>CMFCStatusBar::GetExtendedArea  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL GetExtendedArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rect`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetitemida--cmfcstatusbargetitemid"></a><a name="getitemid"></a>CMFCStatusBar::GetItemID  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetitemrecta--cmfcstatusbargetitemrect"></a><a name="getitemrect"></a>CMFCStatusBar::GetItemRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 [in] `lpRect`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetpaneinfoa--cmfcstatusbargetpaneinfo"></a><a name="getpaneinfo"></a>CMFCStatusBar::GetPaneInfo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void GetPaneInfo(
    int nIndex,  
    UINT& nID,  
    UINT& nStyle,  
    int& cxWidth) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 [in] `nID`  
 [in] `nStyle`  
 [in] `cxWidth`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetpaneprogressa--cmfcstatusbargetpaneprogress"></a><a name="getpaneprogress"></a>CMFCStatusBar::GetPaneProgress  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
long GetPaneProgress(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetpanestylea--cmfcstatusbargetpanestyle"></a><a name="getpanestyle"></a>CMFCStatusBar::GetPaneStyle  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
UINT GetPaneStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetpanetexta--cmfcstatusbargetpanetext"></a><a name="getpanetext"></a>CMFCStatusBar::GetPaneText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void GetPaneText(
    int nIndex,  
    CString& s) const;  
  
CString GetPaneText(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 [in] `s`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetpanewidtha--cmfcstatusbargetpanewidth"></a><a name="getpanewidth"></a>CMFCStatusBar::GetPaneWidth  
 Ruft die Breite des Bereichs einer Statusleiste ab.  
  
```  
int GetPaneWidth(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Gibt den Index des im Bereich der Status angezeigt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite der Balken Statusbereich, `nIndex` gibt, andernfalls&0;, wenn eine Statusleiste nicht vorhanden ist.  
  
##  <a name="a-namegettiptexta--cmfcstatusbargettiptext"></a><a name="gettiptext"></a>CMFCStatusBar::GetTipText  
 Rufen Sie den QuickInfo-Text des Bereichs der Statusleiste an ab.  
  
```  
CString GetTipText(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Gibt den Index des Bereichs für die QuickInfo-Text abzurufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der QuickInfo-Text der Statusleiste, `nIndex` angibt. Wenn eine Leiste Statusbereich für den angegebenen nicht vorhanden ist, andernfalls die leere Zeichenfolge `nIndex` oder wenn der QuickInfo-Text leer ist.  
  
##  <a name="a-nameinvalidatepanecontenta--cmfcstatusbarinvalidatepanecontent"></a><a name="invalidatepanecontent"></a>CMFCStatusBar::InvalidatePaneContent  
 Für ungültig erklärt Statusbereich angezeigt, und zeichnen Sie den Inhalt erneut.  
  
```  
void InvalidatePaneContent(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Gibt den Index des Bereichs, dessen Inhalt für ungültig erklärt und neu gezeichnet wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Statusleiste ungültig ist, wird sie für das Neuzeichnen markiert. Windows zeichnet es neu bei der `UpdateWindow` -Methode sendet eine `WM_PAINT` Nachricht an die `OnPaint` Methode.  
  
##  <a name="a-nameondrawpanea--cmfcstatusbarondrawpane"></a><a name="ondrawpane"></a>CMFCStatusBar::OnDrawPane  
 Zeichnen Sie den Bereich der Statusleiste neu.  
  
```  
virtual void OnDrawPane(
    CDC* pDC,  
    CMFCStatusBarPaneInfo* pPane);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf einen Gerätekontext für das Zeichnen.  
  
 [in] `pPane`  
 Ein Zeiger auf eine `CMFCStatusBarPaneInfo` -Struktur, die die Informationen zum zu zeichnenden Bereich enthält.  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung `OnDrawPane` zeichnet im Bereich mit den Gerätekontext `pDC` entsprechend dem Layout und den Inhalt des Bereichs.  
  
 Überschreiben Sie diese Methode in einer `CMFCStatusBar`-abgeleitete Klasse, um die Darstellung eines Bereichs anzupassen.  
  
##  <a name="a-nameprecreatewindowa--cmfcstatusbarprecreatewindow"></a><a name="precreatewindow"></a>CMFCStatusBar::PreCreateWindow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `cs`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetdrawextendedareaa--cmfcstatusbarsetdrawextendedarea"></a><a name="setdrawextendedarea"></a>CMFCStatusBar::SetDrawExtendedArea  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetDrawExtendedArea(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bSet`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetindicatorsa--cmfcstatusbarsetindicators"></a><a name="setindicators"></a>CMFCStatusBar::SetIndicators  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL SetIndicators(
    const UINT* lpIDArray,  
    int nIDCount);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpIDArray`  
 [in] `nIDCount`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetpaneanimationa--cmfcstatusbarsetpaneanimation"></a><a name="setpaneanimation"></a>CMFCStatusBar::SetPaneAnimation  
 Weist eine Animation in den angegebenen Bereich.  
  
```  
void SetPaneAnimation(
    int nIndex,  
    HIMAGELIST hImageList,  
    UINT nFrameRate=500,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Gibt den Index des Bereichs eine Animation zugewiesen werden soll.  
  
 [in] `hImageList`  
 Gibt ein Handle für die Liste der Images, die die Frame-Animationen enthält.  
  
 [in] `nFrameRate`  
 Gibt die Framerate für die Animation in Millisekunden an.  
  
 [in] `bUpdate`  
 Wenn `TRUE`, aktualisieren Sie den Bereich Inhalt sofort. Andernfalls wird der Bereich Inhalt aktualisiert, wenn er bereits ungültig ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die aktuelle Animation deaktivieren möchten, rufen Sie `SetPaneAnimation` mit `hImageList` festgelegt `NULL`.  
  
##  <a name="a-namesetpanebackgroundcolora--cmfcstatusbarsetpanebackgroundcolor"></a><a name="setpanebackgroundcolor"></a>CMFCStatusBar::SetPaneBackgroundColor  
 Legt die Hintergrundfarbe der im Bereich der Status angezeigt.  
  
```  
void SetPaneBackgroundColor(
    int nIndex,  
    COLORREF clrBackground=(COLORREF)-1,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Gibt den Index des Bereichs für die neue Hintergrundfarbe festzulegen.  
  
 [in] `clrBackground`  
 Gibt die neue Hintergrundfarbe an.  
  
 [in] `bUpdate`  
 Wenn `TRUE`, aktualisieren Sie den Bereich Inhalt sofort. Andernfalls werden erst aktualisiert, der Inhalt im Bereich mit einer anderen Methode ungültig ist.  
  
##  <a name="a-namesetpaneicona--cmfcstatusbarsetpaneicon"></a><a name="setpaneicon"></a>CMFCStatusBar::SetPaneIcon  
 Legen Sie das Symbol im Statusbereich der Leiste.  
  
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
 [in] `nIndex`  
 Gibt den Index des Bereichs für das Bild festgelegt.  
  
 [in] `hIcon`  
 Gibt ein Handle für das Symbol wie das Bild im Bereich festgelegt werden.  
  
 [in] `bUpdate`  
 Gibt an, ob den Bereich Inhalt sofort zu aktualisieren.  
  
 [in] `hBmp`  
 Gibt ein Handle für die Bitmap als Bild Bereich festgelegt werden.  
  
 [in] `clrTransparent`  
 Gibt die transparente Farbe der Bitmap, die die `hBmp` angibt.  
  
### <a name="remarks"></a>Hinweise  
 Übergeben Sie entweder `HICON` oder `HBITMAP` sowie die transparente Farbe des Bereichs Bild festlegen. Wenn Sie nicht mehr das Bild anzeigen möchten, übergeben Sie die `NULL` Wert als Bild-Handle.  
  
 Es ist Animation ausgeführte, [CMFCStatusBar::SetPaneAnimation](#setpaneanimation) wurde festgelegt, wird die Animation beendet.  
  
##  <a name="a-namesetpaneinfoa--cmfcstatusbarsetpaneinfo"></a><a name="setpaneinfo"></a>CMFCStatusBar::SetPaneInfo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetPaneInfo(
    int nIndex,  
    UINT nID,  
    UINT nStyle,  
    int cxWidth);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 [in] `nID`  
 [in] `nStyle`  
 [in] `cxWidth`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetpaneprogressa--cmfcstatusbarsetpaneprogress"></a><a name="setpaneprogress"></a>CMFCStatusBar::SetPaneProgress  
 Legen Sie die aktuellen Statusanzeige der Statusanzeige für den angegebenen Bereich.  
  
```  
void SetPaneProgress(
    int nIndex,  
    long nCurr,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Gibt den Index des Bereichs für die Statusanzeige zu aktualisieren.  
  
 [in] `nCurr`  
 Gibt den aktuellen Wert der Statusanzeige.  
  
 [in] `bUpdate`  
 Gibt an, ob der Bereich sofort aktualisiert werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, wenn die Statusanzeige für die Statusanzeige im angegebenen Bereich aktualisiert werden soll.  
  
 Um diese Funktion für den angegebenen Bereich zu verwenden, müssen Sie aufrufen [CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar) ersten.  
  
##  <a name="a-namesetpanestylea--cmfcstatusbarsetpanestyle"></a><a name="setpanestyle"></a>CMFCStatusBar::SetPaneStyle  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetPaneStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 [in] `nStyle`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetpanetexta--cmfcstatusbarsetpanetext"></a><a name="setpanetext"></a>CMFCStatusBar::SetPaneText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL SetPaneText(
    int nIndex,  
    LPCTSTR lpszNewText,  
    BOOL bUpdate = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 [in] `lpszNewText`  
 [in] `bUpdate`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetpanetextcolora--cmfcstatusbarsetpanetextcolor"></a><a name="setpanetextcolor"></a>CMFCStatusBar::SetPaneTextColor  
 Legt die Textfarbe im angegebenen Bereich fest.  
  
```  
void SetPaneTextColor(
    int nIndex,  
    COLORREF clrText=(COLORREF)-1,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Gibt den Index des Bereichs, dem Sie eine neue Farbe zuweisen möchten.  
  
 [in] `clrText`  
 Gibt die Farbe des Texts an.  
  
 [in] `bUpdate`  
 Wenn `TRUE`, aktualisieren Sie den Bereich Inhalt sofort. Andernfalls werden erst aktualisiert, der Inhalt im Bereich mit einer anderen Methode ungültig ist.  
  
##  <a name="a-namesetpanewidtha--cmfcstatusbarsetpanewidth"></a><a name="setpanewidth"></a>CMFCStatusBar::SetPaneWidth  
 Festlegen Sie die Breite der Balken Statusbereich.  
  
```  
void SetPaneWidth(
    int nIndex,  
    int cx);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Der Index des im Statusbereich angezeigt, für die neue Breite festgelegt.  
  
 [in] `cx`  
 Die neue Breite des Bereichs Leiste Status in Pixel.  
  
##  <a name="a-namesettiptexta--cmfcstatusbarsettiptext"></a><a name="settiptext"></a>CMFCStatusBar::SetTipText  
 Legen Sie den QuickInfo-Text eines Status Leiste angezeigt.  
  
```  
void SetTipText(
    int nIndex,  
    LPCTSTR pszTipText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Der Index der Bereich, der den QuickInfo-Text zugewiesen werden soll.  
  
 [in] `pszTipText`  
 Der neue QuickInfo-Text.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CPane-Klasse](../../mfc/reference/cpane-class.md)   
 [CStatusBar-Klasse](../../mfc/reference/cstatusbar-class.md)

