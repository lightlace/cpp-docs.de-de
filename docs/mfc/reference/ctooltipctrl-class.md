---
title: CToolTipCtrl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CToolTipCtrl
- AFXCMN/CToolTipCtrl
- AFXCMN/CToolTipCtrl::CToolTipCtrl
- AFXCMN/CToolTipCtrl::Activate
- AFXCMN/CToolTipCtrl::AddTool
- AFXCMN/CToolTipCtrl::AdjustRect
- AFXCMN/CToolTipCtrl::Create
- AFXCMN/CToolTipCtrl::CreateEx
- AFXCMN/CToolTipCtrl::DelTool
- AFXCMN/CToolTipCtrl::GetBubbleSize
- AFXCMN/CToolTipCtrl::GetCurrentTool
- AFXCMN/CToolTipCtrl::GetDelayTime
- AFXCMN/CToolTipCtrl::GetMargin
- AFXCMN/CToolTipCtrl::GetMaxTipWidth
- AFXCMN/CToolTipCtrl::GetText
- AFXCMN/CToolTipCtrl::GetTipBkColor
- AFXCMN/CToolTipCtrl::GetTipTextColor
- AFXCMN/CToolTipCtrl::GetTitle
- AFXCMN/CToolTipCtrl::GetToolCount
- AFXCMN/CToolTipCtrl::GetToolInfo
- AFXCMN/CToolTipCtrl::HitTest
- AFXCMN/CToolTipCtrl::Pop
- AFXCMN/CToolTipCtrl::Popup
- AFXCMN/CToolTipCtrl::RelayEvent
- AFXCMN/CToolTipCtrl::SetDelayTime
- AFXCMN/CToolTipCtrl::SetMargin
- AFXCMN/CToolTipCtrl::SetMaxTipWidth
- AFXCMN/CToolTipCtrl::SetTipBkColor
- AFXCMN/CToolTipCtrl::SetTipTextColor
- AFXCMN/CToolTipCtrl::SetTitle
- AFXCMN/CToolTipCtrl::SetToolInfo
- AFXCMN/CToolTipCtrl::SetToolRect
- AFXCMN/CToolTipCtrl::SetWindowTheme
- AFXCMN/CToolTipCtrl::Update
- AFXCMN/CToolTipCtrl::UpdateTipText
dev_langs:
- C++
helpviewer_keywords:
- CToolTipCtrl [MFC], CToolTipCtrl
- CToolTipCtrl [MFC], Activate
- CToolTipCtrl [MFC], AddTool
- CToolTipCtrl [MFC], AdjustRect
- CToolTipCtrl [MFC], Create
- CToolTipCtrl [MFC], CreateEx
- CToolTipCtrl [MFC], DelTool
- CToolTipCtrl [MFC], GetBubbleSize
- CToolTipCtrl [MFC], GetCurrentTool
- CToolTipCtrl [MFC], GetDelayTime
- CToolTipCtrl [MFC], GetMargin
- CToolTipCtrl [MFC], GetMaxTipWidth
- CToolTipCtrl [MFC], GetText
- CToolTipCtrl [MFC], GetTipBkColor
- CToolTipCtrl [MFC], GetTipTextColor
- CToolTipCtrl [MFC], GetTitle
- CToolTipCtrl [MFC], GetToolCount
- CToolTipCtrl [MFC], GetToolInfo
- CToolTipCtrl [MFC], HitTest
- CToolTipCtrl [MFC], Pop
- CToolTipCtrl [MFC], Popup
- CToolTipCtrl [MFC], RelayEvent
- CToolTipCtrl [MFC], SetDelayTime
- CToolTipCtrl [MFC], SetMargin
- CToolTipCtrl [MFC], SetMaxTipWidth
- CToolTipCtrl [MFC], SetTipBkColor
- CToolTipCtrl [MFC], SetTipTextColor
- CToolTipCtrl [MFC], SetTitle
- CToolTipCtrl [MFC], SetToolInfo
- CToolTipCtrl [MFC], SetToolRect
- CToolTipCtrl [MFC], SetWindowTheme
- CToolTipCtrl [MFC], Update
- CToolTipCtrl [MFC], UpdateTipText
ms.assetid: 8973f70c-b73a-46c7-908d-758f364b9a97
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f67a9ccb25216c6f7546d9d906f91cfe5102bc4a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ctooltipctrl-class"></a>CToolTipCtrl Class
Kapselt die Funktionalität eines ToolTip-Steuerelements. Dabei handelt es sich um ein kleines Popupfenster, das eine einzelne Textzeile anzeigt, die den Zweck eines Tools der Anwendung beschreibt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CToolTipCtrl : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CToolTipCtrl::CToolTipCtrl](#ctooltipctrl)|Erstellt ein `CToolTipCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CToolTipCtrl::Activate](#activate)|Aktiviert und deaktiviert das QuickInfo-Steuerelement.|  
|[CToolTipCtrl::AddTool](#addtool)|Registriert ein Tool mit der QuickInfo-Steuerelement.|  
|[CToolTipCtrl::AdjustRect](#adjustrect)|Konvertiert zwischen einer QuickInfo-Steuerelements Text anzeigen Rechteck und das Fenster Rechteck.|  
|[CToolTipCtrl::Create](#create)|Erstellt ein QuickInfo-Steuerelement, und fügt es einer `CToolTipCtrl` Objekt.|  
|[CToolTipCtrl::CreateEx](#createex)|Erstellt ein QuickInfo-Steuerelement mit der angegebenen erweiterten Fensterstile und fügt es einer `CToolTipCtrl` Objekt.|  
|[CToolTipCtrl::DelTool](#deltool)|Entfernt ein Tool aus der QuickInfo-Steuerelement.|  
|[CToolTipCtrl::GetBubbleSize](#getbubblesize)|Ruft die Größe der QuickInfo ab.|  
|[CToolTipCtrl::GetCurrentTool](#getcurrenttool)|Ruft Informationen wie Größe, Position und Text, der das QuickInfo-Fenster, in dem das aktuelle QuickInfo-Steuerelement angezeigt.|  
|[CToolTipCtrl::GetDelayTime](#getdelaytime)|Ruft ab, die anfängliche Popup und Reshow Dauer, die derzeit für ein Tool festgelegt sind QuickInfo-Steuerelement.|  
|[CToolTipCtrl::GetMargin](#getmargin)|Ruft ab, der nach oben, links, unteren und rechten Ränder, die für ein QuickInfo-Fenster festgelegt werden.|  
|[CToolTipCtrl::GetMaxTipWidth](#getmaxtipwidth)|Ruft die maximale Breite für ein QuickInfo-Fenster ab.|  
|[CToolTipCtrl::GetText](#gettext)|Ruft den Text, den ein QuickInfo-Steuerelement für ein Tool verwaltet.|  
|[CToolTipCtrl::GetTipBkColor](#gettipbkcolor)|Ruft die Farbe des Hintergrunds in ein QuickInfo-Fenster ab.|  
|[CToolTipCtrl::GetTipTextColor](#gettiptextcolor)|Ruft die Textfarbe in ein QuickInfo-Fenster ab.|  
|[CToolTipCtrl::GetTitle](#gettitle)|Ruft den Titel des aktuellen QuickInfo-Steuerelements ab.|  
|[CToolTipCtrl::GetToolCount](#gettoolcount)|Ruft die Anzahl der durch ein QuickInfo-Steuerelement verwaltet Tools ab.|  
|[CToolTipCtrl::GetToolInfo](#gettoolinfo)|Ruft ab, der ein QuickInfo-Steuerelement verwaltet Informationen zu einem Tool aus.|  
|[CToolTipCtrl::HitTest](#hittest)|Testet eine herstellen kann, um zu bestimmen, ob es sich innerhalb des umschließenden Rechtecks des angegebenen Tools ist. Wenn dies der Fall ist, ruft Informationen über das Tool ab.|  
|[CToolTipCtrl::Pop](#pop)|Entfernt ein angezeigte QuickInfo-Fenster aus der Ansicht.|  
|[CToolTipCtrl::Popup](#popup)|Bewirkt, dass das aktuelle QuickInfo-Steuerelement an den Koordinaten der letzten Maus Nachricht angezeigt.|  
|[CToolTipCtrl:: RelayEvent](#relayevent)|Übergibt eine Maus-Nachricht an ein QuickInfo-Steuerelement für die Verarbeitung.|  
|[CToolTipCtrl::SetDelayTime](#setdelaytime)|Legt den ersten, Popup und Wiederholungsdauern für ein QuickInfo-Steuerelement.|  
|[CToolTipCtrl::SetMargin](#setmargin)|Legt fest, der nach oben, links, unteren und rechten Ränder für ein QuickInfo-Fenster.|  
|[CToolTipCtrl::SetMaxTipWidth](#setmaxtipwidth)|Legt die maximale Breite für ein QuickInfo-Fenster an.|  
|[CToolTipCtrl::SetTipBkColor](#settipbkcolor)|Legt die Hintergrundfarbe in einem Tipp Toolfenster fest.|  
|[CToolTipCtrl::SetTipTextColor](#settiptextcolor)|Legt die Textfarbe in einem Tipp Toolfenster fest.|  
|[CToolTipCtrl::SetTitle](#settitle)|Eine QuickInfo hinzugefügt ein Symbol "und" Title Standardzeichenfolge.|  
|[CToolTipCtrl::SetToolInfo](#settoolinfo)|Legt die Informationen, die eine QuickInfo für ein Tool verwaltet.|  
|[CToolTipCtrl::SetToolRect](#settoolrect)|Legt einen neuen umschließenden Rechtecks für ein Tool.|  
|[CToolTipCtrl::SetWindowTheme](#setwindowtheme)|Legt fest, der die visuelle Darstellung der QuickInfo-Fenster.|  
|[CToolTipCtrl::Update](#update)|Erzwingt, dass das aktuelle Tool neu gezeichnet wird.|  
|[CToolTipCtrl::UpdateTipText](#updatetiptext)|Legt den QuickInfo-Text für ein Tool.|  
  
## <a name="remarks"></a>Hinweise  
 Ein "Tool" ist entweder ein Fenster, z. B. ein untergeordnetes Fenster oder Steuerelement oder einen anwendungsdefinierten rechteckigen Bereich im Clientbereich eines Fensters. Eine QuickInfo wird in den meisten Fällen, erscheint nur, wenn der Benutzer fügt den Cursor auf einem Tool und bleibt es zumeist Zweitens ausgeblendet. Die QuickInfo wird angezeigt, in der Nähe des Cursors und verschwindet, wenn der Benutzer eine Maustaste klickt, oder des Cursors deaktiviert das Tool bewegen.  
  
 `CToolTipCtrl`Stellt die Funktionalität steuern die Anfangszeit und die Dauer der QuickInfo, die Rand-Breite, der den QuickInfo-Text, die Breite des das QuickInfo-Fenster selbst und die Hintergrund- und Textfarben der QuickInfo umgibt bereit. Ein einzelnes QuickInfo-Steuerelement kann es sich um Informationen für mehrere Tools bereitstellen.  
  
 Die `CToolTipCtrl` Klasse stellt die Funktionalität des allgemeinen Windows-Tool QuickInfo-Steuerelements bereit. Dieses Steuerelement (und somit die `CToolTipCtrl` Klasse) und höher verfügbar nur für Programme, die unter Windows 95-und Windows 98 und Windows NT, Version 3.51 ausgeführt wird.  
  
 Weitere Informationen zu QuickInfos finden Sie unter [QuickInfos in Fenstern, die nicht von CFrameWnd abgeleitet werden](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).  
  
 Weitere Informationen zur Verwendung von `CToolTipCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CToolTipCtrl](../../mfc/using-ctooltipctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CToolTipCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="activate"></a>CToolTipCtrl::Activate  
 Mit dieser Funktion wird zum Aktivieren oder deaktivieren Sie ein QuickInfo-Steuerelement.  
  
```  
void Activate(BOOL bActivate);
```  
  
### <a name="parameters"></a>Parameter  
 `bActivate`  
 Gibt an, ob das QuickInfo-Steuerelement aktiviert oder deaktiviert wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bActivate` ist **"true"**, das Steuerelement aktiviert ist; Wenn **"false"**, es wird deaktiviert.  
  
 Wenn ein QuickInfo-Steuerelement aktiv ist, werden die Tool QuickInfo-Informationen angezeigt, wenn der Cursor auf einem Tool befindet, die mit dem Steuerelement registriert ist; Wenn er nicht aktiv ist, das Tool QuickInfo-Informationen nicht angezeigt wird, selbst wenn sich der Cursor auf einem Tool befindet.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="addtool"></a>CToolTipCtrl::AddTool  
 Registriert ein Tool mit der QuickInfo-Steuerelement.  
  
```  
BOOL AddTool(
    CWnd* pWnd,  
    UINT nIDText,  
    LPCRECT lpRectTool = NULL,  
    UINT_PTR nIDTool = 0);

 
BOOL AddTool(
    CWnd* pWnd,  
    LPCTSTR lpszText = LPSTR_TEXTCALLBACK,  
    LPCRECT lpRectTool = NULL,  
    UINT_PTR nIDTool = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Ein Zeiger auf das Fenster, das Tool enthält.  
  
 `nIDText`  
 ID der Zeichenfolgenressource, die den Text für das Tool enthält.  
  
 *lpRectTool*  
 Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die Koordinaten des Tools enthält umschließenden Rechtecks. Die Koordinaten sind relativ zur linken oberen Ecke des Clientbereichs des Fensters identifizierten `pWnd`.  
  
 `nIDTool`  
 Die ID des Tools.  
  
 `lpszText`  
 Zeiger auf den Text für das Tool. Wenn dieser Parameter den Wert enthält **LPSTR_TEXTCALLBACK**, **TTN_NEEDTEXT** benachrichtigungsmeldungen zu wechseln, um das übergeordnete Element des Fensters, `pWnd` verweist auf.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die **LpRectTool** und **nIDTool** Parameter müssen beide gültig sein, oder wenn **LpRectTool** NULL ist, **nIDTool** muss 0 sein.  
  
 Ein QuickInfo-Steuerelement kann mehrere Tool zugeordnet werden. Rufen Sie diese Funktion, um ein Tool für das QuickInfo-Steuerelement, zu registrieren, damit die Informationen gespeichert, die in der QuickInfo angezeigt wird, wenn der Cursor in das Tool befindet.  
  
> [!NOTE]
>  Sie können eine QuickInfo auf ein statisches Steuerelement mit festlegen `AddTool`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="adjustrect"></a>CToolTipCtrl::AdjustRect  
 Konvertiert zwischen ein QuickInfo-Steuerelement Text anzeigen Rechteck und das Fenster Rechteck.  
  
```  
BOOL AdjustRect(
    LPRECT lprc,  
    BOOL bLarger = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `lprc`  
 Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die ein Tool Tipp Fenster Rechteck oder eine Anzeigerechteck Text enthält.  
  
 `bLarger`  
 Wenn **"true"**, `lprc` wird verwendet, um Text Anzeigerechteck angeben und die entsprechenden fensterrechtecke erhält. Wenn **"false"**, `lprc` verwendet, um ein Rechteck Fenster anzugeben und den entsprechenden Text Anzeigerechteck erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn das Rechteck erfolgreich angepasst wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion berechnet ein QuickInfo-Steuerelement des Text-Anzeigerechteck aus seiner fensterrechtecke oder das Tool Tipp fensterrechtecke benötigt, um einen angegebenen Text Anzeigerechteck anzuzeigen.  
  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_ADJUSTRECT](http://msdn.microsoft.com/library/windows/desktop/bb760352)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="create"></a>CToolTipCtrl::Create  
 Erstellt ein QuickInfo-Steuerelement, und fügt es einer `CToolTipCtrl` Objekt.  
  
```  
virtual BOOL Create(CWnd* pParentWnd, DWORD dwStyle = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentWnd`  
 Gibt an, das QuickInfo-Steuerelement des übergeordneten Fensters, in der Regel eine `CDialog`. Es muss nicht **NULL**.  
  
 `dwStyle`  
 Gibt den QuickInfo-Steuerelements-Stil. Finden Sie unter der **"Hinweise"** Abschnitt, um weitere Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CToolTipCtrl` Objekt wurde erfolgreich erstellt wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CToolTipCtrl` in zwei Schritten. Rufen Sie zunächst den Konstruktor zum Erstellen der `CToolTipCtrl` Objekt, und rufen dann **erstellen** erstellen das QuickInfo-Steuerelement und fügen Sie es auf die `CToolTipCtrl` Objekt.  
  
 Die `dwStyle` Parameter kann eine beliebige Kombination von [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles). Darüber hinaus weist ein QuickInfo-Steuerelement zwei klassenspezifische Stile: **TTS_ALWAYSTIP** und **TTS_NOPREFIX**.  
  
|Stil|Bedeutung|  
|-----------|-------------|  
|**TTS_ALWAYSTIP**|Gibt an, dass die QuickInfo angezeigt wird, wenn der Cursor befindet sich auf einem Tool, unabhängig davon, ob die QuickInfo-Steuerelements Besitzerfenster aktiv oder inaktiv ist. Ohne diesen Stil wird das QuickInfo-Steuerelement angezeigt, wenn das Tool besitzende Fenster aktiv ist, jedoch nicht, wenn er nicht aktiv ist.|  
|**TTS_NOPREFIX**|Dieses Format wird verhindert, dass das System Striping das kaufmännische und-Zeichen aus einer Zeichenfolge (&). Wenn ein QuickInfo-Steuerelement keinen der **TTS_NOPREFIX** Format, das System entfernt automatisch kaufmännische und-Zeichen, ermöglicht es einer Anwendung auf die gleiche Zeichenfolge als sowohl ein Menüelement und als Text in ein QuickInfo-Steuerelement verwenden.|  
  
 Ein QuickInfo-Steuerelement verfügt über die `WS_POPUP` und **WS_EX_TOOLWINDOW** Fensterstile, unabhängig davon, ob Sie sie angeben, wenn das Steuerelement erstellt.  
  
 Rufen Sie zum Erstellen einer QuickInfo-Steuerelement mit erweiterten Fensterstile [CToolTipCtrl::CreateEx](#createex) anstelle von **erstellen**.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="createex"></a>CToolTipCtrl::CreateEx  
 Erstellt ein Steuerelement (ein untergeordnetes Fenster), und ordnen sie die `CToolTipCtrl` Objekt.  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwStyle = 0,  
    DWORD dwStyleEx = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentWnd`  
 Ein Zeiger auf das Fenster, das das Steuerelement übergeordnet ist.  
  
 `dwStyle`  
 Gibt den QuickInfo-Steuerelements-Stil. Finden Sie unter der **"Hinweise"** Abschnitt [erstellen](#create) Weitere Informationen.  
  
 *dwStyleEx*  
 Gibt den erweiterten Stil des Steuerelements erstellt wird. Eine Liste der erweiterten Fensterstile, finden Sie unter der `dwExStyle` -Parameter für [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL bei Erfolg, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von **erstellen** anzuwendende erweiterten Fensterstile, angegeben durch die Windows-erweiterten Stil ihm etwas voranzustellen **WS_EX_**.  
  
##  <a name="ctooltipctrl"></a>CToolTipCtrl::CToolTipCtrl  
 Erstellt ein `CToolTipCtrl`-Objekt.  
  
```  
CToolTipCtrl();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie **erstellen** nach dem Erstellen des Objekts.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#74](../../mfc/codesnippet/cpp/ctooltipctrl-class_1.h)]  
  
##  <a name="deltool"></a>CToolTipCtrl::DelTool  
 Entfernt das Tool gemäß `pWnd` und `nIDTool` aus der Auflistung der Tools, die durch ein QuickInfo-Steuerelement unterstützt.  
  
```  
void DelTool(
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Ein Zeiger auf das Fenster, das Tool enthält.  
  
 `nIDTool`  
 Die ID des Tools.  
  
##  <a name="getbubblesize"></a>CToolTipCtrl::GetBubbleSize  
 Ruft die Größe der QuickInfo ab.  
  
```  
CSize GetBubbleSize(LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpToolInfo`  
 Ein Zeiger auf der QuickInfo [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe der QuickInfo.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_GETBUBBLESIZE](http://msdn.microsoft.com/library/windows/desktop/bb760387)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="getcurrenttool"></a>CToolTipCtrl::GetCurrentTool  
 Ruft Informationen wie Größe, Position und Text, der das QuickInfo-Fenster, das im aktuellen QuickInfo-Steuerelement angezeigt wird.  
  
```  
BOOL GetCurrentTool(LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] `lpToolInfo`|Zeiger auf eine [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) -Struktur, die Informationen zu den aktuellen QuickInfo-Fenster empfängt.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die Informationen erfolgreich abgerufen wird; andernfalls`false.`  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TTM_GETCURRENTTOOL](http://msdn.microsoft.com/library/windows/desktop/bb760389) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel ruft Informationen zu den aktuellen QuickInfo-Fenster ab.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1#6](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_2.cpp)]  
  
##  <a name="getdelaytime"></a>CToolTipCtrl::GetDelayTime  
 Ruft den ersten, Popup und Wiederholungsdauern, die derzeit für ein QuickInfo-Steuerelement festgelegt.  
  
```  
int GetDelayTime(DWORD dwDuration) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `dwDuration`  
 Flag, die angibt, welche Duration-Wert abgerufen wird. Dieser Parameter kann einen der folgenden Werte sein:  
  
- `TTDT_AUTOPOP`Rufen Sie die Zeitdauer, die das QuickInfo-Fenster sichtbar bleibt, wenn der Mauszeiger innerhalb des Tools umschließenden Rechtecks nicht bewegt wird.  
  
- `TTDT_INITIAL`Rufen Sie die Zeitdauer, die der Zeiger innerhalb des Tools umschließenden Rechtecks verbleiben muss, bevor das QuickInfo-Fenster angezeigt wird.  
  
- `TTDT_RESHOW`Rufen Sie die Länge der Zeitaufwand für nachfolgende Tipp Toolfenster angezeigt werden, während der Zeiger zwischen den beiden Tools zu einem anderen verschoben.  
  
### <a name="return-value"></a>Rückgabewert  
 Die angegebene Verzögerung in Millisekunden  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_GETDELAYTIME](http://msdn.microsoft.com/library/windows/desktop/bb760390)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="getmargin"></a>CToolTipCtrl::GetMargin  
 Ruft ab, der nach oben, links, unteren und rechten Ränder, legen Sie für ein QuickInfo-Fenster.  
  
```  
void GetMargin(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lprc`  
 Adresse von einem `RECT` -Struktur, die die Randinformationen erhält. Die Mitglieder der [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur kein umschließendes Rechteck definiert. Strukturmember werden für diese Nachricht wie folgt interpretiert:  
  
|Member|Darstellung|  
|------------|--------------------|  
|**top**|Abstand zwischen dem oberen Rand "und" Top "des QuickInfo-Text, in Pixel.|  
|**left**|Der Abstand zwischen linkem Rahmen und linken Ende der QuickInfo-Text, in Pixel.|  
|**unten**|Der Abstand zwischen unterem Rahmen und unteren Rand in Pixel der QuickInfo-Text.|  
|**right**|Der Abstand zwischen rechtem Rahmen und rechts neben dem QuickInfo-Text, in Pixel.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_GETMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb760391)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="getmaxtipwidth"></a>CToolTipCtrl::GetMaxTipWidth  
 Ruft die maximale Breite für ein QuickInfo-Fenster ab.  
  
```  
int GetMaxTipWidth() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Breite für ein QuickInfo-Fenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_GETMAXTIPWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760392)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="gettext"></a>CToolTipCtrl::GetText  
 Ruft den Text, den ein QuickInfo-Steuerelement für ein Tool verwaltet.  
  
```  
void GetText(
    CString& str,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `str`  
 Ein Verweis auf eine `CString` -Objekt, das Tool Text empfängt.  
  
 `pWnd`  
 Ein Zeiger auf das Fenster, das Tool enthält.  
  
 `nIDTool`  
 Die ID des Tools.  
  
### <a name="remarks"></a>Hinweise  
 Die `pWnd` und `nIDTool` Parameter zu identifizieren, das Tool. Dieses Tool zuvor mit der QuickInfo-Steuerelement durch einen vorherigen Aufruf von registriert wurde, **CToolTipCtrl::AddTool**, das Objekt verweist die `str` Parameter ist das Tool Text zugewiesen.  
  
##  <a name="gettipbkcolor"></a>CToolTipCtrl::GetTipBkColor  
 Ruft die Farbe des Hintergrunds in ein QuickInfo-Fenster ab.  
  
```  
COLORREF GetTipBkColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert, der die Hintergrundfarbe darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_GETTIPBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760394)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="gettiptextcolor"></a>CToolTipCtrl::GetTipTextColor  
 Ruft die Textfarbe in ein QuickInfo-Fenster ab.  
  
```  
COLORREF GetTipTextColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert, der die Farbe des Textes darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_GETTIPTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760395)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="gettitle"></a>CToolTipCtrl::GetTitle  
 Ruft den Titel des aktuellen QuickInfo-Steuerelements ab.  
  
```  
void GetTitle(PTTGETTITLE pttgt) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] `pttgt`|Zeiger auf eine [TTGETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760260) -Struktur, die Informationen über das QuickInfo-Steuerelement enthält. Bei der Rückgabe dieser Methode die `pszTitle` Mitglied der [TTGETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760260) Struktur verweist auf den Text des Titels.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TTM_GETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760396) Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="gettoolcount"></a>CToolTipCtrl::GetToolCount  
 Ruft die Anzahl der Tools registriert das QuickInfo-Steuerelement ab.  
  
```  
int GetToolCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Anzahl der Tools registriert das QuickInfo-Steuerelement.  
  
##  <a name="gettoolinfo"></a>CToolTipCtrl::GetToolInfo  
 Ruft ab, der ein QuickInfo-Steuerelement verwaltet Informationen zu einem Tool aus.  
  
```  
BOOL GetToolInfo(
    CToolInfo& ToolInfo,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *ToolInfo*  
 Ein Verweis auf eine `TOOLINFO` -Objekt, das Tool Text empfängt.  
  
 `pWnd`  
 Ein Zeiger auf das Fenster, das Tool enthält.  
  
 `nIDTool`  
 Die ID des Tools.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die **Hwnd** und **uId** Mitglied der [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) Struktur verweist *CToolInfo* identifizieren Sie das Tool. Wenn das QuickInfo-Steuerelement durch einen vorherigen Aufruf von diesem Tool registriert wurden `AddTool`, die `TOOLINFO` Struktur wird mit Informationen zum Tool ausgefüllt.  
  
##  <a name="hittest"></a>CToolTipCtrl::HitTest  
 Testet eine herstellen kann, um zu bestimmen, ob es sich innerhalb des umschließenden Rechtecks des angegebenen Tools ist und wenn dies der Fall ist, Abrufen von Informationen über das Tool an.  
  
```  
BOOL HitTest(
    CWnd* pWnd,  
    CPoint pt,  
    LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Ein Zeiger auf das Fenster, das Tool enthält.  
  
 `pt`  
 Zeiger auf eine `CPoint` Objekt mit den Koordinaten des Punkts, der darauf getestet werden.  
  
 `lpToolInfo`  
 Zeiger auf [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) -Struktur, die Informationen über das Tool enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der durch die Treffertest-Informationen angegebene Punkt innerhalb des Tools umschließenden Rechtecks ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Funktion gibt einen Wert ungleich NULL zurück, die Struktur verweist `lpToolInfo` mit Informationen über das Tool an, innerhalb dessen Rechtecks der Punkt liegt, gefüllt ist.  
  
 Die `TTHITTESTINFO` Struktur ist folgendermaßen definiert:  
  
 `typedef struct _TT_HITTESTINFO { // tthti`  
  
 `HWND hwnd;   // handle of tool or window with tool`  
  
 `POINT pt;    // client coordinates of point to test`  
  
 `TOOLINFO ti; // receives information about the tool`  
  
 `} TTHITTESTINFO, FAR * LPHITTESTINFO;`  
  
 **HWND**  
 Gibt das Tool Handle an.  
  
 **pt**  
 Gibt die Koordinaten eines Punkts an, ob es sich bei der Punkt in des Tools Rechteck umgebenden befindet.  
  
 **ti**  
 Informationen zu diesem Tool. Weitere Informationen zu den `TOOLINFO` -Struktur, finden Sie unter [CToolTipCtrl::GetToolInfo](#gettoolinfo).  
  
##  <a name="pop"></a>CToolTipCtrl::Pop  
 Ein angezeigte QuickInfo-Fenster aus der Ansicht gelöscht.  
  
```  
void Pop();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_POP](http://msdn.microsoft.com/library/windows/desktop/bb760401)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="popup"></a>CToolTipCtrl::Popup  
 Bewirkt, dass das aktuelle QuickInfo-Steuerelement an den Koordinaten der letzten Maus Nachricht angezeigt.  
  
```  
void Popup();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TTM_POPUP](http://msdn.microsoft.com/library/windows/desktop/bb760402) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel zeigt ein QuickInfo-Fenster.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1#7](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_3.cpp)]  
  
##  <a name="relayevent"></a>CToolTipCtrl:: RelayEvent  
 Übergibt eine Maus-Nachricht an ein QuickInfo-Steuerelement für die Verarbeitung.  
  
```  
void RelayEvent(LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Parameter  
 `lpMsg`  
 Zeiger auf eine [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958) -Struktur, die die Nachricht das Relay enthält.  
  
### <a name="remarks"></a>Hinweise  
 Ein QuickInfo-Steuerelement verarbeitet nur die folgenden Meldungen, die an, indem sie gesendet werden `RelayEvent`:  
  
|WM_LBUTTONDOWN|WM_MOUSEMOVE|  
|---------------------|-------------------|  
|`WM_LBUTTONUP`|`WM_RBUTTONDOWN`|  
|`WM_MBUTTONDOWN`|`WM_RBUTTONUP`|  
|`WM_MBUTTONUP`||  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="setdelaytime"></a>CToolTipCtrl::SetDelayTime  
 Legt die Verzögerungszeit für ein QuickInfo-Steuerelement fest.  
  
```  
void SetDelayTime(UINT nDelay);

 
void SetDelayTime(
    DWORD dwDuration,  
    int iTime);
```  
  
### <a name="parameters"></a>Parameter  
 *nDelay*  
 Gibt die neue Verzögerung in Millisekunden an.  
  
 `dwDuration`  
 Flag, die angibt, welche Duration-Wert abgerufen wird. Finden Sie unter [CToolTipCtrl::GetDelayTime](#getdelaytime) eine Beschreibung der gültigen Werte.  
  
 *iTime*  
 Die angegebene Verzögerung in Millisekunden.  
  
### <a name="remarks"></a>Hinweise  
 Die Verzögerung ist die Zeitdauer, die der Cursor auf einem Tool bleiben muss, bevor das QuickInfo-Fenster angezeigt wird. Die Standardzeit für die Verzögerung beträgt 500 Millisekunden.  
  
##  <a name="setmargin"></a>CToolTipCtrl::SetMargin  
 Legt fest, der nach oben, links, unteren und rechten Ränder für ein QuickInfo-Fenster.  
  
```  
void SetMargin(LPRECT lprc);
```  
  
### <a name="parameters"></a>Parameter  
 `lprc`  
 Adresse der einen `RECT` -Struktur, die den Rand Typeninformationen festgelegt werden. Die Mitglieder der `RECT` Struktur kein umschließendes Rechteck definiert. Finden Sie unter [CToolTipCtrl::GetMargin](#getmargin) eine Beschreibung der Randinformationen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_SETMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb760406)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="setmaxtipwidth"></a>CToolTipCtrl::SetMaxTipWidth  
 Legt die maximale Breite für ein QuickInfo-Fenster an.  
  
```  
int SetMaxTipWidth(int iWidth);
```  
  
### <a name="parameters"></a>Parameter  
 *iWidth*  
 Die maximale Tool Tipp-Fensterbreite festgelegt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Tipp maximale Breite.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_SETMAXTIPWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760408)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="settipbkcolor"></a>CToolTipCtrl::SetTipBkColor  
 Legt die Hintergrundfarbe in einem Tipp Toolfenster fest.  
  
```  
void SetTipBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Parameter  
 `clr`  
 Die neue Hintergrundfarbe.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_SETTIPBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760411)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="settiptextcolor"></a>CToolTipCtrl::SetTipTextColor  
 Legt die Textfarbe in einem Tipp Toolfenster fest.  
  
```  
void SetTipTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Parameter  
 `clr`  
 Die neue Textfarbe.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_SETTIPTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760413)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="settitle"></a>CToolTipCtrl::SetTitle  
 Eine QuickInfo hinzugefügt ein Symbol "und" Title Standardzeichenfolge.  
  
```  
BOOL SetTitle(
    UINT uIcon,  
    LPCTSTR lpstrTitle);
```  
  
### <a name="parameters"></a>Parameter  
 *uIcon*  
 Finden Sie unter *Symbol* in [TTM_SETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760414) im Windows SDK.  
  
 *lpstrTitle*  
 Ein Zeiger auf die Titelzeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_SETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760414)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="settoolinfo"></a>CToolTipCtrl::SetToolInfo  
 Legt die Informationen, die eine QuickInfo für ein Tool verwaltet.  
  
```  
void SetToolInfo(LPTOOLINFO lpToolInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `lpToolInfo`  
 Ein Zeiger auf eine [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) -Struktur, die Informationen festzulegende angibt.  
  
##  <a name="settoolrect"></a>CToolTipCtrl::SetToolRect  
 Legt einen neuen umschließenden Rechtecks für ein Tool.  
  
```  
void SetToolRect(
    CWnd* pWnd,  
    UINT_PTR nIDTool,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Ein Zeiger auf das Fenster, das Tool enthält.  
  
 `nIDTool`  
 Die ID des Tools.  
  
 `lpRect`  
 Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die das neue umfassende Rechteck angibt.  
  
##  <a name="setwindowtheme"></a>CToolTipCtrl::SetWindowTheme  
 Legt fest, der die visuelle Darstellung der QuickInfo-Fenster.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Parameter  
 `pszSubAppName`  
 Ein Zeiger auf eine Unicode-Zeichenfolge, die den visuellen Stil festzulegende enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen des die [TTM_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb760418) Nachricht, wie im Windows SDK beschrieben.  
  
##  <a name="update"></a>CToolTipCtrl::Update  
 Erzwingt, dass das aktuelle Tool neu gezeichnet wird.  
  
```  
void Update();
```  
  
##  <a name="updatetiptext"></a>CToolTipCtrl::UpdateTipText  
 Aktualisiert den QuickInfo-Text für dieses Steuerelement Tools.  
  
```  
void UpdateTipText(
    LPCTSTR lpszText,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0);

 
void UpdateTipText(
    UINT nIDText,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszText`  
 Zeiger auf den Text für das Tool.  
  
 `pWnd`  
 Ein Zeiger auf das Fenster, das Tool enthält.  
  
 `nIDTool`  
 Die ID des Tools.  
  
 `nIDText`  
 ID der Zeichenfolgenressource, die den Text für das Tool enthält.  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CToolBar-Klasse](../../mfc/reference/ctoolbar-class.md)
