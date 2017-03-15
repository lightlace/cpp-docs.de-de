---
title: CToolTipCtrl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CToolTipCtrl
dev_langs:
- C++
helpviewer_keywords:
- tool tips [C++], tool tip controls
- data tips [C++]
- CToolTipCtrl class
ms.assetid: 8973f70c-b73a-46c7-908d-758f364b9a97
caps.latest.revision: 20
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
ms.openlocfilehash: 982aae01dc1308896e9c625e2c2e118b65ec2e64
ms.lasthandoff: 02/24/2017

---
# <a name="ctooltipctrl-class"></a>CToolTipCtrl Class
Kapselt die Funktionalität eines ToolTip-Steuerelements. Dabei handelt es sich um ein kleines Popupfenster, das eine einzelne Textzeile anzeigt, die den Zweck eines Tools der Anwendung beschreibt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CToolTipCtrl : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CToolTipCtrl::CToolTipCtrl](#ctooltipctrl)|Erstellt ein `CToolTipCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CToolTipCtrl::Activate](#activate)|Aktiviert und deaktiviert das QuickInfo-Steuerelement.|  
|[CToolTipCtrl::AddTool](#addtool)|Registriert ein Tool mit dem QuickInfo-Steuerelement.|  
|[CToolTipCtrl::AdjustRect](#adjustrect)|Konvertiert zwischen einer QuickInfo-Steuerelements anzeigen Rechteck und das Rechteck im Fenster.|  
|[CToolTipCtrl::Create](#create)|Erstellt ein QuickInfo-Steuerelement und fügt es ein `CToolTipCtrl` Objekt.|  
|[CToolTipCtrl::CreateEx](#createex)|Erstellt ein QuickInfo-Steuerelement mit dem angegebenen erweiterten Fensterstile und fügt es ein `CToolTipCtrl` Objekt.|  
|[CToolTipCtrl::DelTool](#deltool)|Entfernt ein Tool aus dem QuickInfo-Steuerelement.|  
|[CToolTipCtrl::GetBubbleSize](#getbubblesize)|Ruft die Größe der QuickInfo ab.|  
|[CToolTipCtrl::GetCurrentTool](#getcurrenttool)|Ruft Informationen wie Größe, Position und Text, der das QuickInfo-Fenster, in dem das aktuelle QuickInfo-Steuerelement angezeigt.|  
|[CToolTipCtrl::GetDelayTime](#getdelaytime)|Ruft die anfängliche Popupfenster und Reshow Dauer, der derzeit für ein Tool sind QuickInfo-Steuerelement.|  
|[CToolTipCtrl::GetMargin](#getmargin)|Ruft ab, die nach oben, links, unteren und rechten Ränder, die für ein QuickInfo-Fenster festgelegt werden.|  
|[CToolTipCtrl::GetMaxTipWidth](#getmaxtipwidth)|Ruft die maximale Breite für ein QuickInfo-Fenster ab.|  
|[CToolTipCtrl::GetText](#gettext)|Ruft den Text ab, dem ein QuickInfo-Steuerelement für ein Tool verwaltet.|  
|[CToolTipCtrl::GetTipBkColor](#gettipbkcolor)|Ruft die Hintergrundfarbe in ein QuickInfo-Fenster ab.|  
|[CToolTipCtrl::GetTipTextColor](#gettiptextcolor)|Ruft die Farbe des Texts in einem QuickInfo-Fenster ab.|  
|[CToolTipCtrl::GetTitle](#gettitle)|Ruft den Titel des aktuellen Tooltip-Steuerelements ab.|  
|[CToolTipCtrl::GetToolCount](#gettoolcount)|Ruft die Anzahl der Tools, die durch ein QuickInfo-Steuerelement verwaltet.|  
|[CToolTipCtrl::GetToolInfo](#gettoolinfo)|Ruft die Informationen zu einem Tool ein QuickInfo-Steuerelement verwaltet.|  
|[CToolTipCtrl::HitTest](#hittest)|Testet einen Punkt, um festzustellen, ob er das umschließende Rechteck des angegebenen Tools befindet. Wenn dies der Fall ist, ruft Informationen über das Tool ab.|  
|[CToolTipCtrl::Pop](#pop)|Entfernt ein angezeigte QuickInfo-Fenster aus der Ansicht.|  
|[CToolTipCtrl::Popup](#popup)|Bewirkt, dass die aktuelle ToolTip-Steuerelement an den Koordinaten der letzten Maus Meldung angezeigt.|  
|[CToolTipCtrl:: RelayEvent](#relayevent)|Übergibt eine Maus-Nachricht an ein QuickInfo-Steuerelement für die Verarbeitung.|  
|[CToolTipCtrl::SetDelayTime](#setdelaytime)|Legt den ersten, die Popupfenster und Wiederholungsdauern für ein QuickInfo-Steuerelement.|  
|[CToolTipCtrl::SetMargin](#setmargin)|Legt fest, die nach oben, links, unteren und rechten Ränder für ein QuickInfo-Fenster.|  
|[CToolTipCtrl::SetMaxTipWidth](#setmaxtipwidth)|Legt die maximale Breite für ein QuickInfo-Fenster.|  
|[CToolTipCtrl::SetTipBkColor](#settipbkcolor)|Legt die Farbe des Hintergrunds in ein QuickInfo-Fenster fest.|  
|[CToolTipCtrl::SetTipTextColor](#settiptextcolor)|Legt die Farbe des Texts in ein QuickInfo-Fenster fest.|  
|[CToolTipCtrl::SetTitle](#settitle)|Eine QuickInfo hinzugefügt eine Standardzeichenfolge Symbol und dem Titel.|  
|[CToolTipCtrl::SetToolInfo](#settoolinfo)|Die Informationen, die in einer QuickInfo für ein Tool verwaltet fest.|  
|[CToolTipCtrl::SetToolRect](#settoolrect)|Legt ein neues umschließendes Rechteck für ein Tool.|  
|[CToolTipCtrl::SetWindowTheme](#setwindowtheme)|Legt fest, der die visuelle Darstellung der QuickInfo-Fenster.|  
|[CToolTipCtrl::Update](#update)|Erzwingt, dass das aktuelle Tool neu gezeichnet wird.|  
|[CToolTipCtrl::UpdateTipText](#updatetiptext)|Legt den QuickInfo-Text für ein Tool.|  
  
## <a name="remarks"></a>Hinweise  
 Ein "Tool" ist ein Fenster, z. B. ein untergeordnetes Fenster Steuerelement oder eine Anwendung definierte Rechteck im Clientbereich eines Fensters. Eine QuickInfo wird meistens, erscheint nur, wenn der Benutzer platziert den Cursor auf einem Tool und bleibt es für ca. eine halbe Sekunde ausgeblendet. Die QuickInfo wird angezeigt, in der Nähe des Cursors und verschwindet, wenn der Benutzer eine Maustaste klickt oder den Cursor aus dem Tool verschiebt.  
  
 `CToolTipCtrl`Stellt die Funktionalität zu steuern, die Anfangszeit und die Dauer für die QuickInfo die Margin-Breite Zusammenhang mit den QuickInfo-Text, die Breite der das QuickInfo-Fenster selbst und die Hintergrund- und Textfarben der QuickInfo bereit. Eine einzelne QuickInfo-Steuerelements kann Informationen für mehrere Tools bereitstellen.  
  
 Die `CToolTipCtrl` -Klasse stellt die Funktionalität des Windows common QuickInfo-Steuerelements bereit. Dieses Steuerelement (und somit die `CToolTipCtrl` Klasse) ist nur für Programme, die unter Windows 95/98 und Windows NT, Version 3.51 und höher.  
  
 Weitere Informationen zu QuickInfos finden Sie unter [QuickInfos in Windows nicht von CFrameWnd abgeleitet](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).  
  
 Weitere Informationen zur Verwendung von `CToolTipCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CToolTipCtrl](../../mfc/using-ctooltipctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CToolTipCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="a-nameactivatea--ctooltipctrlactivate"></a><a name="activate"></a>CToolTipCtrl::Activate  
 Rufen Sie diese Funktion zum Aktivieren oder deaktivieren ein QuickInfo-Steuerelement.  
  
```  
void Activate(BOOL bActivate);
```  
  
### <a name="parameters"></a>Parameter  
 `bActivate`  
 Gibt an, ob das QuickInfo-Steuerelement aktiviert oder deaktiviert werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bActivate` ist **TRUE**, das Steuerelement aktiviert ist, wenn **FALSE**, es ist deaktiviert.  
  
 Wenn ein QuickInfo-Steuerelement aktiv ist, wird die Informationen über das QuickInfo angezeigt, wenn der Cursor auf einem Tool, das mit dem Steuerelement registriert ist. Wenn sie inaktiv ist, die Informationen über das QuickInfo nicht angezeigt wird, selbst wenn der Cursor auf einem Tool befindet.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="a-nameaddtoola--ctooltipctrladdtool"></a><a name="addtool"></a>CToolTipCtrl::AddTool  
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
 `pWnd`  
 Ein Zeiger auf das Fenster, das Tool enthält.  
  
 `nIDText`  
 ID der Zeichenfolgenressource, die den Text für das Tool enthält.  
  
 *lpRectTool*  
 Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur mit Koordinaten des Tools umschließenden Rechtecks. Die Koordinaten sind relativ zu der oberen linken Ecke des Clientbereichs des Fensters identifizierten `pWnd`.  
  
 `nIDTool`  
 Die ID des Tools.  
  
 `lpszText`  
 Zeiger auf den Text für das Tool. Wenn dieser Parameter den Wert enthält **LPSTR_TEXTCALLBACK**, **TTN_NEEDTEXT** Benachrichtigungsnachrichten werden an das übergeordnete Element des Fensters, `pWnd` verweist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die **LpRectTool** und **nIDTool** beide Parameter gültig sein müssen oder wenn **LpRectTool** NULL ist, **nIDTool** muss 0 sein.  
  
 Ein QuickInfo-Steuerelement kann mehr als ein Tool zugeordnet werden. Rufen Sie diese Funktion, um ein Tool mit dem QuickInfo-Steuerelement zu registrieren, sodass die Daten in der QuickInfo angezeigt wird, wenn der Cursor auf das Tool befindet.  
  
> [!NOTE]
>  Sie können eine QuickInfo auf ein statisches Steuerelement mit festlegen `AddTool`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="a-nameadjustrecta--ctooltipctrladjustrect"></a><a name="adjustrect"></a>CToolTipCtrl::AdjustRect  
 Konvertiert zwischen Text eines QuickInfo-Steuerelements anzeigen Rechteck und das Rechteck im Fenster.  
  
```  
BOOL AdjustRect(
    LPRECT lprc,  
    BOOL bLarger = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `lprc`  
 Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die ein Tool-Tipps im Fenster Rechteck oder eine Anzeigerechteck Text enthält.  
  
 `bLarger`  
 Wenn **TRUE**, `lprc` dient zum Angeben eines Rechtecks mit Text anzeigen, und das entsprechende Fenster Rechteck empfängt. Wenn **FALSE**, `lprc` wird verwendet, um ein Rechteck Fenster angeben und den entsprechenden Text Anzeigerechteck empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn das Rechteck erfolgreich angepasst wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Member-Funktion berechnet eine QuickInfo-Steuerelements Text Anzeigerechteck das Rechteck im Fenster oder das Tool Tipp Fenster Rechteck benötigt ein Anzeigerechteck angegebenen Text angezeigt.  
  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_ADJUSTRECT](http://msdn.microsoft.com/library/windows/desktop/bb760352), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namecreatea--ctooltipctrlcreate"></a><a name="create"></a>CToolTipCtrl::Create  
 Erstellt ein QuickInfo-Steuerelement und fügt es ein `CToolTipCtrl` Objekt.  
  
```  
virtual BOOL Create(CWnd* pParentWnd, DWORD dwStyle = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentWnd`  
 Gibt das QuickInfo-Steuerelement des übergeordneten Fensters, normalerweise eine `CDialog`. Er darf nicht sein **NULL**.  
  
 `dwStyle`  
 Gibt den QuickInfo-Steuerelements-Stil. Finden Sie unter der **Hinweise** Weitere Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CToolTipCtrl` Objekt erfolgreich erstellt wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie eine `CToolTipCtrl` in zwei Schritten. Zunächst rufen Sie den Konstruktor zum Erstellen der `CToolTipCtrl` -Objekt, und rufen Sie dann **erstellen** des QuickInfo-Steuerelements erstellen und diese an die `CToolTipCtrl` Objekt.  
  
 Die `dwStyle` Parameter kann eine beliebige Kombination von [Fensterstile](../../mfc/reference/window-styles.md). Darüber hinaus ein QuickInfo-Steuerelement hat zwei klassenspezifische Stile: **TTS_ALWAYSTIP** und **TTS_NOPREFIX**.  
  
|Stil|Bedeutung|  
|-----------|-------------|  
|**TTS_ALWAYSTIP**|Gibt an, dass die QuickInfo angezeigt wird, wenn der Cursor ein Tool ist, unabhängig davon, ob die QuickInfo-Steuerelements Besitzerfenster aktiv oder inaktiv ist. Ohne dieses Format wird das QuickInfo-Steuerelement angezeigt, wenn Besitzerfenster des Tools aktiv ist, jedoch nicht, wenn er nicht aktiv ist.|  
|**TTS_NOPREFIX**|Dieses Format wird verhindert, dass das System das kaufmännische und-Zeichen (&) Zeichen aus einer Zeichenfolge entfernt. Wenn ein QuickInfo-Steuerelement keinen der **TTS_NOPREFIX** Format, das System automatisch entfernt kaufmännische und-Zeichen, ermöglicht es einer Anwendung auf die gleiche Zeichenfolge als sowohl ein Menüelement und als Text in einer QuickInfo-Steuerelement verwenden.|  
  
 Ein QuickInfo-Steuerelement verfügt über die `WS_POPUP` und **WS_EX_TOOLWINDOW** Fensterstile, unabhängig davon, ob Sie diese angeben, wenn das Steuerelement erstellt.  
  
 Rufen Sie zum Erstellen einer QuickInfo-Steuerelement mit erweiterten Fensterstile [CToolTipCtrl::CreateEx](#createex) anstelle von **erstellen**.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="a-namecreateexa--ctooltipctrlcreateex"></a><a name="createex"></a>CToolTipCtrl::CreateEx  
 Erstellt ein Steuerelement (ein untergeordnetes Fenster), und ordnen sie die `CToolTipCtrl` Objekt.  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwStyle = 0,  
    DWORD dwStyleEx = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentWnd`  
 Ein Zeiger auf das Fenster, das übergeordnete Element des Steuerelements ist.  
  
 `dwStyle`  
 Gibt den QuickInfo-Steuerelements-Stil. Finden Sie unter der **Hinweise** Abschnitt [erstellen](#create) Weitere Informationen.  
  
 *dwStyleEx*  
 Gibt den erweiterten Stil des Steuerelements erstellt wird. Eine Liste der erweiterten Fensterstile, finden Sie unter der `dwExStyle` -Parameter für [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von **erstellen** erweiterten Fensterstile, angegeben durch den Wert der Windows-erweiterten Stil anwenden **WS_EX_**.  
  
##  <a name="a-namectooltipctrla--ctooltipctrlctooltipctrl"></a><a name="ctooltipctrl"></a>CToolTipCtrl::CToolTipCtrl  
 Erstellt ein `CToolTipCtrl`-Objekt.  
  
```  
CToolTipCtrl();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Aufrufen **erstellen** nach dem Erstellen des Objekts.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog&#74;](../../mfc/codesnippet/cpp/ctooltipctrl-class_1.h)]  
  
##  <a name="a-namedeltoola--ctooltipctrldeltool"></a><a name="deltool"></a>CToolTipCtrl::DelTool  
 Entfernt das Tool, das vom angegebenen `pWnd` und `nIDTool` aus der Auflistung von Tools, die durch ein QuickInfo-Steuerelement unterstützt.  
  
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
  
##  <a name="a-namegetbubblesizea--ctooltipctrlgetbubblesize"></a><a name="getbubblesize"></a>CToolTipCtrl::GetBubbleSize  
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
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_GETBUBBLESIZE](http://msdn.microsoft.com/library/windows/desktop/bb760387), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetcurrenttoola--ctooltipctrlgetcurrenttool"></a><a name="getcurrenttool"></a>CToolTipCtrl::GetCurrentTool  
 Ruft Informationen wie Größe, Position und Text, der das QuickInfo-Fenster angezeigt, wenn das aktuelle QuickInfo-Steuerelement an.  
  
```  
BOOL GetCurrentTool(LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] `lpToolInfo`|Zeiger auf eine [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) -Struktur, die Informationen über das aktuelle QuickInfo-Fenster empfängt.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die Informationen erfolgreich abgerufen wird. andernfalls`false.`  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TTM_GETCURRENTTOOL](http://msdn.microsoft.com/library/windows/desktop/bb760389) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel ruft Informationen zu den aktuellen QuickInfo-Fenster ab.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1&6;](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_2.cpp)]  
  
##  <a name="a-namegetdelaytimea--ctooltipctrlgetdelaytime"></a><a name="getdelaytime"></a>CToolTipCtrl::GetDelayTime  
 Ruft den ersten, die Popupfenster und Wiederholungsdauern, die derzeit für ein QuickInfo-Steuerelement festgelegt.  
  
```  
int GetDelayTime(DWORD dwDuration) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `dwDuration`  
 Flag, die angibt, welche Duration-Wert abgerufen wird. Dieser Parameter kann einen der folgenden Werte sein:  
  
- `TTDT_AUTOPOP`Rufen Sie die Zeitdauer, die das QuickInfo-Fenster sichtbar bleibt, wenn der Mauszeiger innerhalb des Tools umschließenden Rechtecks nicht bewegt wird.  
  
- `TTDT_INITIAL`Rufen Sie die Zeitdauer, die der Zeiger in ein Tool umschließende Rechteck verbleiben muss, bevor das QuickInfo-Fenster angezeigt wird.  
  
- `TTDT_RESHOW`Rufen Sie die Länge der Zeitaufwand für nachfolgende QuickInfo-Fenster angezeigt werden, während der Mauszeiger über ein Tool auf einen anderen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die angegebenen Verzögerung in Millisekunden  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_GETDELAYTIME](http://msdn.microsoft.com/library/windows/desktop/bb760390)wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetmargina--ctooltipctrlgetmargin"></a><a name="getmargin"></a>CToolTipCtrl::GetMargin  
 Ruft ab, die oben, links, unteren und rechten Rändern legen Sie für ein QuickInfo-Fenster.  
  
```  
void GetMargin(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lprc`  
 Adresse der eine `RECT` -Struktur, die die Margin-Informationen erhält. Die Mitglieder der [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur ein umschließendes Rechteck definieren. Strukturmember werden im Rahmen dieser Meldung wie folgt interpretiert:  
  
|Member|Darstellung|  
|------------|--------------------|  
|**top**|Abstand zwischen dem oberen Rahmen und dem Anfang der QuickInfo-Text, in Pixel.|  
|**left**|Der Abstand zwischen dem linken Rahmen und linken Ende der QuickInfo-Text in Pixel.|  
|**unten**|Abstand zwischen dem unteren Rahmen und dem unteren Rand in Pixel der QuickInfo-Text.|  
|**right**|Abstand zwischen dem rechten Rand und rechts neben dem QuickInfo-Text, in Pixel.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_GETMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb760391), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetmaxtipwidtha--ctooltipctrlgetmaxtipwidth"></a><a name="getmaxtipwidth"></a>CToolTipCtrl::GetMaxTipWidth  
 Ruft die maximale Breite für ein QuickInfo-Fenster ab.  
  
```  
int GetMaxTipWidth() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Breite für ein QuickInfo-Fenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_GETMAXTIPWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760392), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegettexta--ctooltipctrlgettext"></a><a name="gettext"></a>CToolTipCtrl::GetText  
 Ruft den Text ab, dem ein QuickInfo-Steuerelement für ein Tool verwaltet.  
  
```  
void GetText(
    CString& str,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `str`  
 Ein Verweis auf ein `CString` -Objekt, das Tool Text.  
  
 `pWnd`  
 Ein Zeiger auf das Fenster, das Tool enthält.  
  
 `nIDTool`  
 Die ID des Tools.  
  
### <a name="remarks"></a>Hinweise  
 Die `pWnd` und `nIDTool` Parameter identifiziert das Tool. Dieses Tool, mit dem QuickInfo-Steuerelement durch einen vorherigen Aufruf von zuvor registriert wurde **CToolTipCtrl::AddTool**, das Objekt, das auf der `str` Parameter ist das Tool Text zugewiesen.  
  
##  <a name="a-namegettipbkcolora--ctooltipctrlgettipbkcolor"></a><a name="gettipbkcolor"></a>CToolTipCtrl::GetTipBkColor  
 Ruft die Hintergrundfarbe in ein QuickInfo-Fenster ab.  
  
```  
COLORREF GetTipBkColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) -Wert, der die Hintergrundfarbe darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_GETTIPBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760394), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegettiptextcolora--ctooltipctrlgettiptextcolor"></a><a name="gettiptextcolor"></a>CToolTipCtrl::GetTipTextColor  
 Ruft die Farbe des Texts in einem QuickInfo-Fenster ab.  
  
```  
COLORREF GetTipTextColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert, der die Farbe des Texts darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_GETTIPTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760395), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegettitlea--ctooltipctrlgettitle"></a><a name="gettitle"></a>CToolTipCtrl::GetTitle  
 Ruft den Titel des aktuellen Tooltip-Steuerelements ab.  
  
```  
void GetTitle(PTTGETTITLE pttgt) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] `pttgt`|Zeiger auf eine [TTGETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760260) -Struktur, die Informationen über die ToolTip-Steuerelement enthält. Bei dieser Methode wird die `pszTitle` Mitglied der [TTGETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760260) -Struktur verweist auf den Text des Titels.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TTM_GETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760396) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegettoolcounta--ctooltipctrlgettoolcount"></a><a name="gettoolcount"></a>CToolTipCtrl::GetToolCount  
 Ruft die Anzahl der Tools für das QuickInfo-Steuerelement registriert.  
  
```  
int GetToolCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Anzahl der Tools werden mit dem QuickInfo-Steuerelement registriert.  
  
##  <a name="a-namegettoolinfoa--ctooltipctrlgettoolinfo"></a><a name="gettoolinfo"></a>CToolTipCtrl::GetToolInfo  
 Ruft die Informationen zu einem Tool ein QuickInfo-Steuerelement verwaltet.  
  
```  
BOOL GetToolInfo(
    CToolInfo& ToolInfo,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *ToolInfo*  
 Ein Verweis auf ein `TOOLINFO` -Objekt, das Tool Text.  
  
 `pWnd`  
 Ein Zeiger auf das Fenster, das Tool enthält.  
  
 `nIDTool`  
 Die ID des Tools.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die **Hwnd** und **uId** Mitglieder der [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) auf die Struktur *CToolInfo* identifizieren Sie das Tool. Dieses Tool registriert wurde, mit dem QuickInfo-Steuerelement durch einen vorherigen Aufruf von `AddTool`, `TOOLINFO` Struktur wird mit Informationen zu diesem Tool ausgefüllt.  
  
##  <a name="a-namehittesta--ctooltipctrlhittest"></a><a name="hittest"></a>CToolTipCtrl::HitTest  
 Testet einen Punkt, um zu bestimmen, ob es in das umschließende Rechteck des angegebenen Tools und ggf. Informationen über das Tool abzurufen.  
  
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
 Zeiger auf ein `CPoint` Objekt mit den Koordinaten des Punkts getestet werden soll.  
  
 `lpToolInfo`  
 Zeiger auf [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) -Struktur, die Informationen über das Tool enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, ist der durch die Treffertests Informationen angegebene Punkt innerhalb des Tools umschließenden Rechtecks; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Funktion einen Wert ungleich NULL zurückgibt, die Struktur auf den `lpToolInfo` mit Informationen über das Tool an, innerhalb dessen Rechtecks der Punkt liegt, gefüllt.  
  
 Die `TTHITTESTINFO` Struktur ist wie folgt definiert:  
  
 `typedef struct _TT_HITTESTINFO { // tthti`  
  
 `HWND hwnd;   // handle of tool or window with tool`  
  
 `POINT pt;    // client coordinates of point to test`  
  
 `TOOLINFO ti; // receives information about the tool`  
  
 `} TTHITTESTINFO, FAR * LPHITTESTINFO;`  
  
 **HWND**  
 Gibt das Tool-Handle.  
  
 **pt**  
 Gibt die Koordinaten eines Punkts, wenn der Punkt in des Tools Rechteck umgebenden befindet.  
  
 **ti**  
 Informationen zu diesem Tool. Weitere Informationen zu den `TOOLINFO` -Struktur, finden Sie unter [CToolTipCtrl::GetToolInfo](#gettoolinfo).  
  
##  <a name="a-namepopa--ctooltipctrlpop"></a><a name="pop"></a>CToolTipCtrl::Pop  
 Entfernt ein angezeigte QuickInfo-Fenster aus der Ansicht.  
  
```  
void Pop();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_POP](http://msdn.microsoft.com/library/windows/desktop/bb760401)wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namepopupa--ctooltipctrlpopup"></a><a name="popup"></a>CToolTipCtrl::Popup  
 Bewirkt, dass das aktuelle QuickInfo-Steuerelement an den Koordinaten der letzten Meldung der Maus angezeigt.  
  
```  
void Popup();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TTM_POPUP](http://msdn.microsoft.com/library/windows/desktop/bb760402) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird ein QuickInfo-Fenster angezeigt.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s&#1;7](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_3.cpp)]  
  
##  <a name="a-namerelayeventa--ctooltipctrlrelayevent"></a><a name="relayevent"></a>CToolTipCtrl:: RelayEvent  
 Übergibt eine Maus-Nachricht an ein QuickInfo-Steuerelement für die Verarbeitung.  
  
```  
void RelayEvent(LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Parameter  
 `lpMsg`  
 Zeiger auf eine [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958) -Struktur, die die Nachricht Relay enthält.  
  
### <a name="remarks"></a>Hinweise  
 Ein QuickInfo-Steuerelement verarbeitet nur die folgenden Meldungen, die an diese gesendet werden `RelayEvent`:  
  
|WM_LBUTTONDOWN|WM_MOUSEMOVE|  
|---------------------|-------------------|  
|`WM_LBUTTONUP`|`WM_RBUTTONDOWN`|  
|`WM_MBUTTONDOWN`|`WM_RBUTTONUP`|  
|`WM_MBUTTONUP`||  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="a-namesetdelaytimea--ctooltipctrlsetdelaytime"></a><a name="setdelaytime"></a>CToolTipCtrl::SetDelayTime  
 Legt die Verzögerung für ein QuickInfo-Steuerelement fest.  
  
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
 Die angegebenen Verzögerung in Millisekunden.  
  
### <a name="remarks"></a>Hinweise  
 Die Verzögerung ist die Zeitdauer, die der Cursor auf einem Tool bleiben muss, bevor das QuickInfo-Fenster angezeigt wird. Die Standardzeit für die Verzögerung beträgt 500 Millisekunden.  
  
##  <a name="a-namesetmargina--ctooltipctrlsetmargin"></a><a name="setmargin"></a>CToolTipCtrl::SetMargin  
 Legt fest, die nach oben, links, unteren und rechten Ränder für ein QuickInfo-Fenster.  
  
```  
void SetMargin(LPRECT lprc);
```  
  
### <a name="parameters"></a>Parameter  
 `lprc`  
 Adresse der eine `RECT` -Struktur, die den Rand Informationen festgelegt werden. Die Mitglieder der `RECT` Struktur ein umschließendes Rechteck definieren. Finden Sie unter [CToolTipCtrl::GetMargin](#getmargin) für eine Beschreibung der Margin-Informationen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_SETMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb760406), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetmaxtipwidtha--ctooltipctrlsetmaxtipwidth"></a><a name="setmaxtipwidth"></a>CToolTipCtrl::SetMaxTipWidth  
 Legt die maximale Breite für ein QuickInfo-Fenster.  
  
```  
int SetMaxTipWidth(int iWidth);
```  
  
### <a name="parameters"></a>Parameter  
 *iWidth*  
 Die maximale Tool Tip-Fensterbreite festgelegt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Tipp maximale Breite.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_SETMAXTIPWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760408), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesettipbkcolora--ctooltipctrlsettipbkcolor"></a><a name="settipbkcolor"></a>CToolTipCtrl::SetTipBkColor  
 Legt die Farbe des Hintergrunds in ein QuickInfo-Fenster fest.  
  
```  
void SetTipBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Parameter  
 `clr`  
 Die neue Hintergrundfarbe.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_SETTIPBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760411), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesettiptextcolora--ctooltipctrlsettiptextcolor"></a><a name="settiptextcolor"></a>CToolTipCtrl::SetTipTextColor  
 Legt die Farbe des Texts in ein QuickInfo-Fenster fest.  
  
```  
void SetTipTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Parameter  
 `clr`  
 Die neue Textfarbe.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_SETTIPTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760413), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesettitlea--ctooltipctrlsettitle"></a><a name="settitle"></a>CToolTipCtrl::SetTitle  
 Eine QuickInfo hinzugefügt eine Standardzeichenfolge Symbol und dem Titel.  
  
```  
BOOL SetTitle(
    UINT uIcon,  
    LPCTSTR lpstrTitle);
```  
  
### <a name="parameters"></a>Parameter  
 *uIcon*  
 Finden Sie unter *Symbol* in [TTM_SETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760414) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *lpstrTitle*  
 Zeiger auf die Title-Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TTM_SETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760414), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesettoolinfoa--ctooltipctrlsettoolinfo"></a><a name="settoolinfo"></a>CToolTipCtrl::SetToolInfo  
 Die Informationen, die in einer QuickInfo für ein Tool verwaltet fest.  
  
```  
void SetToolInfo(LPTOOLINFO lpToolInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `lpToolInfo`  
 Ein Zeiger auf eine [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) -Struktur, die Informationen festlegen angibt.  
  
##  <a name="a-namesettoolrecta--ctooltipctrlsettoolrect"></a><a name="settoolrect"></a>CToolTipCtrl::SetToolRect  
 Legt ein neues umschließendes Rechteck für ein Tool.  
  
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
 Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur des neuen umschließenden Rechtecks angeben.  
  
##  <a name="a-namesetwindowthemea--ctooltipctrlsetwindowtheme"></a><a name="setwindowtheme"></a>CToolTipCtrl::SetWindowTheme  
 Legt fest, der die visuelle Darstellung der QuickInfo-Fenster.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Parameter  
 `pszSubAppName`  
 Ein Zeiger auf eine Unicode-Zeichenfolge mit den visuellen Stil fest.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionalität der [TTM_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb760418) angezeigt, wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameupdatea--ctooltipctrlupdate"></a><a name="update"></a>CToolTipCtrl::Update  
 Erzwingt, dass das aktuelle Tool neu gezeichnet wird.  
  
```  
void Update();
```  
  
##  <a name="a-nameupdatetiptexta--ctooltipctrlupdatetiptext"></a><a name="updatetiptext"></a>CToolTipCtrl::UpdateTipText  
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

