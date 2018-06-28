---
title: CMFCOutlookBarTabCtrl-Klasse | Microsoft Docs
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
ms.openlocfilehash: d30ad25a21bf380dd7687ccd0da0fb261aeeb023
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37042308"
---
# <a name="cmfcoutlookbartabctrl-class"></a>CMFCOutlookBarTabCtrl Class
Ein Registerkarten-Steuerelement mit dem Aussehen des **Navigationsbereichs** in Microsoft Outlook verfügt.  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]    
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
|[CMFCOutlookBarTabCtrl::AddControl](#addcontrol)|Fügt ein Windows-Steuerelement als neue Registerkarte in der Outlook-Leiste hinzu.|  
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|Vom Framework aufgerufen, eine Registerkarte, um zu bestimmen, der angezeigt, wenn ein Benutzer die Dimensionen neben dem Bearbeitungsfeld benennt. (Überschreibt `CMFCBaseTabCtrl::CalcRectEdit`.)|  
|[CMFCOutlookBarTabCtrl::CanShowFewerPageButtons](#canshowfewerpagebuttons)|Vom Framework aufgerufen, während der größenänderungsvorgängen zu bestimmen, ob weniger Outlook-Leiste Registerkartenschaltflächen angezeigt werden können, als derzeit sichtbar sind.|  
|[CMFCOutlookBarTabCtrl::CanShowMorePageButtons](#canshowmorepagebuttons)|Vom Framework aufgerufen, während der größenänderungsvorgängen zu bestimmen, ob weitere Outlook-Leiste Registerkartenschaltflächen angezeigt werden können, als derzeit sichtbar sind.|  
|[CMFCOutlookBarTabCtrl::Create](#create)|Erstellt das Outlook-Leiste Registerkarten-Steuerelement.|  
|`CMFCOutlookBarTabCtrl::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation)|Gibt an, ob die Animation, die während der Wechsel zwischen Registerkarten active auftritt aktiviert ist.|  
|[CMFCOutlookBarTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|Gibt an, ob ein Benutzer die Bezeichnungen auf die Schaltflächen der Outlook-Leiste auf der Registerkarte ändern kann. (Überschreibt [CMFCBaseTabCtrl::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit).)|  
|[CMFCOutlookBarTabCtrl::EnableScrollButtons](#enablescrollbuttons)|Wird aufgerufen, durch das Framework Schaltflächen "" aktiviert, die den Benutzer einen Bildlauf durch die Schaltflächen in der Outlook-Leistenbereich zu ermöglichen.|  
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|Identifiziert den Bereich, der einen angegebenen Punkt enthält. (Überschreibt [CMFCBaseTabCtrl::FindTargetWnd](../../mfc/reference/cmfcbasetabctrl-class.md#findtargetwnd).)|  
|[CMFCOutlookBarTabCtrl::GetBorderSize](#getbordersize)|Gibt die Rahmengröße des Outlook-Registerkarten-Steuerelements zurück.|  
|`CMFCOutlookBarTabCtrl::GetTabArea`|Ruft die Größe und Position des Registerkartenbereichs des Registerkarten-Steuerelements. (Überschreibt [CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea).)|  
|`CMFCOutlookBarTabCtrl::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMFCOutlookBarTabCtrl::GetVisiblePageButtons](#getvisiblepagebuttons)||  
|[CMFCOutlookBarTabCtrl::IsAnimation](#isanimation)|Bestimmt, ob die Animation, die während der Wechsel zwischen Registerkarten active auftritt aktiviert ist.|  
|[CMFCOutlookBarTabCtrl::IsMode2003](#ismode2003)|Bestimmt, ob das Registerkarten-Steuerelement von Outlook-Leiste in einem Modus ist, die Microsoft Outlook 2003 emuliert.|  
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|Bestimmt, ob ein Punkt innerhalb der Registerkartenbereich befindet. (Überschreibt [CMFCBaseTabCtrl::IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea).)|  
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|Bestimmt, ob eine Registerkarte gelöst werden kann. (Überschreibt [CMFCBaseTabCtrl::IsTabDetachable](../../mfc/reference/cmfcbasetabctrl-class.md#istabdetachable).)|  
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|Vom Framework aufgerufen, wenn eine Registerkarte eingefügt oder entfernt wird. (Überschreibt `CMFCBaseTabCtrl::OnChangeTabs`.)|  
|[CMFCOutlookBarTabCtrl::OnShowFewerPageButtons](#onshowfewerpagebuttons)|Wird aufgerufen, durch das Framework senken die Anzahl von Schaltflächen der Registerkarte "-Seite, die sichtbar sind.|  
|[CMFCOutlookBarTabCtrl::OnShowMorePageButtons](#onshowmorepagebuttons)|Wird aufgerufen, durch das Framework zum Erhöhen der Anzahl der Registerkartenschaltflächen, die sichtbar sind.|  
|[CMFCOutlookBarTabCtrl::OnShowOptions](#onshowoptions)|Zeigt die **Navigationsbereichsoptionen** Dialogfeld.|  
|`CMFCOutlookBarTabCtrl::RecalcLayout`|Berechnet das interne Layout des Registerkarten-Steuerelements an. (Überschreibt [CMFCBaseTabCtrl::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout).)|  
|[CMFCOutlookBarTabCtrl::SetActiveTab](#setactivetab)|Legt die aktive Registerkarte fest. (Überschreibt [CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab).)|  
|[CMFCOutlookBarTabCtrl::SetBorderSize](#setbordersize)|Legt die Rahmengröße des Outlook-Registerkarten-Steuerelements.|  
|[CMFCOutlookBarTabCtrl::SetPageButtonTextAlign](#setpagebuttontextalign)|Legt die Ausrichtung der Beschriftungen für die Schaltflächen der Outlook-Leiste auf der Registerkarte fest.|  
|[CMFCOutlookBarTabCtrl::SetToolbarImageList](#settoolbarimagelist)|Legt die Bitmap, die die Symbole enthält, die am unteren Rand der Outlook-Leiste in Outlook 2003-Modus angezeigt werden (siehe [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)).|  
|[CMFCOutlookBarTabCtrl::SetVisiblePageButtons](#setvisiblepagebuttons)||  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Erstellen, die andockunterstützung hat einer Outlook-Leiste ein `CMFCOutlookBar` -Objekt, das Outlook-Leiste Registerkarten-Steuerelement zu hosten. Weitere Informationen finden Sie unter [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie zum Initialisieren einer `CMFCOutlookBarTabCtrl` -Objekts und die Verwendung verschiedener Methoden in der `CMFCOutlookBarTabCtrl` Klasse. Im Beispiel wird gezeigt, wie zu aktivieren, die direkte Bearbeitung der Beschriftung Text auf Schaltflächen auf der Registerkarte Seite von der Outlook-Leiste, die die Animation aktivieren, Scroll-Handles, die dem Benutzer ermöglichen, über die Schaltflächen in der Outlook-Leistenbereich scrollen, Festlegen der Border Size der Fortsetzung der Outlook-Registerkarte "aktivieren Agentattribute, und legen Sie die Ausrichtung der textbezeichnungen auf Schaltflächen auf der Registerkarte der Outlook-Leiste. Dieser Codeausschnitt ist Teil der [Outlook Demobeispiel](../../visual-cpp-samples.md).  
  
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
 Fügt ein Windows-Steuerelement als neue Registerkarte in der Outlook-Leiste hinzu.  
  
```  
void AddControl(
    CWnd* pWndCtrl,  
    LPCTSTR lpszName,  
    int nImageID=-1,  
    BOOL bDetachable=TRUE,  
    DWORD dwControlBarStyle=AFX_CBRS_FLOAT |  AFX_CBRS_CLOSE | AFX_CBRS_RESIZE |  CBRS_AFX_AUTOHIDE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pWndCtrl*  
 Ein Zeiger auf ein Steuerelement hinzufügen.  
  
 [in] *Wert*  
 Gibt den Namen der Registerkarte ".  
  
 [in] *bDetachable*  
 Wenn `TRUE`, die Seite wird als lösbare erstellt werden.  
  
 [in] *nImageID*  
 Abbildindex in der internen Bildliste für das Bild in der neuen Registerkarte angezeigt werden.  
  
 [in] *DwControlBarStyle*  
 Gibt an, die AFX_ `CBRS_`* Stil für umschlossene andockbare Bereiche.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um ein Steuerelement als neue Seite eines Outlook-Leiste hinzuzufügen.  
  
 Diese Funktion ruft intern auf [:: addTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab).  
  
 Wenn Sie festlegen, *bDetachable* auf `TRUE`, `AddControl` erstellt intern ein `CDockablePaneAdapter` -Objekt und dient als Wrapper für das hinzugefügte Steuerelement. Die Common Language Runtime-Klasse, der dem Fenster im Registerkartenformat automatisch auf die Laufzeitklasse festgelegt `CMFCOutlookBar` und die Common Language Runtime-Klasse des floating Frames in `CMultiPaneFrameWnd`.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `AddControl` Methode in der `CMFCOutlookBarTabCtrl` Klasse. Dieser Codeausschnitt ist Teil der [Outlook Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookDemo#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_3.cpp)]  
  
##  <a name="canshowfewerpagebuttons"></a>  CMFCOutlookBarTabCtrl::CanShowFewerPageButtons  
 Vom Framework aufgerufen, während der größenänderungsvorgänge, um festzustellen, ob weniger Outlook-Leiste Registerkartenschaltflächen angezeigt werden können, als derzeit sichtbar sind.  
  
```  
virtual BOOL CanShowFewerPageButtons() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn mehr als eine Schaltfläche vorhanden ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Outlook-Leiste Registerkarten-Steuerelement wird dynamisch hinzugefügt oder entfernt Registerkarten aus der Anzeige, je nachdem, wie viel Platz verfügbar ist. Diese Methode wird vom Framework verwendet, um diesen Prozess zu unterstützen.  
  
##  <a name="canshowmorepagebuttons"></a>  CMFCOutlookBarTabCtrl::CanShowMorePageButtons  
 Vom Framework aufgerufen, während der größenänderungsvorgänge, um festzustellen, ob weitere Outlook-Leiste Registerkartenschaltflächen angezeigt werden können, als derzeit sichtbar sind.  
  
```  
virtual BOOL CanShowMorePageButtons() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn es befinden sich Schaltflächen, die zurzeit nicht sichtbar sind; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Outlook-Leiste Registerkarten-Steuerelement wird dynamisch hinzugefügt oder entfernt Registerkarten aus der Anzeige, je nachdem, wie viel Platz verfügbar ist. Diese Methode wird vom Framework verwendet, um diesen Prozess zu unterstützen.  
  
##  <a name="create"></a>  CMFCOutlookBarTabCtrl::Create  
 Erstellt das Outlook-Leiste Registerkarten-Steuerelement.  
  
```  
virtual BOOL Create(
    const CRect& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Rect*  
 Gibt die anfängliche Größe und Position in Pixel.  
  
 [in] *pParentWnd*  
 Verweist auf das übergeordnete Fenster. Dieser Wert darf nicht `NULL` sein.  
  
 [in] *nID*  
 Die Steuerelement-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Steuerelement erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel Outlook-Leiste Registerkarten-Steuerelemente werden erstellt, wenn [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md) steuert die WM_DESTROY-Meldung des Prozesses.  
  
##  <a name="enableanimation"></a>  CMFCOutlookBarTabCtrl::EnableAnimation  
 Gibt an, ob die Animation, die während der Wechsel zwischen Registerkarten active auftritt aktiviert ist.  
  
```  
static void EnableAnimation(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bAktivieren*  
 Gibt an, ob die Animation aktiviert oder deaktiviert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Aktivieren und Deaktivieren der Animation. Wenn der Benutzer eine Registerkarte geöffnet wird, wird Beschriftung für den Anzeigezustand der Seite nach oben oder unten aus, wenn die Animation aktiviert ist. Wenn die Animation deaktiviert ist, wird die Seite sofort aktiviert.  
  
 Die Standardeinstellung ist die Animation aktiviert.  
  
##  <a name="enableinplaceedit"></a>  CMFCOutlookBarTabCtrl::EnableInPlaceEdit  
 Gibt an, ob ein Benutzer die Bezeichnungen auf der Registerkartenschaltflächen von der Outlook-Leiste ändern kann.  
  
```  
virtual void EnableInPlaceEdit(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 *bAktivieren*  
 Wenn `TRUE`, aktivieren Sie die direkte Bearbeitung der Beschriftung. Wenn `FALSE`, deaktivieren Sie die direkte Bearbeitung.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Aktivieren oder deaktivieren die direkte Bearbeitung von Bezeichnungen auf der Registerkartenschaltflächen. Die direkte Bearbeitung ist standardmäßig deaktiviert.  
  
##  <a name="enablescrollbuttons"></a>  CMFCOutlookBarTabCtrl::EnableScrollButtons  
 Wird aufgerufen, durch das Framework Scroll-Handles zu aktivieren, die den Benutzer einen Bildlauf durch die Schaltflächen in der Outlook-Leistenbereich zu ermöglichen.  
  
```  
void EnableScrollButtons(
    BOOL bEnable = TRUE,  
    BOOL bIsUp = TRUE,  
    BOOL bIsDown = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bAktivieren*  
 Bestimmt, ob das Scroll-Schaltflächen angezeigt werden.  
  
 [in] *bIsUp*  
 Bestimmt, ob die oberste Bildlaufleiste angezeigt wird.  
  
 [in] *bIsDown*  
 Bestimmt, ob die untere Bildlaufleiste angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
 Ermöglicht die Anzeige der Bildlaufschaltflächen. Diese Methode wird vom Framework aufgerufen, wenn die aktive Registerkarte ändert die Bildlaufschaltflächen wiederherstellen.  
  
##  <a name="getbordersize"></a>  CMFCOutlookBarTabCtrl::GetBorderSize  
 Gibt die Rahmengröße des Outlook-Registerkarten-Steuerelements zurück.  
  
```  
int GetBorderSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe des Rahmens in Pixel.  
  
##  <a name="getvisiblepagebuttons"></a>  CMFCOutlookBarTabCtrl::GetVisiblePageButtons  

  
```  
int GetVisiblePageButtons() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isanimation"></a>  CMFCOutlookBarTabCtrl::IsAnimation  
 Gibt an, ob die Animation, die während der Wechsel zwischen Registerkarten active auftritt aktiviert ist.  
  
```  
static BOOL IsAnimation();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Animation aktiviert ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation) Funktion aktivieren oder Deaktivieren der Animation.  
  
##  <a name="ismode2003"></a>  CMFCOutlookBarTabCtrl::IsMode2003  
 Bestimmt, ob das Registerkarten-Steuerelement von Outlook-Leiste in einem Modus, die Microsoft Outlook 2003 emuliert.  
  
```  
BOOL IsMode2003() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Outlook-Leiste Registerkarten-Steuerelement in Outlook 2003-Modus ist. andernfalls `FALSE`;  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert wird festgelegt, indem [CMFCOutlookBar::SetMode2003](../../mfc/reference/cmfcoutlookbar-class.md#setmode2003).  
  
##  <a name="onshowfewerpagebuttons"></a>  CMFCOutlookBarTabCtrl::OnShowFewerPageButtons  
 Wird aufgerufen, durch das Framework senken die Anzahl von Schaltflächen der Registerkarte "-Seite, die sichtbar sind.  
  
```  
virtual void OnShowFewerPageButtons();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode passt die Anzahl der sichtbaren Seite Registerkartenschaltflächen beim Ändern der Größe des Steuerelements an.  
  
##  <a name="onshowmorepagebuttons"></a>  CMFCOutlookBarTabCtrl::OnShowMorePageButtons  
 Wird aufgerufen, durch das Framework zum Erhöhen der Anzahl der Registerkartenschaltflächen, die sichtbar sind.  
  
```  
virtual void OnShowMorePageButtons();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode passen Sie die Anzahl der Registerkartenschaltflächen, die angezeigt werden, wenn das Steuerelement angepasst wird.  
  
##  <a name="onshowoptions"></a>  CMFCOutlookBarTabCtrl::OnShowOptions  
 Zeigt die **Navigationsbereichsoptionen** (Dialogfeld).  
  
```  
virtual void OnShowOptions();
```  
  
### <a name="remarks"></a>Hinweise  
 Die **Navigationsbereichsoptionen** Dialogfeld ermöglicht dem Benutzer, wählen Sie die Registerkarte Schaltflächen angezeigt werden soll, und die Reihenfolge, in der sie angezeigt werden.  
  
 Diese Methode wird vom Framework aufgerufen, wenn der Benutzer wählt die **Navigationsbereichsoptionen** Menüelement aus dem Steuerelementmenü Anpassung.  
  
##  <a name="setactivetab"></a>  CMFCOutlookBarTabCtrl::SetActiveTab  
 Legt die aktive Registerkarte fest. Die aktive Registerkarte ist dasjenige, das geöffnet, mit dessen Inhalt sichtbar ist.  
  
```  
virtual BOOL SetActiveTab(int iTab);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *iTab*  
 Der nullbasierte Index einer Registerkarte geöffnet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die angegebene Registerkarte erfolgreich geöffnet wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die visuelle Auswirkung der Einstellung der aktiven Registerkarte hängt davon ab, ob Sie die Animation aktiviert haben. Weitere Informationen finden Sie unter [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation).  
  
##  <a name="setbordersize"></a>  CMFCOutlookBarTabCtrl::SetBorderSize  
 Legt die Rahmengröße des Outlook-Registerkarten-Steuerelements.  
  
```  
void SetBorderSize(int nBorderSize);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nBorderSize*  
 Gibt die neue Rahmengröße in Pixel an.  
  
### <a name="remarks"></a>Hinweise  
 Legt die neue Rahmengröße, und das Outlook-Fensterlayout berechnet.  
  
##  <a name="setpagebuttontextalign"></a>  CMFCOutlookBarTabCtrl::SetPageButtonTextAlign  
 Legt die Ausrichtung der Beschriftungen für die Schaltflächen der Outlook-Leiste auf der Registerkarte fest.  
  
```  
void SetPageButtonTextAlign(
    UINT uiAlign,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *UiAlign*  
 Gibt die Ausrichtung des Texts an.  
  
 [in] *bRedraw*  
 Wenn `TRUE`, das Outlook-Fenster wird neu gezeichnet werden.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um die Ausrichtung des Texts für Schaltflächen zu ändern.  
  
 *UiAlign* kann einen der folgenden Werte sein:  
  
|Konstante|Bedeutung|  
|--------------|-------------|  
|TA_LEFT|Linksbündige Ausrichtung|  
|TA_CENTER|zentrierte Ausrichtung|  
|TA_RIGHT|rechtsbündige Ausrichtung|  
  
 Der Standardwert ist TA_CENTER.  
  
##  <a name="settoolbarimagelist"></a>  CMFCOutlookBarTabCtrl::SetToolbarImageList  
 Legt die Bitmap, die die Symbole enthält, die am unteren Rand der Outlook-Leiste in Outlook 2003-Modus angezeigt werden.  
  
```  
BOOL SetToolbarImageList(
    UINT uiID,  
    int cx,  
    COLORREF clrTransp=RGB(255, 0, 255));
```  
  
### <a name="parameters"></a>Parameter  
 [in] *UiID*  
 Gibt die Ressourcen-ID beim Laden des Bilds an.  
  
 [in] *Cx*  
 Gibt die Breite eines Bilds in der Bildliste in Pixel an.  
  
 [in] *ClrTransp*  
 Ein RGB-Wert, der die transparente Farbe angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` Wenn erfolgreich; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion mit einer Bildliste anfügen, deren Bilder auf Symbolleisten-Schaltflächen in Microsoft Office 2003-Modus angezeigt werden. Bild von Indizes sollten Seite Indizes entsprechen.  
  
 Diese Methode sollte nicht im Microsoft Office 2003-Modus nicht aufgerufen werden. Weitere Informationen finden Sie unter [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md).  
  
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
