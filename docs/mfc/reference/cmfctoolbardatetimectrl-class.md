---
title: Klasse CMFCToolBarDateTimeCtrl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- OnDrawOnCustomizeList
- CMFCToolBarDateTimeCtrl::OnDraw
- OnDraw
- CMFCToolBarDateTimeCtrl.Serialize
- CMFCToolBarDateTimeCtrl.OnSize
- CMFCToolBarDateTimeCtrl.OnDrawOnCustomizeList
- OnSize
- OnCalculateSize
- CMFCToolBarDateTimeCtrl
- CMFCToolBarDateTimeCtrl::OnCalculateSize
- SetStyle
- CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList
- CMFCToolBarDateTimeCtrl.OnDraw
- CMFCToolBarDateTimeCtrl.SetStyle
- CMFCToolBarDateTimeCtrl::SetStyle
- CMFCToolBarDateTimeCtrl.OnCalculateSize
- CMFCToolBarDateTimeCtrl::Serialize
- CMFCToolBarDateTimeCtrl::OnSize
- Serialize
dev_langs:
- C++
helpviewer_keywords:
- SetStyle method
- OnCalculateSize method
- OnDraw method
- OnDrawOnCustomizeList method
- CMFCToolBarDateTimeCtrl class
- Serialize method
- OnSize method
ms.assetid: a3853cb9-8ebc-444f-a1e4-9cf905e24c18
caps.latest.revision: 30
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
ms.openlocfilehash: 9558d62710c7be571d6aefab2c44fe504ca56d60
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbardatetimectrl-class"></a>CMFCToolBarDateTimeCtrl-Klasse
Eine Symbolleisten-Schaltfläche, die ein Datums- / Zeitauswahl-Steuerelement enthält.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCToolBarDateTimeCtrl : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl](#cmfctoolbardatetimectrl)|Erstellt ein `CMFCToolBarDateTimeCtrl`-Objekt.|  
|`CMFCToolBarDateTimeCtrl::~CMFCToolBarDateTimeCtrl`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarDateTimeCtrl::CanBeStretched](#canbestretched)|Gibt an, ob ein Benutzer während der Anpassung der Schaltfläche gestreckt werden kann. (Überschreibt [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|  
|[CMFCToolBarDateTimeCtrl::CopyFrom](#copyfrom)|Kopiert die Eigenschaften des aktuellen Schaltfläche eine andere Symbolleisten-Schaltfläche. (Überschreibt [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|`CMFCToolBarDateTimeCtrl::DuplicateData`|Für zukünftige Verwendung reserviert.|  
|[CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)|Kopiert den Text aus der Symbolleisten-Schaltfläche ein Menü.|  
|`CMFCToolBarDateTimeCtrl::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCToolBarDateTimeCtrl::GetByCmd](#getbycmd)|Ruft die erste `CMFCToolBarDateTimeCtrl` Objekt in der Anwendung mit der angegebenen Befehls-ID.|  
|[CMFCToolBarDateTimeCtrl::GetDateTimeCtrl](#getdatetimectrl)|Gibt einen Zeiger auf das Steuerelement für die Datums- und Zeitauswahl.|  
|[CMFCToolBarDateTimeCtrl::GetHwnd](#gethwnd)|Ruft das Fensterhandle, das dem die Symbolleisten-Schaltfläche zugeordnet ist. (Überschreibt [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|  
|`CMFCToolBarDateTimeCtrl::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|[CMFCToolBarDateTimeCtrl::GetTime](#gettime)|Ruft den ausgewählten Zeitpunkt aus einem Datums- / Zeitauswahl-Steuerelement ab und fügt es in einem angegebenen [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur.|  
|[CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall)|Gibt die ausgewählte Zeit über die Zeit Picker-Steuerelement-Schaltfläche, die eine angegebenen Befehls-ID.|  
|[CMFCToolBarDateTimeCtrl::HaveHotBorder](#havehotborder)|Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer die Schaltfläche auswählt. (Überschreibt [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|  
|[CMFCToolBarDateTimeCtrl::NotifyCommand](#notifycommand)|Gibt an, ob die Schaltfläche verarbeitet die [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachricht. (Überschreibt [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|  
|[CMFCToolBarDateTimeCtrl::OnAddToCustomizePage](#onaddtocustomizepage)|Vom Framework aufgerufen, wenn die Schaltfläche hinzugefügt wird ein **anpassen** Dialogfeld. (Überschreibt [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|  
|`CMFCToolBarDateTimeCtrl::OnCalculateSize`|Aufgerufen, um die Größe der Schaltfläche für den angegebenen Gerätekontext und Andockstatus berechnen. (Überschreibt [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|[CMFCToolBarDateTimeCtrl::OnChangeParentWnd](#onchangeparentwnd)|Wird vom Framework aufgerufen, wenn eine neue Symbolleiste die Schaltfläche eingefügt wird. (Überschreibt [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCToolBarDateTimeCtrl::OnClick](#onclick)|Vom Framework aufgerufen, wenn der Benutzer das Steuerelement klickt. (Überschreibt [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCToolBarDateTimeCtrl::OnCtlColor](#onctlcolor)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste behandelt eine `WM_CTLCOLOR` Nachricht. (Überschreibt [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|  
|`CMFCToolBarDateTimeCtrl::OnDraw`|Vom Framework aufgerufen wird die Schaltfläche gezeichnet werden soll, mithilfe der angegebenen Formate und -Optionen. (Überschreibt [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|`CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList`|Aufgerufen, um das Zeichnen der Schaltfläche die **Befehle** im Bereich der **anpassen** Dialogfeld. (Überschreibt [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged](#onglobalfontschanged)|Wird vom Framework aufgerufen, wenn die globale Schriftart geändert hat. (Überschreibt [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|  
|[CMFCToolBarDateTimeCtrl::OnMove](#onmove)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste verschoben wird. (Überschreibt [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|  
|[CMFCToolBarDateTimeCtrl::OnShow](#onshow)|Vom Framework aufgerufen, wenn die Schaltfläche wird sichtbar oder unsichtbar. (Überschreibt [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|  
|`CMFCToolBarDateTimeCtrl::OnSize`|Wird vom Framework aufgerufen, wenn die übergeordneten Symbolleiste seine Größe ändert oder Position und diese Änderung bewirkt, dass die Schaltfläche, um die Größe zu ändern. (Überschreibt [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|  
|[CMFCToolBarDateTimeCtrl::OnUpdateToolTip](#onupdatetooltip)|Wird vom Framework aufgerufen, wenn die übergeordneten Symbolleiste den QuickInfotext aktualisiert. (Überschreibt [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|  
|`CMFCToolBarDateTimeCtrl::Serialize`|Dieses Objekt aus dem Archiv liest oder schreibt dieses in ein Archiv (überschreibt [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|`CMFCToolBarDateTimeCtrl::SetStyle`|Legt den Stil der Symbolleisten-Schaltfläche. (Überschreibt [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|  
|[CMFCToolBarDateTimeCtrl::SetTime](#settime)|Legt das Datum und die im Steuerelement für die Auswahl fest.|  
|[CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall)|Legt das Datum und die in alle Instanzen des Steuerelements für die Auswahl mit einem angegebenen Befehls-ID.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Beispiel zur Verwendung einer Datums- / Zeitauswahl-Steuerelement finden Sie unter das ToolbarDateTimePicker-Beispielprojekt. Informationen zur Vorgehensweise beim Hinzufügen von Schaltflächen in Symbolleisten finden Sie unter [Exemplarische Vorgehensweise: Einfügen von Steuerelementen auf Symbolleisten](../../mfc/walkthrough-putting-controls-on-toolbars.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtoolbardatetimectrl.h  
  
##  <a name="a-namecanbestretcheda--cmfctoolbardatetimectrlcanbestretched"></a><a name="canbestretched"></a>CMFCToolBarDateTimeCtrl::CanBeStretched  
 Gibt an, ob ein Benutzer während der Anpassung der Schaltfläche gestreckt werden kann.  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig lässt das Framework nicht den Benutzer eine Symbolleisten-Schaltfläche während der Anpassung ausdehnen. Diese Methode erweitert die Implementierung der Basisklasse ( [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)) von dem der Benutzer eine Symbolleisten-Schaltfläche für Datum und Uhrzeit während der Anpassung ausdehnen.  
  
##  <a name="a-namecmfctoolbardatetimectrla--cmfctoolbardatetimectrlcmfctoolbardatetimectrl"></a><a name="cmfctoolbardatetimectrl"></a>CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl  
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
 Das Format von den `CMFCToolBarDateTimeCtrlImpl` Fenster, das erstellt wird, wenn ein Benutzer auf die Schaltfläche klickt.  
  
 [in] `iWidth`  
 Die Breite des Steuerelements in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Objekt wird mit dem Systemdatum und-Uhrzeit initialisiert. Der Fensterstil des internen `CMFCToolBarDateTimeCtrlImpl` -Objekt enthält die `dwStyle` Parameter und die `WS_CHILD` und `WS_VISIBLE` Formate. Sie können mit dieser Stile ändern `CMFCToolBarDateTimeCtrl::SetStyle`. Verwendung `SetStyle` so ändern Sie den Stil des der `CMFCToolBarDateTimeCtrl` Steuerelement.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt vom Erstellen der `CMFCToolBarDateTimeCtrl` Klasse. Dieser Codeausschnitt ist Teil der [Symbolleiste Datums-/Zeitauswahl-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_ToolbarDateTimePicker&#1;](../../mfc/reference/codesnippet/cpp/cmfctoolbardatetimectrl-class_1.cpp)]  
  
##  <a name="a-namecopyfroma--cmfctoolbardatetimectrlcopyfrom"></a><a name="copyfrom"></a>CMFCToolBarDateTimeCtrl::CopyFrom  
 Kopiert die Eigenschaften des aktuellen Schaltfläche eine andere Symbolleisten-Schaltfläche.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `src`  
 Ein Verweis auf die Schaltfläche "Quelle" aus dem kopiert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Kopieren von einem anderen Symbolleisten-Schaltfläche auf diese Schaltfläche. `src`muss vom Typ `CMFCToolBarDateTimeCtrl`.  
  
##  <a name="a-nameexporttomenubuttona--cmfctoolbardatetimectrlexporttomenubutton"></a><a name="exporttomenubutton"></a>CMFCToolBarDateTimeCtrl::ExportToMenuButton  
 Kopiert den Text aus der Symbolleisten-Schaltfläche ein Menü.  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `menuButton`  
 Ein Verweis auf die Schaltfläche Ziel.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die Implementierung der Basisklasse ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) durch Laden der Zeichenfolgenressource, die die Befehls-ID des Steuerelements zugeordnet ist. Weitere Informationen zu Ressourcen finden Sie unter [CStringT::LoadString](../../atl-mfc-shared/reference/cstringt-class.md#loadstring).  
  
##  <a name="a-namegetbycmda--cmfctoolbardatetimectrlgetbycmd"></a><a name="getbycmd"></a>CMFCToolBarDateTimeCtrl::GetByCmd  
 Ruft die erste `CMFCToolBarDateTimeCtrl` Objekt in der Anwendung mit der angegebenen Befehls-ID.  
  
```  
static CMFCToolBarDateTimeCtrl* __stdcall GetByCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die Befehls-ID der Schaltfläche abrufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste `CMFCToolBarDateTimeCtrl` Objekt in der Anwendung mit der angegebenen Befehls-ID oder `NULL` Wenn kein `CMFCToolBarDateTimeCtrl` Objekte verfügen über die angegebene Befehls-ID.  
  
### <a name="remarks"></a>Hinweise  
 Diese gemeinsam genutzte Dienstprogramme-Methode wird von Methoden verwendet, z. B. [CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall) und [CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall) festlegen oder Abrufen von Uhrzeit und Datum der alle Instanzen des Steuerelements für die Auswahl mit einem angegebenen Befehls-ID.  
  
##  <a name="a-namegetdatetimectrla--cmfctoolbardatetimectrlgetdatetimectrl"></a><a name="getdatetimectrl"></a>CMFCToolBarDateTimeCtrl::GetDateTimeCtrl  
 Gibt einen Zeiger auf das Steuerelement für die Datums- und Zeitauswahl.  
  
```  
CDateTimeCtrl* GetDateTimeCtrl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Datums- und Zeitauswahl; oder `NULL` , wenn das Steuerelement nicht vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Die `CMFCToolBarDateTimeCtrl` Klasse initialisiert die `m_pWndDateTime` Datenmember beim Einfügen einer `CMFCToolBarDateTimeCtrl` Objekt in eine Symbolleiste.  
  
##  <a name="a-namegethwnda--cmfctoolbardatetimectrlgethwnd"></a><a name="gethwnd"></a>CMFCToolBarDateTimeCtrl::GetHwnd  
 Ruft das Fensterhandle, das dem die Symbolleisten-Schaltfläche zugeordnet ist.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Fensterhandle, das dem Datum und Uhrzeit Symbolleisten-Schaltfläche zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) Methode.  
  
##  <a name="a-namegettimea--cmfctoolbardatetimectrlgettime"></a><a name="gettime"></a>CMFCToolBarDateTimeCtrl::GetTime  
 Ruft die ausgewählte Zeit aus der zugeordneten Datums und / Zeitauswahl-Steuerelement ab und fügt es in einem angegebenen [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur  
  
```  
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `[out] timeDest`  
 In der ersten Überladung ist ein [COleDateTime-Klasse](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, das die Zeitinformationen System erhalten. In der zweiten Überladung ist ein [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das die Zeitinformationen System erhalten.  
  
 `[out] pTimeDest`  
 Ein Zeiger auf die [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, um die Systeminformationen für die Zeit zu erhalten. Dieser Wert darf nicht `NULL` sein.  
  
### <a name="return-value"></a>Rückgabewert  
 In der ersten Überladung, die einen Wert ungleich NULL, wenn die Zeit erfolgreich, um geschrieben werden die [COleDateTime-Klasse](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, andernfalls 0. In der zweiten und dritten Überladungen der Rückgabewert ist eine `DWORD` gleich das dwFlags-Element, das festgelegt wurde, in der [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Der Methode wird der [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) Struktur DwFlags Member, um anzugeben, ob die Datums- und Zeitauswahl auf Datum und Uhrzeit festgelegt wird. Wenn der Wert gleich GDT_NONE ist, wird das Steuerelement auf festgelegt `no date` Status, und verwendet den DTS_SHOWNONE-Stil. Wenn der zurückgegebene Wert GDT_VALID gleich ist, wird die Systemzeit erfolgreich am Zielspeicherort gespeichert.  
  
##  <a name="a-namegettimealla--cmfctoolbardatetimectrlgettimeall"></a><a name="gettimeall"></a>CMFCToolBarDateTimeCtrl::GetTimeAll  
 Gibt die Zeit, die vom Benutzer über die Zeit Picker-Steuerelement Schaltfläche mit einer angegebenen Befehls-ID. ausgewählt  
  
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
 Gibt eine Symbolleisten-Schaltfläche-Befehls-ID.  
  
 `[out] timeDest`  
 In der ersten Überladung ist ein [COleDateTime-Klasse](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, das die Zeitinformationen System erhalten. In der zweiten Überladung ist ein [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das die Zeitinformationen System erhalten.  
  
 `[out] pTimeDest`  
 Ein Zeiger auf die [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, um die Systeminformationen für die Zeit zu erhalten. Dieser Wert darf nicht `NULL` sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn das Framework eine Symbolleisten-Schaltfläche finden kann, die die Befehls-ID entspricht `uiCmd`, der Rückgabewert ist&0; (null) in der ersten Überladung und GDT_NONE in den anderen Überladungen. Wenn die Symbolleisten-Schaltfläche gefunden wird, wird der Rückgabewert ist identisch mit der Rückgabewert bei einem Aufruf von [CMFCToolBarDateTimeCtrl::GetTime](#gettime) auf diese Schaltfläche. Ein Rückgabewert Wert&0; (null) oder GDT_NONE kann auftreten, wenn die Schaltfläche gefunden wird, der angibt, dass der Aufruf von `GetTime` hat kein gültiges Datum für einen anderen Grund zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sucht nach einer Symbolleisten-Schaltfläche mit der angegebenen Befehls-ID und Aufrufe [CMFCToolBarDateTimeCtrl::GetTime](#gettime) Methode auf diese Schaltfläche.  
  
##  <a name="a-namehavehotbordera--cmfctoolbardatetimectrlhavehotborder"></a><a name="havehotborder"></a>CMFCToolBarDateTimeCtrl::HaveHotBorder  
 Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer die Schaltfläche auswählt.  
  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn eine Schaltfläche eine Rahmenlinie bei Auswahl angezeigt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt einen Wert ungleich NULL zurück, wenn das Steuerelement sichtbar ist.  
  
##  <a name="a-namenotifycommanda--cmfctoolbardatetimectrlnotifycommand"></a><a name="notifycommand"></a>CMFCToolBarDateTimeCtrl::NotifyCommand  
 Gibt an, ob die Schaltfläche verarbeitet die [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachricht.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iNotifyCode`  
 Die Nachricht, die mit dem Befehl zugeordnet ist.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Schaltfläche verarbeitet die `WM_COMMAND` Nachricht oder `FALSE` an, dass die Nachricht von der übergeordneten Symbolleiste behandelt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode aus, wenn es senden möchten, ist ein [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachricht an das übergeordnete Fenster.  
  
 Diese Methode erweitert die Implementierung der Basisklasse ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) durch die Verarbeitung der [DTN_DATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761737) Benachrichtigung. Den interne Status aktualisiert und aktualisiert die Time-Eigenschaft aller `CMFCToolBarDateTimeCtrl` Objekte mit dem gleichen Befehl ID.  
  
##  <a name="a-nameonaddtocustomizepagea--cmfctoolbardatetimectrlonaddtocustomizepage"></a><a name="onaddtocustomizepage"></a>CMFCToolBarDateTimeCtrl::OnAddToCustomizePage  
 Vom Framework aufgerufen, wenn die Schaltfläche hinzugefügt wird ein **anpassen** Dialogfeld.  
  
```  
virtual void OnAddToCustomizePage();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die Implementierung der Basisklasse [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage), durch Kopieren der Eigenschaften aus dem ersten Datum und die Uhrzeit-Steuerelement in die Symbolleisten, die derselben Befehls-ID wie dieses Objekt ist. Diese Methode bewirkt nichts, wenn keine Symbolleiste ein Steuerelements für Datum und Uhrzeit, das mit derselben Befehls-ID wie dieses Objekt besitzt.  
  
 Weitere Informationen zu den **anpassen** Dialogfeld finden Sie unter [CMFCToolBarsCustomizeDialog Klasse](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).  
  
##  <a name="a-nameonchangeparentwnda--cmfctoolbardatetimectrlonchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFCToolBarDateTimeCtrl::OnChangeParentWnd  
 Wird vom Framework aufgerufen, wenn eine neue Symbolleiste die Schaltfläche eingefügt wird.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
 Das neue übergeordnete Fenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die Implementierung der Basisklasse ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) durch Neuerstellen der internen `CMFCToolBarDateTimeCtrlImpl` Objekt.  
  
##  <a name="a-nameonclicka--cmfctoolbardatetimectrlonclick"></a><a name="onclick"></a>CMFCToolBarDateTimeCtrl::OnClick  
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
 Diese Methode überschreibt die Implementierung der Basisklasse [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), indem ein Wert ungleich NULL zurückgegeben, wenn die interne `CMFCToolBarDateTimeCtrlImpl` -Objekt sichtbar ist.  
  
##  <a name="a-nameonctlcolora--cmfctoolbardatetimectrlonctlcolor"></a><a name="onctlcolor"></a>CMFCToolBarDateTimeCtrl::OnCtlColor  
 Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste behandelt eine `WM_CTLCOLOR` Nachricht.  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Der Gerätekontext, der die Schaltfläche angezeigt.  
  
 [in] `nCtlColor`  
 Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für den globalen Pinsel, den das Framework verwendet, um den Hintergrund der Schaltfläche zeichnen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die Implementierung der Basisklasse [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)durch Festlegen des Texts und Hintergrundfarben des Gerätekontexts auf den globalen Text bereitgestellten und Hintergrundfarben, bzw..  
  
 Weitere Informationen zu globalen Optionen, die für Ihre Anwendung verfügbar sind, finden Sie unter [AFX_GLOBAL_DATA-Struktur](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="a-nameonglobalfontschangeda--cmfctoolbardatetimectrlonglobalfontschanged"></a><a name="onglobalfontschanged"></a>CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged  
 Wird vom Framework aufgerufen, wenn die globale Schriftart geändert hat.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die Implementierung der Basisklasse ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) durch Ändern der Schriftart des Steuerelements mit der globalen Schriftart.  
  
 Weitere Informationen zu globalen Optionen, die für Ihre Anwendung verfügbar sind, finden Sie unter [AFX_GLOBAL_DATA-Struktur](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="a-nameonmovea--cmfctoolbardatetimectrlonmove"></a><a name="onmove"></a>CMFCToolBarDateTimeCtrl::OnMove  
 Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste verschoben wird.  
  
```  
virtual void OnMove();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die Implementierung der Klasse ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)) aktualisieren Sie die Position des internen `CMFCToolBarDateTimeCtrlImpl` Objekt.  
  
##  <a name="a-nameonshowa--cmfctoolbardatetimectrlonshow"></a><a name="onshow"></a>CMFCToolBarDateTimeCtrl::OnShow  
 Vom Framework aufgerufen, wenn die Schaltfläche wird sichtbar oder unsichtbar.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShow`  
 Gibt an, ob die Schaltfläche sichtbar ist. Wenn dieser Parameter ist `TRUE`, die Schaltfläche sichtbar ist. Andernfalls ist die Schaltfläche nicht angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die Implementierung der Basisklasse ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)) durch die Schaltfläche anzeigen, wenn `bShow` ist `TRUE`. Diese Methode ist, andernfalls die Schaltfläche ausgeblendet.  
  
##  <a name="a-nameonsizea--cmfctoolbardatetimectrlonsize"></a><a name="onsize"></a>CMFCToolBarDateTimeCtrl::OnSize  
 Wird vom Framework aufgerufen, wenn die übergeordneten Symbolleiste seine Größe ändert oder Position und diese Änderung bewirkt, dass die Schaltfläche, um die Größe zu ändern.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iSize`  
 Die neue Breite der Schaltfläche in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die Implementierung der Klasse ( [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)) durch Aktualisieren der Größe und Position des internen `CMFCToolBarDateTimeCtrlImpl` Objekt.  
  
##  <a name="a-nameonupdatetooltipa--cmfctoolbardatetimectrlonupdatetooltip"></a><a name="onupdatetooltip"></a>CMFCToolBarDateTimeCtrl::OnUpdateToolTip  
 Wird vom Framework aufgerufen, wenn die übergeordneten Symbolleiste den QuickInfotext aktualisiert.  
  
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
 Ein `CString` -Objekt, das den aktualisierten QuickInfo-Text erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Methode den QuickInfo-Text aktualisiert; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die Implementierung der Basisklasse ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)) durch Anzeigen des QuickInfo-Texts, der mit der Schaltfläche zugeordnet ist. Wenn die Schaltfläche nicht horizontal angedockt ist, wird diese Methode führt keine Aktion aus und gibt `FALSE`.  
  
##  <a name="a-namesettimea--cmfctoolbardatetimectrlsettime"></a><a name="settime"></a>CMFCToolBarDateTimeCtrl::SetTime  
 Legt das Datum und die im Steuerelement für die Auswahl fest.  
  
```  
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* timeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `[in] timeNew`  
 In der ersten Version, die einen Verweis auf eine [COleDateTime-Klasse](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, das die Zeit enthält, zu dem das Steuerelement festgelegt werden. In der zweiten Version, die einen Zeiger auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das die Zeit enthält, zu dem das Steuerelement festgelegt werden.  
  
 `[in] pTimeNew`  
 Ein Zeiger auf die [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) -Struktur, die den Zeitpunkt enthält, zu dem das Steuerelement festgelegt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Legt die Zeit in einem Datums- / Zeitauswahl-Steuerelement durch Aufrufen von [CDateTimeCtrl::SetTime](../../mfc/reference/cdatetimectrl-class.md#settime).  
  
##  <a name="a-namesettimealla--cmfctoolbardatetimectrlsettimeall"></a><a name="settimeall"></a>CMFCToolBarDateTimeCtrl::SetTimeAll  
 Legt das Datum und die in alle Instanzen des Steuerelements für die Auswahl mit einem angegebenen Befehls-ID.  
  
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
 Gibt eine Symbolleisten-Schaltfläche-Befehls-ID.  
  
 `[in] timeNew`  
 In der ersten Version eine [COleDateTime-Klasse](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, das die Zeit enthält, zu dem das Steuerelement festgelegt werden. In der zweiten Version, die einen Zeiger auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das die Zeit enthält, zu dem das Steuerelement festgelegt werden.  
  
 `[in] pTimeNew`  
 Ein Zeiger auf die [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) -Struktur, die den Zeitpunkt enthält, zu dem das Steuerelement festgelegt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Sucht nach einer Symbolleisten-Schaltfläche mit der angegebenen Befehls-ID und legt die Zeit in einem Datums- / Zeitauswahl-Steuerelement durch Aufrufen von [CMFCToolBarDateTimeCtrl::SetTime](#settime).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [Exemplarische Vorgehensweise: Einfügen von Steuerelementen in Symbolleisten](../../mfc/walkthrough-putting-controls-on-toolbars.md)




