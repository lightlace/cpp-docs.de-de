---
title: CToolTipCtrl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 06f0b78938534f685f14757ca16e5ad2574412f2
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43684806"
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
|[CToolTipCtrl::AddTool](#addtool)|Registriert ein Tool mit dem QuickInfo-Steuerelement.|  
|[CToolTipCtrl::AdjustRect](#adjustrect)|Konvertiert zwischen einer QuickInfo-Steuerelements Text anzeigen Rechteck und das Fenster-Rechteck.|  
|[CToolTipCtrl::Create](#create)|Erstellt ein QuickInfo-Steuerelement, und fügt sie an einer `CToolTipCtrl` Objekt.|  
|[CToolTipCtrl::CreateEx](#createex)|Erstellt ein QuickInfo-Steuerelement mit dem angegebenen erweiterten Stile für Windows und fügt sie an einer `CToolTipCtrl` Objekt.|  
|[CToolTipCtrl::DelTool](#deltool)|Entfernt ein Tool aus dem QuickInfo-Steuerelement.|  
|[CToolTipCtrl::GetBubbleSize](#getbubblesize)|Ruft die Größe der QuickInfo ab.|  
|[CToolTipCtrl::GetCurrentTool](#getcurrenttool)|Ruft Informationen wie Größe, Position und Text, der den QuickInfo-Fenster, das das aktuelle QuickInfo-Steuerelement anzeigt.|  
|[CToolTipCtrl::GetDelayTime](#getdelaytime)|Ruft ab, die ursprüngliche, Popup und Reshow Dauer, die derzeit für ein Tool festgelegt sind QuickInfo-Steuerelement.|  
|[CToolTipCtrl::GetMargin](#getmargin)|Ruft ab, der oben, linken, unteren und rechten Rändern, die für eine QuickInfo-Fenster festgelegt werden.|  
|[CToolTipCtrl::GetMaxTipWidth](#getmaxtipwidth)|Ruft die maximale Breite für ein QuickInfo-Fenster ab.|  
|[CToolTipCtrl::GetText](#gettext)|Ruft den Text ab, dem ein QuickInfo-Steuerelement für ein Tool verwaltet.|  
|[CToolTipCtrl::GetTipBkColor](#gettipbkcolor)|Ruft die Hintergrundfarbe in einer QuickInfo-Fenster ab.|  
|[CToolTipCtrl::GetTipTextColor](#gettiptextcolor)|Ruft die Textfarbe in einer QuickInfo-Fenster ab.|  
|[CToolTipCtrl::GetTitle](#gettitle)|Ruft den Titel des aktuellen QuickInfo-Steuerelements ab.|  
|[CToolTipCtrl::GetToolCount](#gettoolcount)|Ruft die Anzahl der durch ein QuickInfo-Steuerelement verwaltet Tools ab.|  
|[CToolTipCtrl::GetToolInfo](#gettoolinfo)|Ruft ab, der ein QuickInfo-Steuerelement verwaltet Informationen zu einem Tool aus.|  
|[CToolTipCtrl::HitTest](#hittest)|Testet einen Punkt, um festzustellen, ob es das umschließende Rechteck des angegebenen Tools befindet. Wenn dies der Fall ist, ruft Informationen über das Tool ab.|  
|[CToolTipCtrl::Pop](#pop)|Entfernt eine angezeigte QuickInfo-Fenster aus der Ansicht.|  
|[CToolTipCtrl::Popup](#popup)|Bewirkt, dass das aktuelle QuickInfo-Steuerelement an den Koordinaten der Maus letzten Nachricht angezeigt.|  
|[CToolTipCtrl:: RelayEvent](#relayevent)|Übergibt eine Maus-Nachricht an ein QuickInfo-Steuerelement für die Verarbeitung.|  
|[CToolTipCtrl::SetDelayTime](#setdelaytime)|Legt den ersten, Popup und Wiederholungsdauern für ein QuickInfo-Steuerelement.|  
|[CToolTipCtrl::SetMargin](#setmargin)|Legt fest, der oben, linken, unteren und rechten Rändern für ein QuickInfo-Fenster.|  
|[CToolTipCtrl::SetMaxTipWidth](#setmaxtipwidth)|Legt die maximale Breite für ein QuickInfo-Fenster fest.|  
|[CToolTipCtrl::SetTipBkColor](#settipbkcolor)|Legt die Farbe des Hintergrunds in ein QuickInfo-Fenster fest.|  
|[CToolTipCtrl::SetTipTextColor](#settiptextcolor)|Legt die Textfarbe in einer QuickInfo-Fenster fest.|  
|[CToolTipCtrl::SetTitle](#settitle)|Fügt eine Standardzeichenfolge Symbol und dem Titel, eine QuickInfo an.|  
|[CToolTipCtrl::SetToolInfo](#settoolinfo)|Legt fest, die Informationen, die eine QuickInfo für ein Tool verwaltet.|  
|[CToolTipCtrl::SetToolRect](#settoolrect)|Legt ein neues umschließendes Rechteck für ein Tool an.|  
|[CToolTipCtrl::SetWindowTheme](#setwindowtheme)|Legt fest, der die visuelle Darstellung der QuickInfo-Fenster.|  
|[CToolTipCtrl::Update](#update)|Erzwingt, dass die aktuelle Tools neu gezeichnet wird.|  
|[CToolTipCtrl::UpdateTipText](#updatetiptext)|Legt den QuickInfo-Text für ein Tool fest.|  
  
## <a name="remarks"></a>Hinweise  
 Ein "Tool" ist entweder ein Fenster, z. B. eines untergeordneten Fensters oder Steuerelements einen anwendungsdefinierten rechteckigen Bereich im Clientbereich eines Fensters. Eine QuickInfo wird ausgeblendet, in den meisten Fällen, angezeigt werden, nur, wenn der Benutzer platziert den Cursor auf einem Tool und bewirkt, dass sie es für ca. eine halbe Sekunde. Die QuickInfo wird angezeigt, in der Nähe des Cursors und verschwindet, wenn der Benutzer eine Maustaste klickt oder den Cursor aus dem Tool verschiebt.  
  
 `CToolTipCtrl` Stellt die Funktionalität, um zu steuern, die die Anfangszeit und die Dauer der QuickInfo, die Margin-Breite Zusammenhang mit den QuickInfo-Text, die Breite des das QuickInfo-Fenster selbst und die Hintergrund- und Textfarbe der QuickInfo bereit. Ein einzelnes QuickInfo-Steuerelement kann es sich um Informationen zu mehr als ein Tool bereit.  
  
 Die `CToolTipCtrl` Klasse stellt die Funktionalität Windows allgemeine QuickInfo-Steuerelements bereit. Dieses Steuerelement (und somit die `CToolTipCtrl` Klasse) ist nur für Programme, die unter Versionen des Windows 95/98 und Windows NT 3.51 und höher.  
  
 Weitere Informationen zu QuickInfos finden Sie unter [QuickInfos in Windows nicht von CFrameWnd abgeleitet](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).  
  
 Weitere Informationen zur Verwendung von `CToolTipCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CToolTipCtrl](../../mfc/using-ctooltipctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CToolTipCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="activate"></a>  CToolTipCtrl::Activate  
 Rufen Sie diese Funktion aktivieren oder deaktivieren ein QuickInfo-Steuerelement.  
  
```  
void Activate(BOOL bActivate);
```  
  
### <a name="parameters"></a>Parameter  
 *bActivate*  
 Gibt an, ob das QuickInfo-Steuerelement aktiviert oder deaktiviert wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn *bActivate* ist "true", das Steuerelement aktiviert ist; Wenn FALSE, wird es deaktiviert.  
  
 Wenn ein QuickInfo-Steuerelement aktiv ist, wird der dem QuickInfo-Informationen angezeigt, wenn der Cursor auf einem Tool befindet, die mit dem Steuerelement registriert ist; Wenn sie inaktiv ist, die dem QuickInfo-Informationen nicht angezeigt wird, selbst wenn sich der Cursor auf einem Tool befindet.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="addtool"></a>  CToolTipCtrl::AddTool  
 Registriert ein Tool mit dem QuickInfo-Steuerelement.  
  
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
 *Aufnehmen*  
 Zeiger auf das Fenster, das Tool enthält.  
  
 *nIDText*  
 ID der Zeichenfolgenressource, die den Text für das Tool enthält.  
  
 *lpRectTool*  
 Zeiger auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur mit der Koordinaten des Tools umschließenden Rechtecks. Die Koordinaten sind relativ zu der oberen linken Ecke des Clientbereichs des Fensters identifizierte *aufnehmen*.  
  
 *nIDTool*  
 Die ID des Tools.  
  
 *lpszText*  
 Zeiger auf den Text für das Tool. Wenn dieser Parameter den Wert LPSTR_TEXTCALLBACK enthält, wechseln Sie TTN_NEEDTEXT-Benachrichtigung an das übergeordnete Element des Fensters, *aufnehmen* verweist auf.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die *LpRectTool* und *nIDTool* Parameter müssen beide gültig sein, oder wenn *LpRectTool* NULL ist, *nIDTool* muss 0 sein.  
  
 Ein QuickInfo-Steuerelement kann mehr als ein Tool zugeordnet werden. Rufen Sie diese Funktion, um ein Tool für das QuickInfo-Steuerelement, zu registrieren, sodass die Informationen gespeichert, in der QuickInfo angezeigt wird, wenn der Cursor auf das Tool befindet.  
  
> [!NOTE]
>  Sie können eine QuickInfo auf ein statisches Steuerelement mit festlegen `AddTool`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="adjustrect"></a>  CToolTipCtrl::AdjustRect  
 Konvertiert zwischen Text eine QuickInfo-Steuerelements anzeigen Rechteck und das Fenster-Rechteck.  
  
```  
BOOL AdjustRect(
    LPRECT lprc,  
    BOOL bLarger = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *lprc*  
 Zeiger auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die entweder ein Tool QuickInfo-Fenster Rechteck oder eine Anzeigerechteck Text enthält.  
  
 *bLarger*  
 True gibt an, *Lprc* dient zum Angeben eines Rechtecks Anzeigen von Text und das entsprechende fensterrechtecke erhält. False gibt an, *Lprc* dient zum Angeben eines Rechtecks Fenster, und das entsprechende Textfeld Anzeigerechteck erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Rechteck, erfolgreich angepasst wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Member-Funktion berechnet eine QuickInfo-Steuerelements Text Anzeigerechteck aus dessen fensterrechtecke oder das Tool Tipp fensterrechtecke erforderlich, um einen angegebenen Text Anzeigerechteck anzuzeigen.  
  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_ADJUSTRECT](/windows/desktop/Controls/ttm-adjustrect), wie im Windows SDK beschrieben.  
  
##  <a name="create"></a>  CToolTipCtrl::Create  
 Erstellt ein QuickInfo-Steuerelement, und fügt sie an einer `CToolTipCtrl` Objekt.  
  
```  
virtual BOOL Create(CWnd* pParentWnd, DWORD dwStyle = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *pParentWnd*  
 Gibt an, das QuickInfo-Steuerelement des übergeordneten Fensters, in der Regel eine `CDialog`. Es darf nicht NULL sein.  
  
 *dwStyle*  
 Gibt den QuickInfo-Steuerelements-Stil. Finden Sie unter den **"Hinweise"** Abschnitt, um weitere Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CToolTipCtrl` Objekt ist, wurde erfolgreich erstellt wurde, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CToolTipCtrl` in zwei Schritten. Rufen Sie zunächst den Konstruktor zum Erstellen der `CToolTipCtrl` Objekt aus, und rufen dann `Create` erstellen das QuickInfo-Steuerelement, und fügen Sie ihn auf die `CToolTipCtrl` Objekt.  
  
 Die *DwStyle* Parameter kann eine beliebige Kombination von sein [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles). Darüber hinaus gelten für ein QuickInfo-Steuerelement zwei mandantenklassen geltenden schemaanpassungen Stile: TTS_ALWAYSTIP und TTS_NOPREFIX.  
  
|Stil|Bedeutung|  
|-----------|-------------|  
|TTS_ALWAYSTIP|Gibt an, der die QuickInfo angezeigt wird, wenn der Cursor auf einem Tool, unabhängig davon, ob das QuickInfo-Steuerelement die besitzende Fenster aktiv oder inaktiv ist. Ohne diesen Stil wird das QuickInfo-Steuerelement angezeigt, wenn das besitzende Fenster des aktiv ist, aber nicht, wenn sie inaktiv ist.|  
|TTS_NOPREFIX|Dieses Format wird verhindert, dass das System das kaufmännische und-Zeichen aus einer Zeichenfolge (&) zu beschränken. Wenn ein QuickInfo-Steuerelement keinen styl TTS_NOPREFIX, entfernt das System automatisch kaufmännische und-Zeichen, dem eine Anwendung die gleiche Zeichenfolge als sowohl ein Menüelement und als Text in ein QuickInfo-Steuerelement zu verwenden.|  
  
 Ein QuickInfo-Steuerelement verfügt über die WS_POPUP und WS_EX_TOOLWINDOW Window-Stile, unabhängig davon, ob Sie sie angeben, wenn das Steuerelement erstellt.  
  
 Rufen Sie zum Erstellen einer QuickInfo-Steuerelement mit erweiterten Fensterstile [CToolTipCtrl::CreateEx](#createex) anstelle von `Create`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="createex"></a>  CToolTipCtrl::CreateEx  
 Erstellt ein Steuerelement (ein untergeordnetes Fenster), und ordnen Sie sie der `CToolTipCtrl` Objekt.  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwStyle = 0,  
    DWORD dwStyleEx = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *pParentWnd*  
 Ein Zeiger auf das Fenster, das übergeordnete Element des Steuerelements ist.  
  
 *dwStyle*  
 Gibt den QuickInfo-Steuerelements-Stil. Finden Sie unter den **"Hinweise"** Abschnitt [erstellen](#create) für Weitere Informationen.  
  
 *dwStyleEx*  
 Gibt den erweiterten Stil des Steuerelements erstellt wird. Eine Liste der erweiterten Windows-Stile, finden Sie unter den *DwExStyle* -Parameter für [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von `Create` anzuwendende Erweiterte Windows-Stile, angegeben durch den Wert der Windows-erweiterten Stil **WS_EX_**.  
  
##  <a name="ctooltipctrl"></a>  CToolTipCtrl::CToolTipCtrl  
 Erstellt ein `CToolTipCtrl`-Objekt.  
  
```  
CToolTipCtrl();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `Create` nach dem Erstellen des Objekts.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#74](../../mfc/codesnippet/cpp/ctooltipctrl-class_1.h)]  
  
##  <a name="deltool"></a>  CToolTipCtrl::DelTool  
 Entfernt das Tool gemäß *aufnehmen* und *nIDTool* aus der Sammlung von Tools, die durch ein QuickInfo-Steuerelement unterstützt.  
  
```  
void DelTool(
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *Aufnehmen*  
 Zeiger auf das Fenster, das Tool enthält.  
  
 *nIDTool*  
 Die ID des Tools.  
  
##  <a name="getbubblesize"></a>  CToolTipCtrl::GetBubbleSize  
 Ruft die Größe der QuickInfo ab.  
  
```  
CSize GetBubbleSize(LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *lpToolInfo*  
 Ein Zeiger auf der QuickInfo [TOOLINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtoolinfoa) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe der QuickInfo.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_GETBUBBLESIZE](/windows/desktop/Controls/ttm-getbubblesize), wie im Windows SDK beschrieben.  
  
##  <a name="getcurrenttool"></a>  CToolTipCtrl::GetCurrentTool  
 Ruft die Informationen, z. B. die Größe, Position und Text, der das QuickInfo-Fenster angezeigt, die für das aktuelle QuickInfo-Steuerelement ab.  
  
```  
BOOL GetCurrentTool(LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] *LpToolInfo*|Zeiger auf eine [TOOLINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtoolinfoa) -Struktur, die Informationen über das aktuelle QuickInfo-Fenster empfängt.|  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Informationen erfolgreich abgerufen wird. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TTM_GETCURRENTTOOL](/windows/desktop/Controls/ttm-getcurrenttool) -Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel ruft Informationen über das aktuelle QuickInfo-Fenster ab.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1#6](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_2.cpp)]  
  
##  <a name="getdelaytime"></a>  CToolTipCtrl::GetDelayTime  
 Ruft den ersten, Popup und Wiederholungsdauern, die derzeit für ein QuickInfo-Steuerelement festgelegt.  
  
```  
int GetDelayTime(DWORD dwDuration) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *dwDuration*  
 Flag, die angibt, welche Duration-Wert abgerufen wird. Dieser Parameter kann einen der folgenden Werte sein:  
  
- TTDT_AUTOPOP abrufen, bleibt die Zeitspanne, die den QuickInfo-Fenster angezeigt, wenn der Zeiger innerhalb der umschließenden Rechtecks des Tools nicht bewegt wird.  
  
- TTDT_INITIAL abzurufen, wird die Zeitspanne, die der Zeiger innerhalb der umschließenden Rechtecks des Tools, bevor das QuickInfo-Fenster feststehend bleiben soll muss angezeigt.  
  
- TTDT_RESHOW abrufen verschiebt die Länge des Zeitaufwands für nachfolgende QuickInfo-Fenster als des Zeigers angezeigt werden, von einem einzigen Tool.  
  
### <a name="return-value"></a>Rückgabewert  
 Die angegebene Verzögerungszeit in Millisekunden  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_GETDELAYTIME](/windows/desktop/Controls/ttm-getdelaytime), wie im Windows SDK beschrieben.  
  
##  <a name="getmargin"></a>  CToolTipCtrl::GetMargin  
 Ruft ab, der oben, linken, unteren und rechten Rändern legen Sie für eine QuickInfo-Fenster.  
  
```  
void GetMargin(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *lprc*  
 Adresse von einem `RECT` -Struktur, die die Informationen im Indikatorrand erhält. Die Mitglieder der [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur ist kein umschließendes Rechteck definiert. Im Rahmen dieser Meldung sind die Strukturmember wie folgt interpretiert:  
  
|Member|Darstellung|  
|------------|--------------------|  
|`top`|Abstand zwischen dem oberen Rahmen und dem oberen Rand der QuickInfo-Text, in Pixel.|  
|`left`|Der Abstand zwischen linkem Rahmen und linken Ende des QuickInfo-Text, in Pixel.|  
|`bottom`|Abstand zwischen dem unteren Rahmen und dem unteren Rand in Pixel der QuickInfo-Text.|  
|`right`|Der Abstand zwischen rechtem Rahmen und das rechte Ende der QuickInfo-Text, in Pixel.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_GETMARGIN](/windows/desktop/Controls/ttm-getmargin), wie im Windows SDK beschrieben.  
  
##  <a name="getmaxtipwidth"></a>  CToolTipCtrl::GetMaxTipWidth  
 Ruft die maximale Breite für ein QuickInfo-Fenster ab.  
  
```  
int GetMaxTipWidth() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Breite für ein QuickInfo-Fenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_GETMAXTIPWIDTH](/windows/desktop/Controls/ttm-getmaxtipwidth), wie im Windows SDK beschrieben.  
  
##  <a name="gettext"></a>  CToolTipCtrl::GetText  
 Ruft den Text ab, dem ein QuickInfo-Steuerelement für ein Tool verwaltet.  
  
```  
void GetText(
    CString& str,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *str*  
 Ein Verweis auf eine `CString` -Objekt, das Tool den Text empfängt.  
  
 *Aufnehmen*  
 Zeiger auf das Fenster, das Tool enthält.  
  
 *nIDTool*  
 Die ID des Tools.  
  
### <a name="remarks"></a>Hinweise  
 Die *aufnehmen* und *nIDTool* Parameter identifiziert das Tool. Wenn Sie dieses Tool in der QuickInfo-Steuerelement durch einen vorherigen Aufruf von zuvor registriert wurde `CToolTipCtrl::AddTool`, das Objekt, das auf die *str* Parameter ist das Tool den Text zugewiesen.  
  
##  <a name="gettipbkcolor"></a>  CToolTipCtrl::GetTipBkColor  
 Ruft die Hintergrundfarbe in einer QuickInfo-Fenster ab.  
  
```  
COLORREF GetTipBkColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COLORREF](/windows/desktop/gdi/colorref) Wert, der die Hintergrundfarbe darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_GETTIPBKCOLOR](/windows/desktop/Controls/ttm-gettipbkcolor), wie im Windows SDK beschrieben.  
  
##  <a name="gettiptextcolor"></a>  CToolTipCtrl::GetTipTextColor  
 Ruft die Textfarbe in einer QuickInfo-Fenster ab.  
  
```  
COLORREF GetTipTextColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COLORREF](/windows/desktop/gdi/colorref) Wert, der die Textfarbe darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_GETTIPTEXTCOLOR](/windows/desktop/Controls/ttm-gettiptextcolor), wie im Windows SDK beschrieben.  
  
##  <a name="gettitle"></a>  CToolTipCtrl::GetTitle  
 Ruft den Titel des aktuellen QuickInfo-Steuerelements ab.  
  
```  
void GetTitle(PTTGETTITLE pttgt) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] *Pttgt*|Zeiger auf eine [TTGETTITLE](/windows/desktop/api/commctrl/ns-commctrl-_ttgettitle) -Struktur, die Informationen über das QuickInfo-Steuerelement enthält. Bei der Rückgabe dieser Methode die *PszTitle* Mitglied der [TTGETTITLE](/windows/desktop/api/commctrl/ns-commctrl-_ttgettitle) Struktur zeigt auf den Text des Titels.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TTM_GETTITLE](/windows/desktop/Controls/ttm-gettitle) -Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="gettoolcount"></a>  CToolTipCtrl::GetToolCount  
 Ruft die Anzahl von den Tools, die das QuickInfo-Steuerelement registriert.  
  
```  
int GetToolCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Anzahl von Tools, die bei das QuickInfo-Steuerelement registriert werden.  
  
##  <a name="gettoolinfo"></a>  CToolTipCtrl::GetToolInfo  
 Ruft ab, der ein QuickInfo-Steuerelement verwaltet Informationen zu einem Tool aus.  
  
```  
BOOL GetToolInfo(
    CToolInfo& ToolInfo,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *ToolInfo*  
 Ein Verweis auf eine `TOOLINFO` -Objekt, das Tool den Text empfängt.  
  
 *Aufnehmen*  
 Zeiger auf das Fenster, das Tool enthält.  
  
 *nIDTool*  
 Die ID des Tools.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die `hwnd` und `uId` Mitglied der [TOOLINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtoolinfoa) Struktur verweist *CToolInfo* identifizieren Sie das Tool. Wenn dieses Tool, mit dem QuickInfo-Steuerelement durch einen vorherigen Aufruf von registriert wurde `AddTool`, `TOOLINFO` Struktur mit Informationen zu diesem Tool gefüllt ist.  
  
##  <a name="hittest"></a>  CToolTipCtrl::HitTest  
 Testet einen Punkt, um zu bestimmen, ob es das umschließende Rechteck des angegebenen Tools befindet und, wenn dies der Fall ist, rufen Informationen zu diesem Tool.  
  
```  
BOOL HitTest(
    CWnd* pWnd,  
    CPoint pt,  
    LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *Aufnehmen*  
 Zeiger auf das Fenster, das Tool enthält.  
  
 *pt*  
 Zeiger auf eine `CPoint` mit den Koordinaten des Punkts zu testende Objekt.  
  
 *lpToolInfo*  
 Zeiger auf [TOOLINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtoolinfoa) Struktur, die Informationen über das Tool enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich null der durch die Informationen des Treffertests angegebene Punkt innerhalb des Tools umschließenden Rechtecks ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Funktion einen Wert ungleich NULL zurückgibt, die Struktur verweist *LpToolInfo* mit Informationen über das Tool an, innerhalb dessen Rechtecks der Punkt liegt, gefüllt ist.  
  
 Die `TTHITTESTINFO` Struktur ist folgendermaßen definiert:  
  
 `typedef struct _TT_HITTESTINFO { // tthti`  
  
 `HWND hwnd;   // handle of tool or window with tool`  
  
 `POINT pt;    // client coordinates of point to test`  
  
 `TOOLINFO ti; // receives information about the tool`  
  
 `} TTHITTESTINFO, FAR * LPHITTESTINFO;`  
  
 `hwnd`  
 Gibt das Tool den Handle.  
  
 `pt`  
 Gibt die Koordinaten eines Punkts an, ob es sich bei der Punkt umschließenden ist, in des Tools des Rechtecks.  
  
 `ti`  
 Informationen zu diesem Tool. Weitere Informationen zu den `TOOLINFO` Struktur, siehe [CToolTipCtrl::GetToolInfo](#gettoolinfo).  
  
##  <a name="pop"></a>  CToolTipCtrl::Pop  
 Eine angezeigte QuickInfo-Fenster aus der Ansicht gelöscht.  
  
```  
void Pop();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_POP](/windows/desktop/Controls/ttm-pop), wie im Windows SDK beschrieben.  
  
##  <a name="popup"></a>  CToolTipCtrl::Popup  
 Bewirkt, dass das aktuelle QuickInfo-Steuerelement an den Koordinaten der Maus letzten Nachricht angezeigt.  
  
```  
void Popup();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TTM_POPUP](/windows/desktop/Controls/ttm-popup) -Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel zeigt ein QuickInfo-Fenster.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1#7](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_3.cpp)]  
  
##  <a name="relayevent"></a>  CToolTipCtrl:: RelayEvent  
 Übergibt eine Maus-Nachricht an ein QuickInfo-Steuerelement für die Verarbeitung.  
  
```  
void RelayEvent(LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Parameter  
 *lpMsg*  
 Zeiger auf eine [MSG](https://msdn.microsoft.com/library/windows/desktop/ms644958) Struktur, die die Nachricht an das Relay enthält.  
  
### <a name="remarks"></a>Hinweise  
 Ein QuickInfo-Steuerelement verarbeitet nur die folgenden Meldungen, die an sie gesendet werden `RelayEvent`:  
  
|WM_LBUTTONDOWN|WM_MOUSEMOVE|  
|---------------------|-------------------|  
|WM_LBUTTONUP|WM_RBUTTONDOWN|  
|WM_MBUTTONDOWN|WM_RBUTTONUP|  
|WM_MBUTTONUP||  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="setdelaytime"></a>  CToolTipCtrl::SetDelayTime  
 Legt die Verzögerungszeit für ein QuickInfo-Steuerelement fest.  
  
```  
void SetDelayTime(UINT nDelay);

 
void SetDelayTime(
    DWORD dwDuration,  
    int iTime);
```  
  
### <a name="parameters"></a>Parameter  
 *nDelay*  
 Gibt die neue Verzögerungszeit in Millisekunden an.  
  
 *dwDuration*  
 Flag, die angibt, welche Duration-Wert abgerufen wird. Finden Sie unter [CToolTipCtrl::GetDelayTime](#getdelaytime) eine Beschreibung der gültigen Werte.  
  
 *iTime*  
 Die Zeit der angegebenen Verzögerung in Millisekunden.  
  
### <a name="remarks"></a>Hinweise  
 Die Verzögerung ist die Zeitspanne, die der Cursor auf einem Tool bleiben muss, bevor das QuickInfo-Fenster angezeigt wird. Die Standardzeit für die Verzögerung beträgt 500 Millisekunden.  
  
##  <a name="setmargin"></a>  CToolTipCtrl::SetMargin  
 Legt fest, der oben, linken, unteren und rechten Rändern für ein QuickInfo-Fenster.  
  
```  
void SetMargin(LPRECT lprc);
```  
  
### <a name="parameters"></a>Parameter  
 *lprc*  
 Adresse von einem `RECT` -Struktur, enthält die Informationen im Indikatorrand festgelegt werden. Die Mitglieder der `RECT` Struktur ist kein umschließendes Rechteck definiert. Finden Sie unter [CToolTipCtrl::GetMargin](#getmargin) eine Beschreibung der Informationen im Indikatorrand.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_SETMARGIN](/windows/desktop/Controls/ttm-setmargin), wie im Windows SDK beschrieben.  
  
##  <a name="setmaxtipwidth"></a>  CToolTipCtrl::SetMaxTipWidth  
 Legt die maximale Breite für ein QuickInfo-Fenster fest.  
  
```  
int SetMaxTipWidth(int iWidth);
```  
  
### <a name="parameters"></a>Parameter  
 *iWidth*  
 Die maximale Tool Tip-Fensterbreite festgelegt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen maximale Tip-Breite.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_SETMAXTIPWIDTH](/windows/desktop/Controls/ttm-setmaxtipwidth), wie im Windows SDK beschrieben.  
  
##  <a name="settipbkcolor"></a>  CToolTipCtrl::SetTipBkColor  
 Legt die Farbe des Hintergrunds in ein QuickInfo-Fenster fest.  
  
```  
void SetTipBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Parameter  
 *CLR*  
 Die neue Hintergrundfarbe.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_SETTIPBKCOLOR](/windows/desktop/Controls/ttm-settipbkcolor), wie im Windows SDK beschrieben.  
  
##  <a name="settiptextcolor"></a>  CToolTipCtrl::SetTipTextColor  
 Legt die Textfarbe in einer QuickInfo-Fenster fest.  
  
```  
void SetTipTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Parameter  
 *CLR*  
 Die neue Textfarbe.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_SETTIPTEXTCOLOR](/windows/desktop/Controls/ttm-settiptextcolor), wie im Windows SDK beschrieben.  
  
##  <a name="settitle"></a>  CToolTipCtrl::SetTitle  
 Fügt eine Standardzeichenfolge Symbol und dem Titel, eine QuickInfo an.  
  
```  
BOOL SetTitle(
    UINT uIcon,  
    LPCTSTR lpstrTitle);
```  
  
### <a name="parameters"></a>Parameter  
 *uIcon*  
 Finden Sie unter *Symbol* in [TTM_SETTITLE](/windows/desktop/Controls/ttm-settitle) im Windows SDK.  
  
 *lpstrTitle*  
 Zeiger auf die Title-Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_SETTITLE](/windows/desktop/Controls/ttm-settitle), wie im Windows SDK beschrieben.  
  
##  <a name="settoolinfo"></a>  CToolTipCtrl::SetToolInfo  
 Legt fest, die Informationen, die eine QuickInfo für ein Tool verwaltet.  
  
```  
void SetToolInfo(LPTOOLINFO lpToolInfo);
```  
  
### <a name="parameters"></a>Parameter  
 *lpToolInfo*  
 Ein Zeiger auf eine [TOOLINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtoolinfoa) -Struktur, die Informationen festlegen angibt.  
  
##  <a name="settoolrect"></a>  CToolTipCtrl::SetToolRect  
 Legt ein neues umschließendes Rechteck für ein Tool an.  
  
```  
void SetToolRect(
    CWnd* pWnd,  
    UINT_PTR nIDTool,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 *Aufnehmen*  
 Zeiger auf das Fenster, das Tool enthält.  
  
 *nIDTool*  
 Die ID des Tools.  
  
 *lpRect*  
 Zeiger auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die das neue umschließende Rechteck angibt.  
  
##  <a name="setwindowtheme"></a>  CToolTipCtrl::SetWindowTheme  
 Legt fest, der die visuelle Darstellung der QuickInfo-Fenster.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Parameter  
 *pszSubAppName*  
 Ein Zeiger auf eine Unicode-Zeichenfolge mit den visuellen Stil festlegen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen des die [TTM_SETWINDOWTHEME](/windows/desktop/Controls/ttm-setwindowtheme) Nachricht, wie im Windows SDK beschrieben.  
  
##  <a name="update"></a>  CToolTipCtrl::Update  
 Erzwingt, dass die aktuelle Tools neu gezeichnet wird.  
  
```  
void Update();
```  
  
##  <a name="updatetiptext"></a>  CToolTipCtrl::UpdateTipText  
 Aktualisiert den QuickInfo-Text für dieses Steuerelements Tools.  
  
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
 *lpszText*  
 Zeiger auf den Text für das Tool.  
  
 *Aufnehmen*  
 Zeiger auf das Fenster, das Tool enthält.  
  
 *nIDTool*  
 Die ID des Tools.  
  
 *nIDText*  
 ID der Zeichenfolgenressource, die den Text für das Tool enthält.  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CToolBar-Klasse](../../mfc/reference/ctoolbar-class.md)
