---
title: CMFCOutlookBarTabCtrl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::AddControl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::Create
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableInPlaceEdit
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableScrollButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetVisiblePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsMode2003
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowOptions
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetActiveTab
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetPageButtonTextAlign
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetToolbarImageList
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetVisiblePageButtons
dev_langs:
- C++
helpviewer_keywords:
- CMFCOutlookBarTabCtrl [MFC], AddControl
- CMFCOutlookBarTabCtrl [MFC], CanShowFewerPageButtons
- CMFCOutlookBarTabCtrl [MFC], CanShowMorePageButtons
- CMFCOutlookBarTabCtrl [MFC], Create
- CMFCOutlookBarTabCtrl [MFC], EnableAnimation
- CMFCOutlookBarTabCtrl [MFC], EnableInPlaceEdit
- CMFCOutlookBarTabCtrl [MFC], EnableScrollButtons
- CMFCOutlookBarTabCtrl [MFC], GetBorderSize
- CMFCOutlookBarTabCtrl [MFC], GetVisiblePageButtons
- CMFCOutlookBarTabCtrl [MFC], IsAnimation
- CMFCOutlookBarTabCtrl [MFC], IsMode2003
- CMFCOutlookBarTabCtrl [MFC], OnShowFewerPageButtons
- CMFCOutlookBarTabCtrl [MFC], OnShowMorePageButtons
- CMFCOutlookBarTabCtrl [MFC], OnShowOptions
- CMFCOutlookBarTabCtrl [MFC], SetActiveTab
- CMFCOutlookBarTabCtrl [MFC], SetBorderSize
- CMFCOutlookBarTabCtrl [MFC], SetPageButtonTextAlign
- CMFCOutlookBarTabCtrl [MFC], SetToolbarImageList
- CMFCOutlookBarTabCtrl [MFC], SetVisiblePageButtons
ms.assetid: b1f2b3f7-cc59-49a3-99d8-7ff9b37c044b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a54f8e21c253c46c6a6a086fd10d193a18b7e59e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718262"
---
# <a name="cmfcoutlookbartabctrl-class"></a>CMFCOutlookBarTabCtrl Class
Ein Registerkarten-Steuerelement mit dem Aussehen des **Navigationsbereichs** in Microsoft Outlook verfügt.  
 Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.    
## <a name="syntax"></a>Syntax  
  
```  
class CMFCOutlookBarTabCtrl : public CMFCBaseTabCtrl  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCOutlookBarTabCtrl::CMFCOutlookBarTabCtrl`|Standardkonstruktor|  
|`CMFCOutlookBarTabCtrl::~CMFCOutlookBarTabCtrl`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCOutlookBarTabCtrl::AddControl](#addcontrol)|Fügt ein Windows-Steuerelement als eine neue Registerkarte in der Outlook-Leiste hinzu.|  
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|Vom Framework aufgerufen, eine Registerkarte, um zu bestimmen, wird angezeigt, wenn ein Benutzer, die die Abmessungen des Bearbeitungsfelds benennt. (Überschreibt `CMFCBaseTabCtrl::CalcRectEdit`.)|  
|[CMFCOutlookBarTabCtrl::CanShowFewerPageButtons](#canshowfewerpagebuttons)|Wird vom Framework aufgerufen, während der Größenänderung von Fenstern annimmt Vorgänge zu bestimmen, ob weniger Outlook-Leiste Registerkarte Seitenschaltflächen angezeigt werden können, als die derzeit sichtbar sind.|  
|[CMFCOutlookBarTabCtrl::CanShowMorePageButtons](#canshowmorepagebuttons)|Wird vom Framework aufgerufen, während der Größenänderung von Fenstern annimmt Vorgänge zu bestimmen, ob weitere Outlook-Leiste Registerkarte Seitenschaltflächen angezeigt werden können, als die derzeit sichtbar sind.|  
|[CMFCOutlookBarTabCtrl::Create](#create)|Das Registerkarten-Steuerelement von Outlook-Leiste wird erstellt.|  
|`CMFCOutlookBarTabCtrl::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation)|Gibt an, ob die Animation, die während des Wechsels zwischen aktiven Registerkarten tritt auf, aktiviert ist.|  
|[CMFCOutlookBarTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|Gibt an, ob ein Benutzer die Bezeichnungen auf die Schaltflächen der Outlook-Leiste auf der Registerkarte ändern kann. (Überschreibt [CMFCBaseTabCtrl::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit).)|  
|[CMFCOutlookBarTabCtrl::EnableScrollButtons](#enablescrollbuttons)|Wird aufgerufen, durch das Framework um Schaltflächen zu ermöglichen, die der Benutzer einen Bildlauf durch Schaltflächen in der Outlook-Leistenbereich durchführen kann.|  
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|Identifiziert den Bereich, der einen angegebenen Punkt enthält. (Überschreibt [CMFCBaseTabCtrl::FindTargetWnd](../../mfc/reference/cmfcbasetabctrl-class.md#findtargetwnd).)|  
|[CMFCOutlookBarTabCtrl::GetBorderSize](#getbordersize)|Gibt zurück, die Rahmengröße des Outlook Registerkarten-Steuerelements.|  
|`CMFCOutlookBarTabCtrl::GetTabArea`|Ruft ab, die Größe und Position des Registerkartenbereichs des Registerkarten-Steuerelements. (Überschreibt [CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea).)|  
|`CMFCOutlookBarTabCtrl::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMFCOutlookBarTabCtrl::GetVisiblePageButtons](#getvisiblepagebuttons)||  
|[CMFCOutlookBarTabCtrl::IsAnimation](#isanimation)|Bestimmt, ob die Animation, die während des Wechsels zwischen aktiven Registerkarten tritt auf, aktiviert ist.|  
|[CMFCOutlookBarTabCtrl::IsMode2003](#ismode2003)|Bestimmt, ob das Registerkarten-Steuerelement von Outlook-Leiste in einem Modus ausgeführt wird, die Microsoft Outlook 2003 emuliert.|  
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|Bestimmt, ob ein Punkt innerhalb der Registerkartenbereich ist. (Überschreibt [CMFCBaseTabCtrl::IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea).)|  
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|Bestimmt, ob eine Registerkarte gelöst werden kann. (Überschreibt [CMFCBaseTabCtrl::IsTabDetachable](../../mfc/reference/cmfcbasetabctrl-class.md#istabdetachable).)|  
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|Vom Framework aufgerufen, wenn eine Registerkarte eingefügt oder entfernt wird. (Überschreibt `CMFCBaseTabCtrl::OnChangeTabs`.)|  
|[CMFCOutlookBarTabCtrl::OnShowFewerPageButtons](#onshowfewerpagebuttons)|Vom Framework aufgerufen, die Anzahl der Registerschaltflächen-Seite zu verringern, die angezeigt werden.|  
|[CMFCOutlookBarTabCtrl::OnShowMorePageButtons](#onshowmorepagebuttons)|Wird aufgerufen, durch das Framework zum Erhöhen der Anzahl der Registerschaltflächen-Seite, die angezeigt werden.|  
|[CMFCOutlookBarTabCtrl::OnShowOptions](#onshowoptions)|Zeigt die **Optionen des Navigationsbereichs** Dialogfeld.|  
|`CMFCOutlookBarTabCtrl::RecalcLayout`|Berechnet das interne Layout des Registerkarten-Steuerelements. (Überschreibt [CMFCBaseTabCtrl::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout).)|  
|[CMFCOutlookBarTabCtrl::SetActiveTab](#setactivetab)|Legt die aktive Registerkarte fest. (Überschreibt [CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab).)|  
|[CMFCOutlookBarTabCtrl::SetBorderSize](#setbordersize)|Legt fest, die Rahmengröße des Outlook Registerkarten-Steuerelements.|  
|[CMFCOutlookBarTabCtrl::SetPageButtonTextAlign](#setpagebuttontextalign)|Legt die Ausrichtung der Beschriftungen für die Schaltflächen der Outlook-Leiste auf der Registerkarte fest.|  
|[CMFCOutlookBarTabCtrl::SetToolbarImageList](#settoolbarimagelist)|Legt die Bitmap, die die Symbole enthält, die am unteren Rand der Outlook-Leiste in Outlook 2003-Modus angezeigt werden (siehe [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)).|  
|[CMFCOutlookBarTabCtrl::SetVisiblePageButtons](#setvisiblepagebuttons)||  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Erstellen einer Outlook-Leiste, das Andocken unterstützt eine `CMFCOutlookBar` Objekt, das die Outlook-Leiste Registerkarten-Steuerelement zu hosten. Weitere Informationen finden Sie unter [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie zum Initialisieren einer `CMFCOutlookBarTabCtrl` Objekt, und Verwenden verschiedener Methoden in der `CMFCOutlookBarTabCtrl` Klasse. Das Beispiel zeigt, wie ermöglichen die direkte Bearbeitung der textbezeichnung auf Schaltflächen auf der Seite Registerkarte der Outlook-Leiste, aktivieren die Animation, Scroll-Handles, mit denen den Benutzer einen Bildlauf durch Schaltflächen in der Outlook-Leistenbereich, legen Sie die Rahmengröße von der Outlook-Registerkarte Inhalt aktivieren ROL, und legen Sie die Ausrichtung der Beschriftungen Text auf Schaltflächen auf der Registerkarte der Outlook-Leiste. Dieser Codeausschnitt ist Teil der [Outlook Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookDemo#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_1.cpp)]  
[!code-cpp[NVC_MFC_OutlookDemo#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxoutlookbartabctrl.h  
  
##  <a name="addcontrol"></a>  CMFCOutlookBarTabCtrl::AddControl  
 Fügt ein Windows-Steuerelement als eine neue Registerkarte in der Outlook-Leiste hinzu.  
  
```  
void AddControl(
    CWnd* pWndCtrl,  
    LPCTSTR lpszName,  
    int nImageID=-1,  
    BOOL bDetachable=TRUE,  
    DWORD dwControlBarStyle=AFX_CBRS_FLOAT |  AFX_CBRS_CLOSE | AFX_CBRS_RESIZE |  CBRS_AFX_AUTOHIDE);
```  
  
### <a name="parameters"></a>Parameter  
*pWndCtrl*<br/>
[in] Ein Zeiger auf ein Steuerelement hinzufügen.  
  
*Wert*<br/>
[in] Gibt den Namen der Registerkarte an.  
  
*bDetachable*<br/>
[in] Wenn TRUE, wird die Seite als entfernbare erstellt werden.  
  
*nImageID*<br/>
[in] Der Bildindex in der internen Bildliste des Bildes, das in der neuen Registerkarte angezeigt werden.  
  
*dwControlBarStyle*<br/>
[in] Gibt den Stil AFX_ CBRS_ * für umschlossene andockbare Bereiche.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um ein Steuerelement als eine neue Seite mit einer Outlook-Leiste hinzuzufügen.  
  
 Diese Funktion ruft intern auf [:: addTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab).  
  
 Setzen Sie *bDetachable* auf "true", `AddControl` erstellt intern eine `CDockablePaneAdapter` Objekt aus, und dient als Wrapper für das hinzugefügte Steuerelement. Automatisch wird die Common Language Runtime-Klasse, der dem Fenster im Registerkartenformat auf die Common Language Runtime-Klasse der `CMFCOutlookBar` und der Common Language Runtime-Klasse des unverankerten Rahmens zu `CMultiPaneFrameWnd`.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `AddControl` -Methode in der die `CMFCOutlookBarTabCtrl` Klasse. Dieser Codeausschnitt ist Teil der [Outlook Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookDemo#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_3.cpp)]  
  
##  <a name="canshowfewerpagebuttons"></a>  CMFCOutlookBarTabCtrl::CanShowFewerPageButtons  
 Wird vom Framework aufgerufen, während der Größenänderung Vorgänge aus, um zu bestimmen, ob weniger Outlook-Leiste Registerkarte Seitenschaltflächen angezeigt werden können, als die derzeit sichtbar sind.  
  
```  
virtual BOOL CanShowFewerPageButtons() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn es mehr als eine Schaltfläche. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Das Outlook-Leiste Registerkarten-Steuerelement wird dynamisch hinzugefügt oder entfernt Registerkarten aus der Anzeige, je nachdem, wie viel Platz verfügbar ist. Diese Methode wird vom Framework verwendet, um diesen Prozess zu erleichtern.  
  
##  <a name="canshowmorepagebuttons"></a>  CMFCOutlookBarTabCtrl::CanShowMorePageButtons  
 Wird vom Framework aufgerufen, während der Größenänderung Vorgänge aus, um zu bestimmen, ob weitere Outlook-Leiste Registerkarte Seitenschaltflächen angezeigt werden können, als die derzeit sichtbar sind.  
  
```  
virtual BOOL CanShowMorePageButtons() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn es befinden sich Schaltflächen, die nicht derzeit sichtbar sind. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Das Outlook-Leiste Registerkarten-Steuerelement wird dynamisch hinzugefügt oder entfernt Registerkarten aus der Anzeige, je nachdem, wie viel Platz verfügbar ist. Diese Methode wird vom Framework verwendet, um diesen Prozess zu erleichtern.  
  
##  <a name="create"></a>  CMFCOutlookBarTabCtrl::Create  
 Das Registerkarten-Steuerelement von Outlook-Leiste wird erstellt.  
  
```  
virtual BOOL Create(
    const CRect& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
*Rect*<br/>
[in] Gibt an, die ursprüngliche Größe und Position, in Pixel.  
  
*pParentWnd*<br/>
[in] Verweist auf das übergeordnete Fenster. Nicht darf NULL sein.  
  
*nID*<br/>
[in] Die Steuerelement-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Steuerelement erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel Outlook-Leiste Registerkarten-Steuerelemente werden erstellt, wenn [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md) steuert die WM_CREATE-Nachricht des Prozesses.  
  
##  <a name="enableanimation"></a>  CMFCOutlookBarTabCtrl::EnableAnimation  
 Gibt an, ob die Animation, die während des Wechsels zwischen aktiven Registerkarten tritt auf, aktiviert ist.  
  
```  
static void EnableAnimation(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
*bAktivieren*<br/>
[in] Gibt an, ob die Animation aktiviert oder deaktiviert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion zum Aktivieren und Deaktivieren von Animationen. Wenn der Benutzer eine Registerkarte geöffnet wird, wird Beschriftung mit der Seite nach oben oder unten aus, wenn die Animation aktiviert ist. Wenn die Animation deaktiviert ist, wird die Seite sofort aktiv.  
  
 Die Standardeinstellung ist die Animation aktiviert.  
  
##  <a name="enableinplaceedit"></a>  CMFCOutlookBarTabCtrl::EnableInPlaceEdit  
 Gibt an, ob ein Benutzer die Bezeichnungen auf der Seitenschaltflächen auf der Registerkarte der Outlook-Leiste nicht ändern kann.  
  
```  
virtual void EnableInPlaceEdit(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 *bAktivieren*  
 Bei "true", ermöglichen Sie die direkte Bearbeitung der textbezeichnung. False gibt an, deaktivieren Sie die direkte Bearbeitung aus.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion aktivieren oder Deaktivieren des direktes Bearbeiten von Beschriftungen auf der Registerkarte Seitenschaltflächen. Die direkte Bearbeitung ist standardmäßig deaktiviert.  
  
##  <a name="enablescrollbuttons"></a>  CMFCOutlookBarTabCtrl::EnableScrollButtons  
 Wird aufgerufen, durch das Framework um Scroll-Handles zu aktivieren, mit die den Benutzer einen Bildlauf durch Schaltflächen in der Outlook-Leistenbereich durchführen zu können.  
  
```  
void EnableScrollButtons(
    BOOL bEnable = TRUE,  
    BOOL bIsUp = TRUE,  
    BOOL bIsDown = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
*bAktivieren*<br/>
[in] Bestimmt, ob die Bildlauf-Schaltflächen angezeigt werden.  
  
*bIsUp*<br/>
[in] Bestimmt, ob die obere Bildlaufleiste angezeigt wird.  
  
*bIsDown*<br/>
[in] Bestimmt, ob die Bildlaufleiste unten angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
 Ermöglicht die Anzeige der scrollschaltflächen. Diese Methode wird vom Framework aufgerufen, wenn die aktive Registerkarte ändert die Bildlaufschaltflächen wiederherstellen.  
  
##  <a name="getbordersize"></a>  CMFCOutlookBarTabCtrl::GetBorderSize  
 Gibt zurück, die Rahmengröße des Outlook Registerkarten-Steuerelements.  
  
```  
int GetBorderSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Rahmengröße in Pixel.  
  
##  <a name="getvisiblepagebuttons"></a>  CMFCOutlookBarTabCtrl::GetVisiblePageButtons  

  
```  
int GetVisiblePageButtons() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isanimation"></a>  CMFCOutlookBarTabCtrl::IsAnimation  
 Gibt an, ob die Animation, die während des Wechsels zwischen aktiven Registerkarten tritt auf, aktiviert ist.  
  
```  
static BOOL IsAnimation();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Animation aktiviert ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation) Funktion aktivieren oder Deaktivieren von Animationen.  
  
##  <a name="ismode2003"></a>  CMFCOutlookBarTabCtrl::IsMode2003  
 Bestimmt, ob das Registerkarten-Steuerelement von Outlook-Leiste in einem Modus ausgeführt wird, die Microsoft Outlook 2003 emuliert.  
  
```  
BOOL IsMode2003() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Outlook-Leiste Registerkarten-Steuerelement in Outlook 2003-Modus. andernfalls "false";  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert wird festgelegt, indem [CMFCOutlookBar::SetMode2003](../../mfc/reference/cmfcoutlookbar-class.md#setmode2003).  
  
##  <a name="onshowfewerpagebuttons"></a>  CMFCOutlookBarTabCtrl::OnShowFewerPageButtons  
 Vom Framework aufgerufen, die Anzahl der Registerschaltflächen-Seite zu verringern, die angezeigt werden.  
  
```  
virtual void OnShowFewerPageButtons();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode passt die Anzahl der sichtbaren Seite Registerkartenschaltflächen beim Ändern der Größe des Steuerelements.  
  
##  <a name="onshowmorepagebuttons"></a>  CMFCOutlookBarTabCtrl::OnShowMorePageButtons  
 Wird aufgerufen, durch das Framework zum Erhöhen der Anzahl der Registerschaltflächen-Seite, die angezeigt werden.  
  
```  
virtual void OnShowMorePageButtons();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode passen Sie die Anzahl von Registerkarten-Seite-Schaltflächen, die angezeigt werden, wenn die Größe des Steuerelements geändert wird.  
  
##  <a name="onshowoptions"></a>  CMFCOutlookBarTabCtrl::OnShowOptions  
 Zeigt die **Optionen des Navigationsbereichs** Dialogfeld.  
  
```  
virtual void OnShowOptions();
```  
  
### <a name="remarks"></a>Hinweise  
 Die **Optionen des Navigationsbereichs** Dialogfeld ermöglicht dem Benutzer, wählen Sie die Registerkarte Seitenschaltflächen angezeigt werden soll, und die Reihenfolge, in der sie angezeigt werden.  
  
 Diese Methode wird vom Framework aufgerufen, wenn der Benutzer wählt die **Optionen des Navigationsbereichs** Menüelement des Steuerelements anpassungsmenü zu öffnen.  
  
##  <a name="setactivetab"></a>  CMFCOutlookBarTabCtrl::SetActiveTab  
 Legt die aktive Registerkarte fest. Die aktive Registerkarte ist diejenige, die geöffnet ist, mit dem Inhalt angezeigt wird.  
  
```  
virtual BOOL SetActiveTab(int iTab);
```  
  
### <a name="parameters"></a>Parameter  
*iTab*<br/>
[in] Der nullbasierte Index einer Registerkarte geöffnet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, wenn die angegebene Registerkarte erfolgreich geöffnet wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Der visuelle Effekt der aktive Registerkarte festlegen, hängt davon ab, ob Sie die Animation aktiviert haben. Weitere Informationen finden Sie unter [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation).  
  
##  <a name="setbordersize"></a>  CMFCOutlookBarTabCtrl::SetBorderSize  
 Legt fest, die Rahmengröße des Outlook Registerkarten-Steuerelements.  
  
```  
void SetBorderSize(int nBorderSize);
```  
  
### <a name="parameters"></a>Parameter  
*nBorderSize*<br/>
[in] Gibt die neue Rahmengröße in Pixel an.  
  
### <a name="remarks"></a>Hinweise  
 Legt die Rahmengröße der neuen fest, und berechnet das Layout der Outlook-Fenster.  
  
##  <a name="setpagebuttontextalign"></a>  CMFCOutlookBarTabCtrl::SetPageButtonTextAlign  
 Legt die Ausrichtung der Beschriftungen für die Schaltflächen der Outlook-Leiste auf der Registerkarte fest.  
  
```  
void SetPageButtonTextAlign(
    UINT uiAlign,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
*uiAlign*<br/>
[in] Gibt die Ausrichtung des Texts an.  
  
*bRedraw*<br/>
[in] True gibt an, das Outlook-Fenster wird neu gezeichnet werden.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um die Ausrichtung des Texts für Seitenschaltflächen zu ändern.  
  
 *UiAlign* kann eine der folgenden Werte:  
  
|Konstante|Bedeutung|  
|--------------|-------------|  
|TA_LEFT|Linksbündig|  
|TA_CENTER|Ausrichtung zentriert|  
|TA_RIGHT|Rechtsbündig|  
  
 Der Standardwert ist TA_CENTER.  
  
##  <a name="settoolbarimagelist"></a>  CMFCOutlookBarTabCtrl::SetToolbarImageList  
 Legt fest, die Bitmap, die die Symbole enthält, die am unteren Rand der Outlook-Leiste in Outlook 2003-Modus angezeigt werden.  
  
```  
BOOL SetToolbarImageList(
    UINT uiID,  
    int cx,  
    COLORREF clrTransp=RGB(255, 0, 255));
```  
  
### <a name="parameters"></a>Parameter  
*uiID*<br/>
[in] Gibt die Ressourcen-ID beim Laden des Bilds an.  
  
*CX*<br/>
[in] Gibt die Breite eines Bilds in der Bildliste in Pixel an.  
  
*clrTransp*<br/>
[in] Ein RGB-Wert, der die transparente Farbe angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn erfolgreich; Andernfalls wird false ZURÜCKGEGEBEN.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion eine Bildliste anfügen, deren Images auf Symbolleisten-Schaltflächen im Microsoft Office 2003-Modus angezeigt werden. Bildindizes sollte die Seite enthält einen Index entsprechen.  
  
 Diese Methode sollte nur in Microsoft Office 2003-Modus nicht aufgerufen werden. Weitere Informationen finden Sie unter [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md).  
  
##  <a name="setvisiblepagebuttons"></a>  CMFCOutlookBarTabCtrl::SetVisiblePageButtons  

  
```  
void SetVisiblePageButtons(int nVisiblePageButtons);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nVisiblePageButtons*  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCBaseTabCtrl-Klasse](../../mfc/reference/cmfcbasetabctrl-class.md)   
 [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCOutlookBarPane-Klasse](../../mfc/reference/cmfcoutlookbarpane-class.md)
