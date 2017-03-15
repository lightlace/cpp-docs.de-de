---
title: Klasse CMFCDesktopAlertWnd | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWnd
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertWnd class
ms.assetid: 73a2dd7b-ea84-4ae2-9830-7cf6e8dd2425
caps.latest.revision: 33
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
ms.openlocfilehash: be9d81ffff003119aa7ff9e0cd100c575bd82d36
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdesktopalertwnd-class"></a>CMFCDesktopAlertWnd Class
Die `CMFCDesktopAlertWnd` Klasse implementiert die Funktion ein nicht modales Dialogfeld angezeigt wird, auf dem Bildschirm, um den Benutzer über ein Ereignis informieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCDesktopAlertWnd : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCDesktopAlertWnd::Create](#create)|Erstellt und initialisiert die desktop-Benachrichtigungsfenster.|  
|[CMFCDesktopAlertWnd::GetAnimationSpeed](#getanimationspeed)|Gibt die Geschwindigkeit der Animation.|  
|[CMFCDesktopAlertWnd::GetAnimationType](#getanimationtype)|Gibt den Animationstyp.|  
|[CMFCDesktopAlertWnd::GetAutoCloseTime](#getautoclosetime)|Gibt das Timeout automatisch geschlossen.|  
|[CMFCDesktopAlertWnd::GetCaptionHeight](#getcaptionheight)|Gibt die Höhe der Beschriftung.|  
|[CMFCDesktopAlertWnd::GetDialogSize](#getdialogsize)||  
|[CMFCDesktopAlertWnd::GetLastPos](#getlastpos)|Gibt die letzte gültige Position von desktop-Benachrichtigungsfenster auf dem Bildschirm zurück.|  
|[CMFCDesktopAlertWnd::GetTransparency](#gettransparency)|Gibt die der Transparenzebene zurück.|  
|[CMFCDesktopAlertWnd::HasSmallCaption](#hassmallcaption)|Bestimmt, ob mit der kleinen Überschrift für den desktop-Benachrichtigungsfenster angezeigt wird.|  
|[CMFCDesktopAlertWnd::OnBeforeShow](#onbeforeshow)||  
|[CMFCDesktopAlertWnd::OnClickLinkButton](#onclicklinkbutton)|Vom Framework aufgerufen, wenn der Benutzer eine Linkschaltfläche desktop Warnung im Menü klickt.|  
|[CMFCDesktopAlertWnd::OnCommand](#oncommand)|Das Framework ruft diese Memberfunktion auf, wenn der Benutzer ein Element aus einem Menü auswählt, wenn ein untergeordnetes Steuerelement eine Benachrichtigung sendet oder ein Tastenanschlag Zugriffstaste übersetzt wird. (Überschreibt [Memberfunktion CWnd:: OnCommand](../../mfc/reference/cwnd-class.md#oncommand).)|  
|[CMFCDesktopAlertWnd::OnDraw](#ondraw)||  
|[CMFCDesktopAlertWnd::ProcessCommand](#processcommand)||  
|[CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed)|Geschwindigkeit der neuen Animation.|  
|[CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype)|Legt den Animationstyp fest.|  
|[CMFCDesktopAlertWnd::SetAutoCloseTime](#setautoclosetime)|Legt das Zeitlimit automatisch geschlossen.|  
|[CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption)|Wechselt zwischen normalem und kleine Beschriftungen.|  
|[CMFCDesktopAlertWnd::SetTransparency](#settransparency)|Legt die Transparenz fest.|  
  
## <a name="remarks"></a>Hinweise  
 Ein desktop-Benachrichtigungsfenster transparent sein kann, kann es mit Animationseffekten angezeigt werden und es kann ausgeblendet (nach der angegebenen Verzögerung oder wenn der Benutzer durch Klicken auf die Schaltfläche Schließen schließt).  
  
 Ein desktop-Benachrichtigungsfenster kann auch ein Standarddialogfeld enthalten, die wiederum ein Symbol, der Text (einer Bezeichnung) und einen Link enthält. Alternativ kann ein desktop-Benachrichtigungsfenster ein benutzerdefiniertes Dialogfeld über die Ressourcen der Anwendung enthalten.  
  
 Sie erstellen eine desktop-Benachrichtigungsfenster in zwei Schritten. Zunächst rufen Sie den Konstruktor zum Erstellen der `CMFCDesktopAlertWnd` Objekt. Rufen Sie anschließend die [CMFCDesktopAlertWnd::Create](#create) Memberfunktion, erstellen Sie das Fenster, und fügen Sie es auf die `CMFCDesktopAlertWnd` Objekt.  
  
 Das `CMFCDesktopAlertWnd` Objekt erstellt eine spezielle untergeordnete-Dialogfeld, das den Clientbereich des Fensters Warnung desktop ausfüllt. Das Dialogfeld beinhaltet alle Steuerelemente, die darauf positioniert sind.  
  
 Um ein benutzerdefiniertes Dialogfeld auf die Popup-Fenster anzuzeigen, gehen Sie folgendermaßen vor:  
  
1.  Leiten Sie eine Klasse von `CMFCDesktopAlertDialog` ab.  
  
2.  Erstellen einer untergeordneten Dialogfeldvorlage in den Ressourcen.  
  
3.  Rufen Sie [CMFCDesktopAlertWnd::Create](#create) mithilfe der Ressourcen-ID, der die Dialogfeldvorlage und einen Zeiger auf die Laufzeit-Klasseninformationen der abgeleiteten Klasse.  
  
4.  Programmieren Sie das benutzerdefinierte Dialogfeld behandeln alle Benachrichtigungen, die die gehosteten Steuerelemente stammen oder Programm die gehosteten Steuerelemente diese Benachrichtigungen direkt behandeln.  
  
 Verwenden Sie die folgenden Funktionen zum Steuern des Verhaltens von desktop-Benachrichtigungsfenster:  
  
-   Legen Sie durch Aufrufen der Animationstyp [CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype). Die gültigen Optionen umfassen erweitern und Folie ausblenden.  
  
-   Legen Sie die Geschwindigkeit der Animation Frame durch Aufrufen von [CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed).  
  
-   Legen Sie die Transparenz durch Aufrufen von [CMFCDesktopAlertWnd::SetTransparency](#settransparency).  
  
-   Ändern Sie die Größe der Beschriftung kleine durch Aufrufen von [CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption). Die kleinen Beschriftung ist 7 Pixel hoch.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCDesktopAlertWnd` Klasse zum Konfigurieren einer `CMFCDesktopAlertWnd` Objekt. Das Beispiel zeigt, wie Sie einen Animationstyp festlegen, legen Sie die Transparenz des Popupfensters, anzugeben, dass das Benachrichtigungsfenster eine kleine Beschriftung anzeigen und die Zeit, die verstreicht, bevor die Warnung im Fenster automatisch geschlossen wird. Darüber hinaus wird das Erstellen und initialisieren die desktop-Benachrichtigungsfenster veranschaulicht. Dieser Codeausschnitt ist Teil der [Desktop Warnung Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo&#1;](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwnd-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxDesktopAlertWnd.h  
  
##  <a name="a-namecreatea--cmfcdesktopalertwndcreate"></a><a name="create"></a>CMFCDesktopAlertWnd::Create  
 Erstellt und initialisiert die desktop-Benachrichtigungsfenster.  
  
```  
virtual BOOL Create(
    CWnd* pWndOwner,  
    UINT uiDlgResID,  
    HMENU hMenu = NULL,  
    CPoint ptPos = CPoint(-1,-1),  
    CRuntimeClass* pRTIDlgBar = RUNTIME_CLASS(CMFCDesktopAlertDialog));

 
virtual BOOL Create(
    CWnd* pWndOwner,  
    CMFCDesktopAlertWndInfo& params,  
    HMENU hMenu = NULL,  
    CPoint ptPos = CPoint(-1,-1));
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out]`pWndOwner`  
 Gibt den Besitzer des Fensters Warnung. Dieser Besitzer erhält alle Benachrichtigungen für die desktop-Benachrichtigungsfenster. Dieser Wert darf nicht `NULL` sein.  
  
 [in] `uiDlgResID`  
 Gibt die Ressourcen-ID des Fensters Warnung an.  
  
 [in] `hMenu`  
 Gibt das Menü, das angezeigt wird, wenn der Benutzer auf die Schaltfläche klickt. Wenn `NULL`, die Schaltfläche wird nicht angezeigt.  
  
 [in] `ptPos`  
 Gibt die Ausgangsposition, in dem die Warnung wird angezeigt, die anhand der Bildschirmkoordinaten. Wenn dieser Parameter ist (-1, -1), wird die Warnung im Fenster in der unteren rechten Ecke des Bildschirms angezeigt.  
  
 [in] `pRTIDlgBar`  
 Laufzeit-Klasseninformationen für eine benutzerdefinierte Dialogfeldklasse, die die Warnung Clientbereich abdeckt.  
  
 [in] `params`  
 Gibt Parameter an, die verwendet werden, um eine Warnung im Fenster zu erstellen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Benachrichtigungsfenster erfolgreich erstellt wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um eine Warnung im Fenster zu erstellen. Der Clientbereich des Fensters Warnung enthält ein untergeordnetes Dialogfeld, die alle Steuerelemente hostet, die dem Benutzer angezeigt werden.  
  
 Die erste methodenüberladung erstellt eine Warnung Fenster, das ein untergeordnetes Element enthält, die über die Ressourcen der Anwendung geladen wird. Die erste methodenüberladung kann auch Laufzeit-Klasseninformationen für eine benutzerdefinierte Dialogfeldklasse angeben.  
  
 Die zweite methodenüberladung erstellt ein Benachrichtigungsfenster, die standardmäßig alle Steuerelemente enthält. Sie können angeben, welche Steuerelemente anzeigen, indem Sie ändern die [CMFCDesktopAlertWndInfo Klasse](../../mfc/reference/cmfcdesktopalertwndinfo-class.md).  
  
##  <a name="a-namegetanimationspeeda--cmfcdesktopalertwndgetanimationspeed"></a><a name="getanimationspeed"></a>CMFCDesktopAlertWnd::GetAnimationSpeed  
 Gibt die Geschwindigkeit der Animation.  
  
```  
UINT GetAnimationSpeed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Geschwindigkeit der Animation des Fensters Warnung in Millisekunden.  
  
### <a name="remarks"></a>Hinweise  
 Geschwindigkeit der Animation wird beschrieben, wie schnell die Warnung im Fenster öffnet und schließt.  
  
##  <a name="a-namegetanimationtypea--cmfcdesktopalertwndgetanimationtype"></a><a name="getanimationtype"></a>CMFCDesktopAlertWnd::GetAnimationType  
 Gibt den Animationstyp.  
  
```  
CMFCPopupMenu::ANIMATION_TYPE GetAnimationType();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der folgenden Animationstypen:  
  
- `NO_ANIMATION`  
  
- `UNFOLD`  
  
- `SLIDE`  
  
- `FADE`  
  
- `SYSTEM_DEFAULT_ANIMATION`  
  
##  <a name="a-namegetautoclosetimea--cmfcdesktopalertwndgetautoclosetime"></a><a name="getautoclosetime"></a>CMFCDesktopAlertWnd::GetAutoCloseTime  
 Gibt das Timeout automatisch geschlossen.  
  
```  
int GetAutoCloseTime() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Zeit in Millisekunden, nach denen die Warnung Fenster automatisch geschlossen wird.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um zu bestimmen, wie viel Zeit vergehen soll, bevor die Warnung Fenster automatisch geschlossen wird.  
  
##  <a name="a-namegetcaptionheighta--cmfcdesktopalertwndgetcaptionheight"></a><a name="getcaptionheight"></a>CMFCDesktopAlertWnd::GetCaptionHeight  
 Gibt die Höhe der Beschriftung.  
  
```  
virtual int GetCaptionHeight();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe der Beschriftung in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann in einer abgeleiteten Klasse überschrieben werden. Die Implementierung der beiden: Wert für die Höhe der kleinen Überschrift (7 Pixel) zurückgibt, wenn das Popupfenster angezeigt werden soll der kleinen Überschrift für oder den Wert der Windows-API-Funktion `GetSystemMetrics(SM_CYSMCAPTION)`.  
  
##  <a name="a-namegetlastposa--cmfcdesktopalertwndgetlastpos"></a><a name="getlastpos"></a>CMFCDesktopAlertWnd::GetLastPos  
 Gibt die letzte Position der desktop-Benachrichtigungsfenster auf dem Bildschirm zurück.  
  
```  
CPoint GetLastPos() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Punkt in Bildschirmkoordinaten.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt die letzte gültige Position des Fensters Warnung auf dem Bildschirm.  
  
##  <a name="a-namegettransparencya--cmfcdesktopalertwndgettransparency"></a><a name="gettransparency"></a>CMFCDesktopAlertWnd::GetTransparency  
 Gibt die der Transparenzebene zurück.  
  
```  
BYTE GetTransparency() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Transparenzstufe zwischen 0 und 255. Je höher der Wert, den undurchsichtigeren Fenster.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die aktuelle Transparenzebene des Fensters Warnung abzurufen.  
  
##  <a name="a-namehassmallcaptiona--cmfcdesktopalertwndhassmallcaption"></a><a name="hassmallcaption"></a>CMFCDesktopAlertWnd::HasSmallCaption  
 Bestimmt, ob die desktop-Benachrichtigungsfenster einer kleinen Beschriftung oder eine Beschriftung, die reguläre Größe hat.  
  
```  
BOOL HasSmallCaption() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Popup-Fenster mit einer kleinen Beschriftung angezeigt wird; `FALSE` Wenn Popup-Fenster mit einer normalen Größe Beschriftung angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um festzustellen, ob das Popupfenster einer kleinen Beschriftung oder eine Beschriftung, die reguläre Größe hat. Standardmäßig ist der kleinen Überschrift 7 Pixel hoch. Sie erhalten die Höhe der Beschriftung reguläre Größe durch Aufrufen der Windows-API-Funktion `GetSystemMetrics(SM_CYCAPTION)`.  
  
##  <a name="a-nameonbeforeshowa--cmfcdesktopalertwndonbeforeshow"></a><a name="onbeforeshow"></a>CMFCDesktopAlertWnd::OnBeforeShow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnBeforeShow(CPoint&);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `CPoint&`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonclicklinkbuttona--cmfcdesktopalertwndonclicklinkbutton"></a><a name="onclicklinkbutton"></a>CMFCDesktopAlertWnd::OnClickLinkButton  
 Vom Framework aufgerufen, wenn der Benutzer eine Linkschaltfläche desktop Warnung im Menü klickt.  
  
```  
virtual BOOL OnClickLinkButton(UINT uiCmdID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdID`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, wenn Sie möchten benachrichtigt werden, wenn ein Benutzer auf die Warnung im Fenster den Link klickt.  
  
##  <a name="a-nameoncommanda--cmfcdesktopalertwndoncommand"></a><a name="oncommand"></a>CMFCDesktopAlertWnd::OnCommand  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnCommand(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `wParam`  
 [in] `lParam`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameondrawa--cmfcdesktopalertwndondraw"></a><a name="ondraw"></a>CMFCDesktopAlertWnd::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameprocesscommanda--cmfcdesktopalertwndprocesscommand"></a><a name="processcommand"></a>CMFCDesktopAlertWnd::ProcessCommand  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL ProcessCommand(HWND hwnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hwnd`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetanimationspeeda--cmfcdesktopalertwndsetanimationspeed"></a><a name="setanimationspeed"></a>CMFCDesktopAlertWnd::SetAnimationSpeed  
 Geschwindigkeit der neuen Animation.  
  
```  
void SetAnimationSpeed(UINT nSpeed);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nSpeed`  
 Gibt die neue animationsgeschwindigkeit in Millisekunden.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Geschwindigkeit der Animation für die Warnung Fenster festgelegt. Die Geschwindigkeit der Standardwert ist 30 Millisekunden.  
  
##  <a name="a-namesetanimationtypea--cmfcdesktopalertwndsetanimationtype"></a><a name="setanimationtype"></a>CMFCDesktopAlertWnd::SetAnimationType  
 Legt den Animationstyp fest.  
  
```  
void SetAnimationType(CMFCPopupMenu::ANIMATION_TYPE type);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `type`  
 Gibt den Animationstyp.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Animation festgelegt. Sie können einen der folgenden Werte angeben:  
  
- `NO_ANIMATION`  
  
- `UNFOLD`  
  
- `SLIDE`  
  
- `FADE`  
  
- `SYSTEM_DEFAULT_ANIMATION`  
  
##  <a name="a-namesetautoclosetimea--cmfcdesktopalertwndsetautoclosetime"></a><a name="setautoclosetime"></a>CMFCDesktopAlertWnd::SetAutoCloseTime  
 Legt das Zeitlimit automatisch geschlossen.  
  
```  
void SetAutoCloseTime(int nTime);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nTime`  
 Die Zeit in Millisekunden die, verstreicht, die vor der Warnung im Fenster automatisch geschlossen wird.  
  
### <a name="remarks"></a>Hinweise  
 Die Warnung im Fenster wird nach der angegebenen Zeit automatisch geschlossen, wenn der Benutzer keine Interaktion mit dem Fenster bietet.  
  
##  <a name="a-namesetsmallcaptiona--cmfcdesktopalertwndsetsmallcaption"></a><a name="setsmallcaption"></a>CMFCDesktopAlertWnd::SetSmallCaption  
 Wechselt zwischen kleinen und reguläre Größe Beschriftungen.  
  
```  
void SetSmallCaption(BOOL bSmallCaption = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bSmallCaption`  
 `TRUE`um anzugeben, dass das Benachrichtigungsfenster eine kleine Beschriftung angezeigt; andernfalls `FALSE` angeben, dass die Warnung im Fenster eine reguläre Größe Beschriftung angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Beschriftung für kleine oder reguläre Größe angezeigt. Standardmäßig ist der kleinen Überschrift 7 Pixel hoch. Sie können die Größe der regulären Beschriftung abrufen, durch Aufrufen der Windows-API-Funktion `GetSystemMetrics(SM_CYCAPTION)`.  
  
##  <a name="a-namesettransparencya--cmfcdesktopalertwndsettransparency"></a><a name="settransparency"></a>CMFCDesktopAlertWnd::SetTransparency  
 Legt fest, der die Transparenz der Popup-Fenster.  
  
```  
void SetTransparency(BYTE nTransparency);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nTransparency`  
 Gibt die der Transparenzebene. Dieser Wert muss zwischen 0 und 255 sein. Je höher der Wert, den undurchsichtigeren Fenster.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um die Transparenzebene eines Popup-Fenster festzulegen.  
  
##  <a name="a-namegetdialogsizea--cmfcdesktopalertwndgetdialogsize"></a><a name="getdialogsize"></a>CMFCDesktopAlertWnd::GetDialogSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetDialogSize();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWndInfo-Klasse](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)   
 [CMFCDesktopAlertDialog-Klasse](../../mfc/reference/cmfcdesktopalertdialog-class.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)

