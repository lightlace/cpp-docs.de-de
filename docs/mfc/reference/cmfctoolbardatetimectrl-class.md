---
title: CMFCToolBarDateTimeCtrl Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CanBeStretched
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CopyFrom
- AFXTOOLBARDATETIMECTRL/CMFCToolBarButton::ExportToMenuButton
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetByCmd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetHwnd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetTime
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetTimeAll
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::HaveHotBorder
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::NotifyCommand
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnAddToCustomizePage
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnChangeParentWnd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnClick
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnCtlColor
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnMove
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnShow
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnUpdateToolTip
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::SetTime
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::SetTimeAll
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarDateTimeCtrl [MFC], CMFCToolBarDateTimeCtrl
- CMFCToolBarDateTimeCtrl [MFC], CanBeStretched
- CMFCToolBarDateTimeCtrl [MFC], CopyFrom
- CMFCToolBarButton [MFC], ExportToMenuButton
- CMFCToolBarDateTimeCtrl [MFC], GetByCmd
- CMFCToolBarDateTimeCtrl [MFC], GetDateTimeCtrl
- CMFCToolBarDateTimeCtrl [MFC], GetHwnd
- CMFCToolBarDateTimeCtrl [MFC], GetTime
- CMFCToolBarDateTimeCtrl [MFC], GetTimeAll
- CMFCToolBarDateTimeCtrl [MFC], HaveHotBorder
- CMFCToolBarDateTimeCtrl [MFC], NotifyCommand
- CMFCToolBarDateTimeCtrl [MFC], OnAddToCustomizePage
- CMFCToolBarDateTimeCtrl [MFC], OnChangeParentWnd
- CMFCToolBarDateTimeCtrl [MFC], OnClick
- CMFCToolBarDateTimeCtrl [MFC], OnCtlColor
- CMFCToolBarDateTimeCtrl [MFC], OnGlobalFontsChanged
- CMFCToolBarDateTimeCtrl [MFC], OnMove
- CMFCToolBarDateTimeCtrl [MFC], OnShow
- CMFCToolBarDateTimeCtrl [MFC], OnUpdateToolTip
- CMFCToolBarDateTimeCtrl [MFC], SetTime
- CMFCToolBarDateTimeCtrl [MFC], SetTimeAll
ms.assetid: a3853cb9-8ebc-444f-a1e4-9cf905e24c18
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 340f9f698d63587b7a3812d5922d8963c87751ee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376791"
---
# <a name="cmfctoolbardatetimectrl-class"></a>CMFCToolBarDateTimeCtrl-Klasse
Eine Symbolleisten-Schaltfläche, die ein Datums- und Zeitauswahl-Steuerelement enthält.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCToolBarDateTimeCtrl : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl](#cmfctoolbardatetimectrl)|Erstellt ein `CMFCToolBarDateTimeCtrl`-Objekt.|  
|`CMFCToolBarDateTimeCtrl::~CMFCToolBarDateTimeCtrl`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarDateTimeCtrl::CanBeStretched](#canbestretched)|Gibt an, ob ein Benutzer die Schaltfläche mit den während der Anpassung gestreckt werden kann. (Überschreibt [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|  
|[CMFCToolBarDateTimeCtrl::CopyFrom](#copyfrom)|Kopiert die Eigenschaften von einer anderen Symbolleistenschaltfläche auf die Schaltfläche mit den aktuellen. (Überschreibt [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|`CMFCToolBarDateTimeCtrl::DuplicateData`|Für zukünftige Verwendung reserviert.|  
|[CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)|Kopiert den Text aus der Symbolleiste auf die Schaltfläche zu einem Menü.|  
|`CMFCToolBarDateTimeCtrl::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCToolBarDateTimeCtrl::GetByCmd](#getbycmd)|Ruft das erste `CMFCToolBarDateTimeCtrl` Objekt in der Anwendung mit der angegebenen Befehls-ID.|  
|[CMFCToolBarDateTimeCtrl::GetDateTimeCtrl](#getdatetimectrl)|Gibt einen Zeiger auf die Datums- / Zeitauswahl-Steuerelement.|  
|[CMFCToolBarDateTimeCtrl::GetHwnd](#gethwnd)|Ruft das Fensterhandle, das die Symbolleisten-Schaltfläche zugeordnet ist. (Überschreibt [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|  
|`CMFCToolBarDateTimeCtrl::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMFCToolBarDateTimeCtrl::GetTime](#gettime)|Ruft den ausgewählten Zeitpunkt über ein Datum und Uhrzeit Kontoauswahl-Steuerelement ab und fügt sie in einem angegebenen [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur.|  
|[CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall)|Gibt die ausgewählte Zeit über die Zeit Zeitauswahl-Steuerelement-Schaltfläche, die eine angegebenen Befehls-ID wurde|  
|[CMFCToolBarDateTimeCtrl::HaveHotBorder](#havehotborder)|Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer die Schaltfläche auswählt. (Überschreibt [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|  
|[CMFCToolBarDateTimeCtrl::NotifyCommand](#notifycommand)|Gibt an, ob die Schaltfläche verarbeitet die [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachricht. (Überschreibt [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|  
|[CMFCToolBarDateTimeCtrl::OnAddToCustomizePage](#onaddtocustomizepage)|Vom Framework aufgerufen, wenn die Schaltfläche "" hinzugefügt wird eine **anpassen** (Dialogfeld). (Überschreibt [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|  
|`CMFCToolBarDateTimeCtrl::OnCalculateSize`|Wird aufgerufen, durch das Framework die Größe der Schaltfläche für den angegebenen Gerätekontext und andockzustand berechnet. (Überschreibt [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|[CMFCToolBarDateTimeCtrl::OnChangeParentWnd](#onchangeparentwnd)|Vom Framework aufgerufen, wenn die Schaltfläche "" in eine neue Symbolleiste eingefügt wird. (Überschreibt [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCToolBarDateTimeCtrl::OnClick](#onclick)|Vom Framework aufgerufen, wenn der Benutzer das Steuerelement klickt. (Überschreibt [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCToolBarDateTimeCtrl::OnCtlColor](#onctlcolor)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste verarbeitet eine `WM_CTLCOLOR` Nachricht. (Überschreibt [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|  
|`CMFCToolBarDateTimeCtrl::OnDraw`|Wird aufgerufen, durch das Framework der Schaltfläche gezeichnet werden soll, mithilfe des angegebenen Stile und Optionen. (Überschreibt [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|`CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList`|Wird aufgerufen, durch das Framework der Schaltfläche gezeichnet werden soll, der **Befehle** im Bereich der **anpassen** (Dialogfeld). (Überschreibt [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged](#onglobalfontschanged)|Vom Framework aufgerufen, wenn die globale Schriftart geändert hat. (Überschreibt [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|  
|[CMFCToolBarDateTimeCtrl::OnMove](#onmove)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste bewegt wird. (Überschreibt [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|  
|[CMFCToolBarDateTimeCtrl::OnShow](#onshow)|Vom Framework aufgerufen, wenn die Schaltfläche wird ein- oder ausgeblendet. (Überschreibt [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|  
|`CMFCToolBarDateTimeCtrl::OnSize`|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste seine Größe ändert oder Position und diese Änderung bewirkt, dass die Schaltfläche, um die Größe zu ändern. (Überschreibt [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|  
|[CMFCToolBarDateTimeCtrl::OnUpdateToolTip](#onupdatetooltip)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste die QuickInfo-Text aktualisiert. (Überschreibt [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|  
|`CMFCToolBarDateTimeCtrl::Serialize`|Dieses Objekt aus einem Archiv liest oder schreibt sie in ein Archiv (Außerkraftsetzungen [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|`CMFCToolBarDateTimeCtrl::SetStyle`|Legt den Stil der Symbolleisten-Schaltfläche. (Überschreibt [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|  
|[CMFCToolBarDateTimeCtrl::SetTime](#settime)|Legt das Datum und die in der / Zeitauswahl-Steuerelement fest.|  
|[CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall)|Legt das Datum und die in allen Instanzen der / Zeitauswahl-Steuerelement mit einer angegebenen Befehls-ID.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Beispiel zum Verwenden eines Datumsauswahl Datum und Uhrzeit finden Sie das Beispielprojekt ToolbarDateTimePicker. Informationen zur Vorgehensweise beim Hinzufügen von Schaltflächen in Symbolleisten finden Sie unter [Exemplarische Vorgehensweise: Einfügen von Steuerelementen auf Symbolleisten](../../mfc/walkthrough-putting-controls-on-toolbars.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtoolbardatetimectrl.h  
  
##  <a name="canbestretched"></a>  CMFCToolBarDateTimeCtrl::CanBeStretched  
 Gibt an, ob ein Benutzer die Schaltfläche mit den während der Anpassung gestreckt werden kann.  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig lässt das Framework nicht den Benutzer, eine Symbolleisten-Schaltfläche während der Anpassung zu Strecken. Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)) indem der Benutzer, eine Symbolleisten-Schaltfläche für Datum und Uhrzeit während der Anpassung zu Strecken.  
  
##  <a name="cmfctoolbardatetimectrl"></a>  CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl  
 Erstellt und initialisiert ein [CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md) Objekt.  
  
```  
CMFCToolBarDateTimeCtrl(
    UINT uiID,  
    int iImage,  
    DWORD dwStyle=0,  
    int iWidth=0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiID`  
 Die Steuerelement-ID.  
  
 [in] `iImage`  
 Der Index des Bilds in der Symbolleiste `CMFCToolBarImages` Objekt.  
  
 [in] `dwStyle`  
 Die Art des der `CMFCToolBarDateTimeCtrlImpl` Fenster, das erstellt wird, wenn ein Benutzer auf die Schaltfläche klickt.  
  
 [in] `iWidth`  
 Die Breite des Steuerelements in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Objekt wird mit dem Systemdatum und Systemzeit initialisiert. Der Fensterstil des internen `CMFCToolBarDateTimeCtrlImpl` Objekt enthält die `dwStyle` Parameter und die `WS_CHILD` und `WS_VISIBLE` Stile. Sie können mit dieser Stile ändern `CMFCToolBarDateTimeCtrl::SetStyle`. Verwendung `SetStyle` so ändern Sie den Stil der `CMFCToolBarDateTimeCtrl` Steuerelement.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen von ein Objekt von der `CMFCToolBarDateTimeCtrl` Klasse. Dieser Codeausschnitt ist Teil der [Symbolleiste Datums-/Zeitauswahl-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_ToolbarDateTimePicker#1](../../mfc/reference/codesnippet/cpp/cmfctoolbardatetimectrl-class_1.cpp)]  
  
##  <a name="copyfrom"></a>  CMFCToolBarDateTimeCtrl::CopyFrom  
 Kopiert die Eigenschaften von einer anderen Symbolleistenschaltfläche auf die Schaltfläche mit den aktuellen.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `src`  
 Ein Verweis auf die Schaltfläche "Quelle" aus dem kopiert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Kopieren von einer anderen Symbolleistenschaltfläche diese Symbolleisten-Schaltfläche. `src` muss vom Typ `CMFCToolBarDateTimeCtrl`.  
  
##  <a name="exporttomenubutton"></a>  CMFCToolBarDateTimeCtrl::ExportToMenuButton  
 Kopiert den Text aus der Symbolleiste auf die Schaltfläche zu einem Menü.  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `menuButton`  
 Ein Verweis auf die Menüschaltfläche Ziel.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die basisklassenimplementierung ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) durch das Laden der Zeichenfolgenressource, die die Befehls-ID des Steuerelements zugeordnet ist. Weitere Informationen zu den Zeichenfolgenressourcen, finden Sie unter [CStringT::LoadString](../../atl-mfc-shared/reference/cstringt-class.md#loadstring).  
  
##  <a name="getbycmd"></a>  CMFCToolBarDateTimeCtrl::GetByCmd  
 Ruft das erste `CMFCToolBarDateTimeCtrl` Objekt in der Anwendung mit der angegebenen Befehls-ID.  
  
```  
static CMFCToolBarDateTimeCtrl* __stdcall GetByCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die Befehls-ID der Schaltfläche abgerufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste `CMFCToolBarDateTimeCtrl` Objekt in der Anwendung mit der angegebenen Befehls-ID oder `NULL` kein `CMFCToolBarDateTimeCtrl` Objekte verfügen über die angegebene Befehls-ID.  
  
### <a name="remarks"></a>Hinweise  
 Diese freigegebenen Utility-Methode wird von Methoden verwendet, z. B. [CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall) und [CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall) festgelegt oder abgerufen werden, das Datum und die Zeit aller Instanzen die Datumsauswahl denen eine angegebene Befehls-ID.  
  
##  <a name="getdatetimectrl"></a>  CMFCToolBarDateTimeCtrl::GetDateTimeCtrl  
 Gibt einen Zeiger auf die Datums- / Zeitauswahl-Steuerelement.  
  
```  
CDateTimeCtrl* GetDateTimeCtrl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf Datums- und Zeitauswahl; oder `NULL` ist das Steuerelement ist nicht vorhanden.  
  
### <a name="remarks"></a>Hinweise  
 Die `CMFCToolBarDateTimeCtrl` -Klasse initialisiert die `m_pWndDateTime` Datenmember, die beim Einfügen einer `CMFCToolBarDateTimeCtrl` Objekt in eine Symbolleiste.  
  
##  <a name="gethwnd"></a>  CMFCToolBarDateTimeCtrl::GetHwnd  
 Ruft das Fensterhandle, das die Symbolleisten-Schaltfläche zugeordnet ist.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Fensterhandle, das das Datum und Uhrzeit Symbolleisten-Schaltfläche zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) Methode.  
  
##  <a name="gettime"></a>  CMFCToolBarDateTimeCtrl::GetTime  
 Ruft die ausgewählte Zeit aus der zugeordneten Datum und Zeit Kontoauswahl-Steuerelement ab und fügt sie in einem angegebenen [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur  
  
```  
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `[out] timeDest`  
 In der ersten Überladung eine [COleDateTime Klasse](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, das die Zeitinformationen System erhält. In der zweiten Überladung ist ein [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das die Zeitinformationen System erhält.  
  
 `[out] pTimeDest`  
 Ein Zeiger auf die [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, um die Systeminformationen für die Zeit zu erhalten. Dieser Wert darf nicht `NULL` sein.  
  
### <a name="return-value"></a>Rückgabewert  
 In der ersten Überladung, die ungleich NULL, wenn die Zeit in erfolgreich geschrieben werden die [COleDateTime Klasse](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, andernfalls 0. In der zweiten und dritten Überladungen der Rückgabewert ist eine `DWORD` , die gleich der DwFlag-Member, die festgelegt wurde, in der [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Die-Methode legt die [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) Struktur DwFlags Member, um anzugeben, ob die Datums- / Zeitauswahl auf einer Datums- und Uhrzeitangabe festgelegt ist. Wenn der Wert der GDT_NONE wird das Steuerelement festzulegen, um `no date` Status, und verwendet den DTS_SHOWNONE-Stil. Wenn der zurückgegebene Wert GDT_VALID entspricht, wird die Systemzeit wurde erfolgreich am Zielspeicherort gespeichert.  
  
##  <a name="gettimeall"></a>  CMFCToolBarDateTimeCtrl::GetTimeAll  
 Gibt die Zeit, die vom Benutzer über die Zeit Zeitauswahl-Steuerelement-Schaltfläche, die eine angegebenen Befehls-ID wurde aktiviert  
  
```  
static BOOL GetTimeAll(
    UINT uiCmd,  
    COleDateTime& timeDest);

static DWORD GetTimeAll(
    UINT uiCmd,  
    CTime& timeDest);

static DWORD GetTimeAll(
    UINT uiCmd,  
    LPSYSTEMTIME pTimeDest);
```  
  
### <a name="parameters"></a>Parameter  
 `[in] uiCmd`  
 Gibt an, eine Symbolleisten-Befehlsschaltfläche-ID.  
  
 `[out] timeDest`  
 In der ersten Überladung eine [COleDateTime Klasse](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, das die Zeitinformationen System erhält. In der zweiten Überladung ist ein [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das die Zeitinformationen System erhält.  
  
 `[out] pTimeDest`  
 Ein Zeiger auf die [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, um die Systeminformationen für die Zeit zu erhalten. Dieser Wert darf nicht `NULL` sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn das Framework eine Symbolleisten-Schaltfläche nicht finden kann, die die Befehls-ID entspricht `uiCmd`, der Rückgabewert ist 0 (null), in der ersten Überladung und GDT_NONE in der anderen Überladungen. Wenn die Symbolleistenschaltfläche gefunden wird, wird der Rückgabewert ist identisch mit der Rückgabewert eines Aufrufs [CMFCToolBarDateTimeCtrl::GetTime](#gettime) auf diese Schaltfläche. Ein Rückgabewert Wert 0 (null) oder GDT_NONE kann auftreten, wenn die Schaltfläche "" gefunden wird, der angibt, dass der Aufruf von `GetTime` hat ein gültiges Datum in einem anderen Grund nicht zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sucht nach einer Symbolleisten-Schaltfläche mit dem angegebenen Befehls-ID und Aufrufe [CMFCToolBarDateTimeCtrl::GetTime](#gettime) Methode auf die Schaltfläche.  
  
##  <a name="havehotborder"></a>  CMFCToolBarDateTimeCtrl::HaveHotBorder  
 Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer die Schaltfläche auswählt.  
  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn eine Schaltfläche eine Rahmenlinie beim aktiviert angezeigt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt einen Wert ungleich NULL zurück, wenn das Steuerelement sichtbar ist.  
  
##  <a name="notifycommand"></a>  CMFCToolBarDateTimeCtrl::NotifyCommand  
 Gibt an, ob die Schaltfläche verarbeitet die [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachricht.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iNotifyCode`  
 Die Benachrichtigung, die dem Befehl zugeordnet ist.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die Taste verarbeitet die `WM_COMMAND` Nachricht oder `FALSE` um anzugeben, dass die Nachricht vom übergeordneten Symbolleiste behandelt werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode aus, wenn es zu senden ist ein [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachricht an das übergeordnete Fenster.  
  
 Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) durch die Verarbeitung der [DTN_DATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761737) Benachrichtigung. Den interne Status aktualisiert und aktualisiert die Time-Eigenschaft aller `CMFCToolBarDateTimeCtrl` Objekte mit dem gleichen Befehl ID.  
  
##  <a name="onaddtocustomizepage"></a>  CMFCToolBarDateTimeCtrl::OnAddToCustomizePage  
 Vom Framework aufgerufen, wenn die Schaltfläche "" hinzugefügt wird eine **anpassen** (Dialogfeld).  
  
```  
virtual void OnAddToCustomizePage();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die basisklassenimplementierung [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage), durch Kopieren Sie die Eigenschaften des ersten Datums und die Uhrzeit des Steuerelements in eine Symbolleiste, die derselben Befehls-ID wie dieses Objekt verfügt. Diese Methode bewirkt nichts, wenn keine Symbolleiste ein Steuerelements für Datum und Uhrzeit, das mit derselben Befehls-ID wie dieses Objekt besitzt.  
  
 Weitere Informationen zu den **anpassen** (Dialogfeld), finden Sie unter [CMFCToolBarsCustomizeDialog Klasse](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).  
  
##  <a name="onchangeparentwnd"></a>  CMFCToolBarDateTimeCtrl::OnChangeParentWnd  
 Vom Framework aufgerufen, wenn die Schaltfläche "" in eine neue Symbolleiste eingefügt wird.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
 Das neue übergeordnete Fenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die basisklassenimplementierung ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) durch das interne Neuerstellen `CMFCToolBarDateTimeCtrlImpl` Objekt.  
  
##  <a name="onclick"></a>  CMFCToolBarDateTimeCtrl::OnClick  
 Vom Framework aufgerufen, wenn der Benutzer das Steuerelement klickt.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Nicht verwendet.  
  
 [in] `bDelay`  
 Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Schaltfläche, die auf-Nachricht verarbeitet; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die basisklassenimplementierung [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), durch einen Wert ungleich NULL zurückgeben, wenn das interne `CMFCToolBarDateTimeCtrlImpl` -Objekts sichtbar ist.  
  
##  <a name="onctlcolor"></a>  CMFCToolBarDateTimeCtrl::OnCtlColor  
 Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste verarbeitet eine `WM_CTLCOLOR` Nachricht.  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Der Gerätekontext, in dem die Schaltfläche angezeigt.  
  
 [in] `nCtlColor`  
 Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für den globalen Pinsel, den das Framework verwendet, um den Hintergrund der Schaltfläche zu zeichnen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die basisklassenimplementierung [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)durch Festlegen des Texts und Hintergrundfarben des Gerätekontexts bereitgestellten auf den globalen Text und Hintergrundfarben, bzw.  
  
 Weitere Informationen zu globalen Optionen, die für Ihre Anwendung verfügbar sind, finden Sie unter [AFX_GLOBAL_DATA-Struktur](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="onglobalfontschanged"></a>  CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged  
 Vom Framework aufgerufen, wenn die globale Schriftart geändert hat.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) durch Ändern der Schriftart des Steuerelements mit der globalen Schriftart.  
  
 Weitere Informationen zu globalen Optionen, die für Ihre Anwendung verfügbar sind, finden Sie unter [AFX_GLOBAL_DATA-Struktur](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="onmove"></a>  CMFCToolBarDateTimeCtrl::OnMove  
 Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste bewegt wird.  
  
```  
virtual void OnMove();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die standardmäßige Klasse-Implementierung ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)) durch Aktualisieren die Position des internen `CMFCToolBarDateTimeCtrlImpl` Objekt.  
  
##  <a name="onshow"></a>  CMFCToolBarDateTimeCtrl::OnShow  
 Vom Framework aufgerufen, wenn die Schaltfläche wird ein- oder ausgeblendet.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShow`  
 Gibt an, ob die Schaltfläche sichtbar ist. Wenn dieser Parameter ist `TRUE`, die Schaltfläche sichtbar ist. Andernfalls ist die Schaltfläche nicht sichtbar.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)) durch die Schaltfläche anzeigen, wenn `bShow` ist `TRUE`. Diese Methode ist, andernfalls die Schaltfläche ausgeblendet.  
  
##  <a name="onsize"></a>  CMFCToolBarDateTimeCtrl::OnSize  
 Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste seine Größe ändert oder Position und diese Änderung bewirkt, dass die Schaltfläche, um die Größe zu ändern.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iSize`  
 Die neue Breite der Schaltfläche in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die standardmäßige Klasse-Implementierung ( [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)) durch Aktualisieren der Größe und Position des internen `CMFCToolBarDateTimeCtrlImpl` Objekt.  
  
##  <a name="onupdatetooltip"></a>  CMFCToolBarDateTimeCtrl::OnUpdateToolTip  
 Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste die QuickInfo-Text aktualisiert.  
  
```  
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,  
    int iButtonIndex,  
    CToolTipCtrl& wndToolTip,  
    CString& str);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
 Das übergeordnete Fenster.  
  
 [in] `iButtonIndex`  
 Der nullbasierte Index der Schaltfläche in der übergeordneten Auflistung.  
  
 [in] `wndToolTip`  
 Das Steuerelement, das den QuickInfo-Text anzeigt.  
  
 [out] `str`  
 Ein `CString` Objekt, das die aktualisierten QuickInfo-Text empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Methode den QuickInfo-Text aktualisiert; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)) durch Anzeigen des QuickInfo-Texts, der mit der Schaltfläche zugeordnet ist. Wenn die Schaltfläche nicht horizontal angedockt ist, wird diese Methode wird keine Aktion ausgeführt und gibt `FALSE`.  
  
##  <a name="settime"></a>  CMFCToolBarDateTimeCtrl::SetTime  
 Legt das Datum und die in der / Zeitauswahl-Steuerelement fest.  
  
```  
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* timeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `[in] timeNew`  
 In der ersten Version, die einen Verweis auf eine [COleDateTime Klasse](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, das den Zeitpunkt enthält, auf den das Steuerelement festgelegt werden. In der zweiten Version, ein Zeiger auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das den Zeitpunkt enthält, auf den das Steuerelement festgelegt werden.  
  
 `[in] pTimeNew`  
 Ein Zeiger auf die [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) -Struktur, die den Zeitpunkt enthält, auf den das Steuerelement festgelegt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Legt die Zeit in einem Datums- und Zeitauswahl-Steuerelement fest, durch den Aufruf [CDateTimeCtrl::SetTime](../../mfc/reference/cdatetimectrl-class.md#settime).  
  
##  <a name="settimeall"></a>  CMFCToolBarDateTimeCtrl::SetTimeAll  
 Legt das Datum und die in allen Instanzen der / Zeitauswahl-Steuerelement mit einer angegebenen Befehls-ID.  
  
```  
static BOOL SetTimeAll(
    UINT uiCmd,  
    const COleDateTime& timeNew);

static BOOL SetTimeAll(
    UINT uiCmd,  
    const CTime* pTimeNew);

static BOOL SetTimeAll(
    UINT uiCmd,  
    LPSYSTEMTIME pTimeNew=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `[in] uiCmd`  
 Gibt an, eine Symbolleisten-Befehlsschaltfläche-ID.  
  
 `[in] timeNew`  
 In der ersten Version einer [COleDateTime Klasse](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, das den Zeitpunkt enthält, auf den das Steuerelement festgelegt werden. In der zweiten Version, ein Zeiger auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das den Zeitpunkt enthält, auf den das Steuerelement festgelegt werden.  
  
 `[in] pTimeNew`  
 Ein Zeiger auf die [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) -Struktur, die den Zeitpunkt enthält, auf den das Steuerelement festgelegt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Sucht nach einer Symbolleisten-Schaltfläche mit den angegebenen Befehls-ID und Festlegen der Zeit in einem Datums- und Zeitauswahl-Steuerelement, durch den Aufruf [CMFCToolBarDateTimeCtrl::SetTime](#settime).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md)



