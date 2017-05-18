---
title: CMFCOutlookBarTabCtrl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CMFCOutlookBarTabCtrl class
ms.assetid: b1f2b3f7-cc59-49a3-99d8-7ff9b37c044b
caps.latest.revision: 26
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 16de4287a2b3a6352fb4fc560b9c8eec2ba766d1
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcoutlookbartabctrl-class"></a>CMFCOutlookBarTabCtrl Class
Ein Registerkarten-Steuerelement mit dem Aussehen des **Navigationsbereichs** in Microsoft Outlook verfügt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCOutlookBarTabCtrl : public CMFCBaseTabCtrl  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCOutlookBarTabCtrl::CMFCOutlookBarTabCtrl`|Standardkonstruktor|  
|`CMFCOutlookBarTabCtrl::~CMFCOutlookBarTabCtrl`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCOutlookBarTabCtrl::AddControl](#addcontrol)|Ein Windows-Steuerelement hinzugefügt als neue Registerkarte in der Outlook-Leiste.|  
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|Vom Framework aufgerufen wird eine Registerkarte, um zu bestimmen, der angezeigt, wenn ein Benutzer die Dimensionen des Bearbeitungsfelds benennt. (Überschreibt `CMFCBaseTabCtrl::CalcRectEdit`.)|  
|[CMFCOutlookBarTabCtrl::CanShowFewerPageButtons](#canshowfewerpagebuttons)|Vom Framework aufgerufen, während der größenänderungsvorgängen bestimmt, ob weniger Outlook-Leiste Registerkartenschaltflächen angezeigt werden können, als derzeit angezeigt werden.|  
|[CMFCOutlookBarTabCtrl::CanShowMorePageButtons](#canshowmorepagebuttons)|Vom Framework aufgerufen, während beim Ändern der Größe Vorgänge zu bestimmen, ob weitere Outlook-Leiste Registerkartenschaltflächen angezeigt werden können, als derzeit angezeigt werden.|  
|[CMFCOutlookBarTabCtrl::Create](#create)|Erstellt die Outlook-Leiste Registerkarten-Steuerelement.|  
|`CMFCOutlookBarTabCtrl::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation)|Gibt an, ob die Animation, die während der Wechsel zwischen aktiven Registerkarten auftritt aktiviert ist.|  
|[CMFCOutlookBarTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|Gibt an, ob ein Benutzer die Beschriftungen auf die Schaltflächen der Outlook-Leiste auf der Registerkarte ändern kann. (Überschreibt [CMFCBaseTabCtrl::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit).)|  
|[CMFCOutlookBarTabCtrl::EnableScrollButtons](#enablescrollbuttons)|Aufgerufen, um Schaltflächen zu ermöglichen, die der Benutzer einen Bildlauf in der Outlook-Leistenbereich Schaltflächen kann.|  
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|Identifiziert den Bereich, der einen angegebenen Punkt enthält. (Überschreibt [CMFCBaseTabCtrl::FindTargetWnd](../../mfc/reference/cmfcbasetabctrl-class.md#findtargetwnd).)|  
|[CMFCOutlookBarTabCtrl::GetBorderSize](#getbordersize)|Gibt die Rahmenstärke des Outlook-Registerkarten-Steuerelements zurück.|  
|`CMFCOutlookBarTabCtrl::GetTabArea`|Ruft die Größe und Position des Registerkartenbereichs des Registerkarten-Steuerelements. (Überschreibt [CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea).)|  
|`CMFCOutlookBarTabCtrl::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|[CMFCOutlookBarTabCtrl::GetVisiblePageButtons](#getvisiblepagebuttons)||  
|[CMFCOutlookBarTabCtrl::IsAnimation](#isanimation)|Bestimmt, ob die Animation, die während der Wechsel zwischen aktiven Registerkarten auftritt aktiviert ist.|  
|[CMFCOutlookBarTabCtrl::IsMode2003](#ismode2003)|Bestimmt, ob das Registerkarten-Steuerelement von Outlook-Leiste in einem Modus, die Microsoft Outlook 2003 emuliert.|  
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|Bestimmt, ob ein Punkt in der Registerkartenbereich ist. (Überschreibt [CMFCBaseTabCtrl::IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea).)|  
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|Bestimmt, ob eine Registerkarte gelöst werden kann. (Überschreibt [CMFCBaseTabCtrl::IsTabDetachable](../../mfc/reference/cmfcbasetabctrl-class.md#istabdetachable).)|  
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|Vom Framework aufgerufen, wenn eine Registerkarte eingefügt oder entfernt werden. (Überschreibt `CMFCBaseTabCtrl::OnChangeTabs`.)|  
|[CMFCOutlookBarTabCtrl::OnShowFewerPageButtons](#onshowfewerpagebuttons)|Aufgerufen, um die Anzahl der Registerkartenschaltflächen zu verringern, die sichtbar sind.|  
|[CMFCOutlookBarTabCtrl::OnShowMorePageButtons](#onshowmorepagebuttons)|Aufgerufen, um die Anzahl der Registerkarte Seitenschaltflächen erhöhen, die sichtbar sind.|  
|[CMFCOutlookBarTabCtrl::OnShowOptions](#onshowoptions)|Zeigt die **Navigationsbereichsoptionen** Dialogfeld.|  
|`CMFCOutlookBarTabCtrl::RecalcLayout`|Berechnet das interne Layout des Registerkarten-Steuerelements. (Überschreibt [CMFCBaseTabCtrl::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout).)|  
|[CMFCOutlookBarTabCtrl::SetActiveTab](#setactivetab)|Legt die aktive Registerkarte fest. (Überschreibt [CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab).)|  
|[CMFCOutlookBarTabCtrl::SetBorderSize](#setbordersize)|Legt die Rahmengröße des Registersteuerelements Outlook.|  
|[CMFCOutlookBarTabCtrl::SetPageButtonTextAlign](#setpagebuttontextalign)|Legt die Ausrichtung der Beschriftungen auf die Schaltflächen der Outlook-Leiste auf der Registerkarte fest.|  
|[CMFCOutlookBarTabCtrl::SetToolbarImageList](#settoolbarimagelist)|Legt die Bitmap, die die Symbole enthält, die am unteren Rand der Outlook-Leiste in Outlook 2003-Modus angezeigt werden (siehe [CMFCOutlookBar Class](../../mfc/reference/cmfcoutlookbar-class.md)).|  
|[CMFCOutlookBarTabCtrl::SetVisiblePageButtons](#setvisiblepagebuttons)||  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Erstellen einer Outlook-Leiste, das Andocken unterstützt ein `CMFCOutlookBar` Objekt, das die Outlook-Leiste Registerkarten-Steuerelement zu hosten. Weitere Informationen finden Sie unter [CMFCOutlookBar Class](../../mfc/reference/cmfcoutlookbar-class.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie zum Initialisieren einer `CMFCOutlookBarTabCtrl` Objekt, und verwenden Sie verschiedene Methoden in der `CMFCOutlookBarTabCtrl` Klasse. Veranschaulicht, wie die direkte Bearbeitung der Beschriftung auf der Registerkartenschaltflächen der Outlook-Leiste zu aktivieren, aktivieren die Animation, aktivieren Sie Scroll-Handles, die dem Benutzer ermöglichen, blättern Sie durch die Schaltflächen auf der Outlook-Leistenbereich fest, die Rahmengröße des Outlook-Registerkarten-Steuerelement, und die Ausrichtung der Beschriftungen auf die Schaltflächen der Outlook-Leiste auf der Registerkarte. Dieser Codeausschnitt ist Teil der [Outlook Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookDemo&#1;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_1.cpp)]  
[!code-cpp[NVC_MFC_OutlookDemo&#2;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxoutlookbartabctrl.h  
  
##  <a name="addcontrol"></a>CMFCOutlookBarTabCtrl::AddControl  
 Ein Windows-Steuerelement hinzugefügt als neue Registerkarte in der Outlook-Leiste.  
  
```  
void AddControl(
    CWnd* pWndCtrl,  
    LPCTSTR lpszName,  
    int nImageID=-1,  
    BOOL bDetachable=TRUE,  
    DWORD dwControlBarStyle=AFX_CBRS_FLOAT |  AFX_CBRS_CLOSE | AFX_CBRS_RESIZE |  CBRS_AFX_AUTOHIDE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndCtrl`  
 Ein Zeiger auf ein Steuerelement hinzufügen.  
  
 [in] `lpszName`  
 Gibt den Namen der Registerkarte.  
  
 [in] `bDetachable`  
 Wenn `TRUE`, die Seite wird als entfernbare erstellt.  
  
 [in] `nImageID`  
 Image-Index in der Liste der internen Images für das Bild in der neuen Registerkarte angezeigt werden.  
  
 [in] `dwControlBarStyle`  
 Gibt die AFX_ `CBRS_`* Style für umschlossene andockbare Bereiche.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um ein Steuerelement hinzufügen, wenn eine neue Seite mit einer Outlook-Leiste.  
  
 Diese Funktion ruft intern auf [:: addTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab).  
  
 Wenn Sie festlegen, `bDetachable` auf `TRUE`, `AddControl` erstellt intern ein `CDockablePaneAdapter` -Objekt und umschließt das hinzugefügte Steuerelement. Automatisch wird die Common Language Runtime-Klasse, der dem Fenster im Registerkartenformat auf die Common Language Runtime-Klasse der `CMFCOutlookBar` und die Common Language Runtime-Klasse des frei verschiebbaren Frames in `CMultiPaneFrameWnd`.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `AddControl` -Methode in der `CMFCOutlookBarTabCtrl` Klasse. Dieser Codeausschnitt ist Teil der [Outlook Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookDemo&3;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_3.cpp)]  
  
##  <a name="canshowfewerpagebuttons"></a>CMFCOutlookBarTabCtrl::CanShowFewerPageButtons  
 Vom Framework aufgerufen, bei der Vorgänge, um festzustellen, ob weniger Outlook-Leiste Registerkartenschaltflächen angezeigt werden können, als derzeit angezeigt werden.  
  
```  
virtual BOOL CanShowFewerPageButtons() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn es mehr als eine Schaltfläche; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Outlook-Leiste Registerkarten-Steuerelement wird dynamisch hinzugefügt oder entfernt Registerkarten aus der Anzeige, je nachdem, wie viel freier Speicherplatz verfügbar ist. Diese Methode wird vom Framework verwendet, um in diesem Prozess zu unterstützen.  
  
##  <a name="canshowmorepagebuttons"></a>CMFCOutlookBarTabCtrl::CanShowMorePageButtons  
 Vom Framework aufgerufen, bei der Vorgänge aus, um zu bestimmen, ob weitere Outlook-Leiste Registerkartenschaltflächen angezeigt werden können, als derzeit angezeigt werden.  
  
```  
virtual BOOL CanShowMorePageButtons() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn es Schaltflächen, die zurzeit nicht sichtbar sind sind. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Outlook-Leiste Registerkarten-Steuerelement wird dynamisch hinzugefügt oder entfernt Registerkarten aus der Anzeige, je nachdem, wie viel freier Speicherplatz verfügbar ist. Diese Methode wird vom Framework verwendet, um in diesem Prozess zu unterstützen.  
  
##  <a name="create"></a>CMFCOutlookBarTabCtrl::Create  
 Erstellt die Outlook-Leiste Registerkarten-Steuerelement.  
  
```  
virtual BOOL Create(
    const CRect& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rect`  
 Gibt die anfängliche Größe und Position in Pixel.  
  
 [in] `pParentWnd`  
 Verweist auf das übergeordnete Fenster. Dieser Wert darf nicht `NULL` sein.  
  
 [in] `nID`  
 Die Steuerelement-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Steuerelement erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel Outlook-Leiste Registerkarten-Steuerelemente werden erstellt, wenn [CMFCOutlookBar Class](../../mfc/reference/cmfcoutlookbar-class.md) Steuerelemente der `WM_CREATE` Nachricht des Prozesses.  
  
##  <a name="enableanimation"></a>CMFCOutlookBarTabCtrl::EnableAnimation  
 Gibt an, ob die Animation, die während der Wechsel zwischen aktiven Registerkarten auftritt aktiviert ist.  
  
```  
static void EnableAnimation(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 Gibt an, ob die Animation aktiviert oder deaktiviert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion aktivieren und Deaktivieren von Animationen. Wenn der Benutzer eine Seite mit Registerkarten geöffnet wird, Folien Beschriftung der Seite nach oben oder unten, wenn die Animation aktiviert ist. Wenn die Animation deaktiviert ist, wird die Seite sofort aktiviert.  
  
 Die Standardeinstellung ist die Animation aktiviert.  
  
##  <a name="enableinplaceedit"></a>CMFCOutlookBarTabCtrl::EnableInPlaceEdit  
 Gibt an, ob ein Benutzer die Beschriftungen auf der Registerkartenschaltflächen der Outlook-Leiste ändern kann.  
  
```  
virtual void EnableInPlaceEdit(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 `bEnable`  
 Wenn `TRUE`, aktivieren Sie die direkte Bearbeitung der Beschriftung. Wenn `FALSE`, deaktivieren Sie die direkte Bearbeitung.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion aktivieren oder deaktivieren die direkte Bearbeitung von textbezeichnungen, die auf der Registerkartenschaltflächen. Die direkte Bearbeitung ist standardmäßig deaktiviert.  
  
##  <a name="enablescrollbuttons"></a>CMFCOutlookBarTabCtrl::EnableScrollButtons  
 Vom Framework aufgerufen Scroll-Handles zu aktivieren, die über Schaltflächen in der Outlook-Leistenbereich Bildlauf zu ermöglichen.  
  
```  
void EnableScrollButtons(
    BOOL bEnable = TRUE,  
    BOOL bIsUp = TRUE,  
    BOOL bIsDown = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 Bestimmt, ob die Bildlaufschaltflächen angezeigt werden.  
  
 [in] `bIsUp`  
 Bestimmt, ob die obere Bildlaufleiste angezeigt wird.  
  
 [in] `bIsDown`  
 Bestimmt, ob die Bildlaufleiste unten angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
 Ermöglicht die Anzeige der Bildlaufschaltflächen. Diese Methode wird vom Framework aufgerufen, wenn die aktive Registerkarte ändert die Bildlaufschaltflächen wiederherstellen.  
  
##  <a name="getbordersize"></a>CMFCOutlookBarTabCtrl::GetBorderSize  
 Gibt die Rahmenstärke des Outlook-Registerkarten-Steuerelements zurück.  
  
```  
int GetBorderSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Rahmengröße in Pixel.  
  
##  <a name="getvisiblepagebuttons"></a>CMFCOutlookBarTabCtrl::GetVisiblePageButtons  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetVisiblePageButtons() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isanimation"></a>CMFCOutlookBarTabCtrl::IsAnimation  
 Gibt an, ob die Animation, die während der Wechsel zwischen aktiven Registerkarten auftritt aktiviert ist.  
  
```  
static BOOL IsAnimation();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Animation aktiviert ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation) Funktion aktivieren oder Deaktivieren der Animation.  
  
##  <a name="ismode2003"></a>CMFCOutlookBarTabCtrl::IsMode2003  
 Bestimmt, ob das Registerkarten-Steuerelement von Outlook-Leiste in einem Modus, die Microsoft Outlook 2003 emuliert.  
  
```  
BOOL IsMode2003() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Outlook-Leiste Registerkarten-Steuerelement in Outlook 2003-Modus ist. andernfalls `FALSE`;  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert wird festgelegt, indem [CMFCOutlookBar::SetMode2003](../../mfc/reference/cmfcoutlookbar-class.md#setmode2003).  
  
##  <a name="onshowfewerpagebuttons"></a>CMFCOutlookBarTabCtrl::OnShowFewerPageButtons  
 Aufgerufen, um die Anzahl der Registerkartenschaltflächen zu verringern, die sichtbar sind.  
  
```  
virtual void OnShowFewerPageButtons();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode passt die Anzahl der sichtbaren Seite Registerkartenschaltflächen des Steuerelements geändert wird.  
  
##  <a name="onshowmorepagebuttons"></a>CMFCOutlookBarTabCtrl::OnShowMorePageButtons  
 Aufgerufen, um die Anzahl der Registerkarte Seitenschaltflächen erhöhen, die sichtbar sind.  
  
```  
virtual void OnShowMorePageButtons();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode passen Sie die Anzahl der Registerkartenschaltflächen, die angezeigt werden, wenn die Größe des Steuerelements geändert wird.  
  
##  <a name="onshowoptions"></a>CMFCOutlookBarTabCtrl::OnShowOptions  
 Zeigt die **Navigationsbereichsoptionen** Dialogfeld.  
  
```  
virtual void OnShowOptions();
```  
  
### <a name="remarks"></a>Hinweise  
 Die **Navigationsbereichsoptionen** Dialogfeld kann der Benutzer auswählen, welche Registerkarte Schaltflächen angezeigt werden sollen, und die Reihenfolge, in der sie angezeigt werden.  
  
 Diese Methode wird vom Framework aufgerufen, wenn der Benutzer wählt die **Navigationsbereichsoptionen** Menüelement Menü Anpassung des Steuerelements.  
  
##  <a name="setactivetab"></a>CMFCOutlookBarTabCtrl::SetActiveTab  
 Legt die aktive Registerkarte fest. Die aktive Registerkarte wird geöffnet, mit dessen Inhalt sichtbar ist.  
  
```  
virtual BOOL SetActiveTab(int iTab);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iTab`  
 Der nullbasierte Index einer Registerkarte geöffnet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die angegebene Registerkarte erfolgreich geöffnet wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Der visuelle Effekt der aktive Registerkarte festlegen, hängt davon ab, ob Sie die Animation aktiviert haben. Weitere Informationen finden Sie unter [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation).  
  
##  <a name="setbordersize"></a>CMFCOutlookBarTabCtrl::SetBorderSize  
 Legt die Rahmengröße des Registersteuerelements Outlook.  
  
```  
void SetBorderSize(int nBorderSize);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nBorderSize`  
 Gibt die neue Rahmengröße in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Legt die neue Rahmengröße, und berechnet das Layout der Outlook-Fenster.  
  
##  <a name="setpagebuttontextalign"></a>CMFCOutlookBarTabCtrl::SetPageButtonTextAlign  
 Legt die Ausrichtung der Beschriftungen auf die Schaltflächen der Outlook-Leiste auf der Registerkarte fest.  
  
```  
void SetPageButtonTextAlign(
    UINT uiAlign,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiAlign`  
 Gibt die Ausrichtung des Texts an.  
  
 [in] `bRedraw`  
 Wenn `TRUE`, wird das Outlook-Fenster neu gezeichnet werden.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion zum Ändern der textausrichtung für die Schaltflächen.  
  
 `uiAlign`die folgenden Werte sind möglich:  
  
|Konstante|Bedeutung|  
|--------------|-------------|  
|TA_LEFT|Linksbündige Ausrichtung|  
|TA_CENTER|Zentrierte Ausrichtung|  
|TA_RIGHT|Rechtsbündig|  
  
 Der Standardwert ist TA_CENTER.  
  
##  <a name="settoolbarimagelist"></a>CMFCOutlookBarTabCtrl::SetToolbarImageList  
 Legt die Bitmap, die die Symbole enthält, die am unteren Rand der Outlook-Leiste in Outlook 2003-Modus angezeigt werden.  
  
```  
BOOL SetToolbarImageList(
    UINT uiID,  
    int cx,  
    COLORREF clrTransp=RGB(255, 0, 255));
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiID`  
 Gibt die Ressourcen-ID des Bilds zu laden.  
  
 [in] `cx`  
 Gibt die Breite eines Bilds in der Bildliste in Pixel an.  
  
 [in] `clrTransp`  
 RGB-Wert, der die transparente Farbe angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` Wenn erfolgreich, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion mit einer Bildliste anfügen, deren Bilder auf Symbolleisten-Schaltflächen in Microsoft Office 2003-Modus angezeigt werden. Image-Indizes sollten Seite Indizes entsprechen.  
  
 Diese Methode sollte nicht im Microsoft Office 2003-Modus nicht aufgerufen werden. Weitere Informationen finden Sie unter [CMFCOutlookBar Class](../../mfc/reference/cmfcoutlookbar-class.md).  
  
##  <a name="setvisiblepagebuttons"></a>CMFCOutlookBarTabCtrl::SetVisiblePageButtons  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetVisiblePageButtons(int nVisiblePageButtons);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nVisiblePageButtons`  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCBaseTabCtrl-Klasse](../../mfc/reference/cmfcbasetabctrl-class.md)   
 [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCOutlookBarPane-Klasse](../../mfc/reference/cmfcoutlookbarpane-class.md)

