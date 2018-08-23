---
title: CMFCDesktopAlertWnd-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::Create
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetCaptionHeight
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetDialogSize
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetLastPos
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetTransparency
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::HasSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnBeforeShow
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnClickLinkButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnDraw
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::ProcessCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetTransparency
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertWnd [MFC], Create
- CMFCDesktopAlertWnd [MFC], GetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], GetAnimationType
- CMFCDesktopAlertWnd [MFC], GetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], GetCaptionHeight
- CMFCDesktopAlertWnd [MFC], GetDialogSize
- CMFCDesktopAlertWnd [MFC], GetLastPos
- CMFCDesktopAlertWnd [MFC], GetTransparency
- CMFCDesktopAlertWnd [MFC], HasSmallCaption
- CMFCDesktopAlertWnd [MFC], OnBeforeShow
- CMFCDesktopAlertWnd [MFC], OnClickLinkButton
- CMFCDesktopAlertWnd [MFC], OnCommand
- CMFCDesktopAlertWnd [MFC], OnDraw
- CMFCDesktopAlertWnd [MFC], ProcessCommand
- CMFCDesktopAlertWnd [MFC], SetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], SetAnimationType
- CMFCDesktopAlertWnd [MFC], SetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], SetSmallCaption
- CMFCDesktopAlertWnd [MFC], SetTransparency
ms.assetid: 73a2dd7b-ea84-4ae2-9830-7cf6e8dd2425
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 09f086673ba015b168211261bed68db479ef77a9
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42540830"
---
# <a name="cmfcdesktopalertwnd-class"></a>CMFCDesktopAlertWnd Class
Die `CMFCDesktopAlertWnd` Klasse implementiert die Funktion ein nicht modales Dialogfeld wird angezeigt, auf dem Bildschirm, um den Benutzer zu einem Ereignis zu informieren.  

 Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.    
## <a name="syntax"></a>Syntax  
  
```  
class CMFCDesktopAlertWnd : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Cmfcdesktopalertwnd:: Create](#create)|Erstellt und initialisiert die desktop-Benachrichtigungsfenster.|  
|[CMFCDesktopAlertWnd::GetAnimationSpeed](#getanimationspeed)|Gibt die animationsgeschwindigkeit zurück.|  
|[CMFCDesktopAlertWnd::GetAnimationType](#getanimationtype)|Gibt den Animationstyp zurück.|  
|[CMFCDesktopAlertWnd::GetAutoCloseTime](#getautoclosetime)|Gibt zurück, das Automatisches Schließen-Timeout.|  
|[CMFCDesktopAlertWnd::GetCaptionHeight](#getcaptionheight)|Gibt die Höhe der Beschriftung.|  
|[CMFCDesktopAlertWnd::GetDialogSize](#getdialogsize)||  
|[CMFCDesktopAlertWnd::GetLastPos](#getlastpos)|Gibt die letzte gültige Position der desktop-Benachrichtigungsfenster auf dem Bildschirm zurück.|  
|[CMFCDesktopAlertWnd::GetTransparency](#gettransparency)|Gibt die der Transparenzebene zurück.|  
|[CMFCDesktopAlertWnd::HasSmallCaption](#hassmallcaption)|Bestimmt, ob die desktop-Benachrichtigungsfenster mit kleiner Beschriftung angezeigt wird.|  
|[CMFCDesktopAlertWnd::OnBeforeShow](#onbeforeshow)||  
|[CMFCDesktopAlertWnd::OnClickLinkButton](#onclicklinkbutton)|Vom Framework aufgerufen, wenn der Benutzer eine Schaltfläche "Link" der desktop im Menü "Warnungen" klickt.|  
|[CMFCDesktopAlertWnd::OnCommand](#oncommand)|Das Framework ruft diese Memberfunktion auf, wenn der Benutzer ein Element aus einem Menü auswählt, wenn ein untergeordnetes Steuerelement eine Benachrichtigung sendet oder ein Accelerator Tastatureingabe übersetzt wird. (Überschreibt [Memberfunktion CWnd:: OnCommand](../../mfc/reference/cwnd-class.md#oncommand).)|  
|[CMFCDesktopAlertWnd::OnDraw](#ondraw)||  
|[CMFCDesktopAlertWnd::ProcessCommand](#processcommand)||  
|[CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed)|Geschwindigkeit der neuen Animation.|  
|[CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype)|Legt den Animationstyp fest.|  
|[CMFCDesktopAlertWnd::SetAutoCloseTime](#setautoclosetime)|Legt das Automatisches Schließen-Timeout fest.|  
|[CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption)|Wechselt zwischen normalem und kleinen Beschriftungen.|  
|[CMFCDesktopAlertWnd::SetTransparency](#settransparency)|Legt die der Transparenzebene fest.|  
  
## <a name="remarks"></a>Hinweise  
 Eine desktop-Benachrichtigungsfenster transparent sein kann, können sie mit Animationseffekten angezeigt werden und können verschwinden, (nach der angegebenen Verzögerung oder wenn der Benutzer es schließt, indem Sie auf die Schaltfläche "Schließen").  
  
 Eine desktop-Benachrichtigungsfenster kann auch ein Standarddialogfeld enthalten, die wiederum ein Symbol, Nachrichtentext (eine Bezeichnung) und einen Link enthält. Alternativ kann eine desktop-Benachrichtigungsfenster ein benutzerdefiniertes Dialogfeld in der Anwendung Ressourcen enthalten.  
  
 Sie erstellen eine desktop-Benachrichtigungsfenster in zwei Schritten. Rufen Sie zunächst den Konstruktor zum Erstellen der `CMFCDesktopAlertWnd` Objekt. Rufen Sie zweitens die [cmfcdesktopalertwnd:: Create](#create) Memberfunktion versucht, erstellen Sie das Fenster, und fügen Sie ihn auf die `CMFCDesktopAlertWnd` Objekt.  
  
 Die `CMFCDesktopAlertWnd` -Objekt erstellt, eine spezielle untergeordnete-Dialogfeld, das den Clientbereich von desktop-Benachrichtigungsfenster ausfüllt. Das Dialogfeld beinhaltet alle Steuerelemente, die darauf positioniert sind.  
  
 Um ein benutzerdefiniertes Dialogfeld für das Popupfenster anzuzeigen, gehen Sie folgendermaßen vor:  
  
1.  Leiten Sie eine Klasse von `CMFCDesktopAlertDialog` ab.  
  
2.  Erstellen Sie eine untergeordnete Dialogfeldvorlage in den Ressourcen.  
  
3.  Rufen Sie [cmfcdesktopalertwnd:: Create](#create) Verwendung der Ressourcen-ID der Dialogfeldvorlage und einem Zeiger auf die laufzeitklasseninformationen der abgeleiteten Klasse.  
  
4.  Programmieren Sie das benutzerdefinierte Dialogfeld, behandeln alle Benachrichtigungen, die die gehosteten Steuerelemente stammen, oder programmieren Sie die gehosteten Steuerelemente so diese Benachrichtigungen direkt verarbeiten.  
  
 Verwenden Sie die folgenden Funktionen zur Steuerung des Verhaltens von der desktop-Benachrichtigungsfenster:  
  
-   Legen Sie durch Aufrufen der Animationstyp [CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype). Gültige Optionen: Erweitern und schieben Sie eingeblendet.  
  
-   Legen Sie die Geschwindigkeit der Animation Frame durch Aufrufen von [CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed).  
  
-   Legen Sie die der Transparenzebene durch Aufrufen von [CMFCDesktopAlertWnd::SetTransparency](#settransparency).  
  
-   Ändern der Größe der Beschriftung auf einen kleinen durch Aufrufen von [CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption). Der kleinen Überschrift ist 7 Pixel hoch.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCDesktopAlertWnd` Klasse zum Konfigurieren einer `CMFCDesktopAlertWnd` Objekt. Das Beispiel zeigt, wie Sie einen Animationstyp festlegen, legen Sie die Transparenz des Popupfensters, anzugeben, dass die Warnung eine kleine Beschriftung angezeigt und legen Sie die Zeit, die verstreicht, bevor die Warnung im Fenster automatisch geschlossen wird. Darüber hinaus wird das Erstellen und initialisieren die desktop-Benachrichtigungsfenster veranschaulicht. Dieser Codeausschnitt ist Teil der [Desktop Warnung Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#1](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwnd-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxDesktopAlertWnd.h  
  
##  <a name="create"></a>  Cmfcdesktopalertwnd:: Create  
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
 [in] [out] *pWndOwner*  
 Gibt den Besitzer des Fensters Warnung. Dieser Besitzer erhält alle Benachrichtigungen für die desktop-Benachrichtigungsfenster. Dieser Wert darf nicht NULL sein.  
  
 [in] *UiDlgResID*  
 Gibt die Ressourcen-ID des Fensters Warnung an.  
  
 [in] *hMenu*  
 Gibt an, das Menü, das angezeigt wird, wenn der Benutzer die Schaltfläche klickt. Wenn der Wert NULL ist, wird die Schaltfläche nicht angezeigt.  
  
 [in] *PtPos*  
 Gibt die Ausgangsposition an, in dem die Warnung wird angezeigt, die anhand der Bildschirmkoordinaten. Wenn dieser Parameter ist (1, -1), wird die Warnung im Fenster in der unteren rechten Ecke des Bildschirms angezeigt.  
  
 [in] *pRTIDlgBar*  
 Laufzeit-Klasseninformationen für eine benutzerdefinierte Dialogfeldklasse, die Clientbereich des Fensters auf die Warnung abdeckt.  
  
 [in] *Params*  
 Gibt Parameter an, die verwendet werden, um eine Warnung im Fenster zu erstellen.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn Sie das Benachrichtigungsfenster erfolgreich erstellt wurde. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um eine Warnung im Fenster zu erstellen. Das den Clientbereich des Fensters Warnung enthält ein untergeordnetes Dialogfeld, das alle Steuerelemente hostet, die dem Benutzer angezeigt werden.  
  
 Die erste methodenüberladung erstellt ein Warnungs-Fenster, das ein untergeordnetes Element enthält, die über die Ressourcen der Anwendung geladen wird. Die erste methodenüberladung kann auch die laufzeitklasseninformationen für ein benutzerdefiniertes Dialogfeldklasse angeben.  
  
 Die zweite methodenüberladung erstellt eine Warnung-Fenster, die Standardsteuerelemente enthält. Sie können angeben, welche Steuerelemente zum Anzeigen durch Ändern der [CMFCDesktopAlertWndInfo-Klasse](../../mfc/reference/cmfcdesktopalertwndinfo-class.md).  
  
##  <a name="getanimationspeed"></a>  CMFCDesktopAlertWnd::GetAnimationSpeed  
 Gibt die animationsgeschwindigkeit zurück.  
  
```  
UINT GetAnimationSpeed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die animationsgeschwindigkeit des Warnung Fensters, in Millisekunden.  
  
### <a name="remarks"></a>Hinweise  
 Die animationsgeschwindigkeit wird beschrieben, wie schnell das Benachrichtigungsfenster geöffnet und geschlossen wird.  
  
##  <a name="getanimationtype"></a>  CMFCDesktopAlertWnd::GetAnimationType  
 Gibt den Animationstyp zurück.  
  
```  
CMFCPopupMenu::ANIMATION_TYPE GetAnimationType();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine der folgenden Animationstypen:  
  
- NO_ANIMATION  
  
- ERWEITERN  
  
- FOLIE  
  
- AUSBLENDEN  
  
- SYSTEM_DEFAULT_ANIMATION  
  
##  <a name="getautoclosetime"></a>  CMFCDesktopAlertWnd::GetAutoCloseTime  
 Gibt zurück, das Automatisches Schließen-Timeout.  
  
```  
int GetAutoCloseTime() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Zeit in Millisekunden, nach denen die Warnung Fenster automatisch geschlossen wird.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um zu bestimmen, wie viel Zeit vergehen sollen, bevor die Warnung Fenster automatisch geschlossen wird.  
  
##  <a name="getcaptionheight"></a>  CMFCDesktopAlertWnd::GetCaptionHeight  
 Gibt die Höhe der Beschriftung.  
  
```  
virtual int GetCaptionHeight();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe der Beschriftung in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann in einer abgeleiteten Klasse überschrieben werden. Die standardmäßige Implementierung der beiden: kleiner Beschriftung Höhenwert (7 Pixel) zurückgegeben, falls das Popupfenster der kleinen Überschrift und den Wert aus der Windows-API-Funktion anzeigen soll `GetSystemMetrics(SM_CYSMCAPTION)`.  
  
##  <a name="getlastpos"></a>  CMFCDesktopAlertWnd::GetLastPos  
 Gibt die letzte Position der desktop-Benachrichtigungsfenster auf dem Bildschirm zurück.  
  
```  
CPoint GetLastPos() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Punkt in Bildschirmkoordinaten.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt die letzte gültige Position des Fensters Warnung auf dem Bildschirm.  
  
##  <a name="gettransparency"></a>  CMFCDesktopAlertWnd::GetTransparency  
 Gibt die der Transparenzebene zurück.  
  
```  
BYTE GetTransparency() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Transparenzebene zwischen 0 und 255 (einschließlich). Je größer der Wert, der den undurchsichtigeren des Fensters.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die aktuelle der Transparenzebene des Fensters Warnungen abzurufen.  
  
##  <a name="hassmallcaption"></a>  CMFCDesktopAlertWnd::HasSmallCaption  
 Bestimmt, ob die desktop-Benachrichtigungsfenster einer kleinen Beschriftung oder Beschriftung, die reguläre Größe hat.  
  
```  
BOOL HasSmallCaption() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das Popupfenster mit einer kleinen Beschriftung angezeigt wird. "False", wenn das Popupfenster mit einer normal großen Beschriftung angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um zu bestimmen, ob das Popupfenster eine kleine Beschriftung oder Beschriftung, die reguläre Größe hat. Standardmäßig ist der kleinen Überschrift 7 Pixel hoch. Sie erhalten die Höhe der Beschriftung reguläre Größe durch Aufrufen der Windows-API-Funktion `GetSystemMetrics(SM_CYCAPTION)`.  
  
##  <a name="onbeforeshow"></a>  CMFCDesktopAlertWnd::OnBeforeShow  

  
```  
virtual BOOL OnBeforeShow(CPoint&);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *CPoint &*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onclicklinkbutton"></a>  CMFCDesktopAlertWnd::OnClickLinkButton  
 Vom Framework aufgerufen, wenn der Benutzer eine Schaltfläche "Link" der desktop im Menü "Warnungen" klickt.  
  
```  
virtual BOOL OnClickLinkButton(UINT uiCmdID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *UiCmdID*  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Immer "false".  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, sollten Sie benachrichtigt werden, wenn ein Benutzer auf den Link auf die Warnung im Fenster klickt.  
  
##  <a name="oncommand"></a>  CMFCDesktopAlertWnd::OnCommand  

  
```  
virtual BOOL OnCommand(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *wParam-Parameter*  
 [in] *lParam*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondraw"></a>  CMFCDesktopAlertWnd::OnDraw  

  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="processcommand"></a>  CMFCDesktopAlertWnd::ProcessCommand  

  
```  
BOOL ProcessCommand(HWND hwnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Hwnd*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setanimationspeed"></a>  CMFCDesktopAlertWnd::SetAnimationSpeed  
 Geschwindigkeit der neuen Animation.  
  
```  
void SetAnimationSpeed(UINT nSpeed);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nSpeed*  
 Gibt die neue animationsgeschwindigkeit, in Millisekunden an.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Geschwindigkeit der Animation für das Benachrichtigungsfenster festgelegt. Die animationsgeschwindigkeit Standardwert ist 30 Millisekunden.  
  
##  <a name="setanimationtype"></a>  CMFCDesktopAlertWnd::SetAnimationType  
 Legt den Animationstyp fest.  
  
```  
void SetAnimationType(CMFCPopupMenu::ANIMATION_TYPE type);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Typ*  
 Gibt den Animationstyp.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Animation festgelegt. Sie können einen der folgenden Werte angeben:  
  
- NO_ANIMATION  
  
- ERWEITERN  
  
- FOLIE  
  
- AUSBLENDEN  
  
- SYSTEM_DEFAULT_ANIMATION  
  
##  <a name="setautoclosetime"></a>  CMFCDesktopAlertWnd::SetAutoCloseTime  
 Legt das Automatisches Schließen-Timeout fest.  
  
```  
void SetAutoCloseTime(int nTime);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nTime*  
 Die Zeit in Millisekunden, Ablauf, der die Warnung im Fenster automatisch geschlossen wird.  
  
### <a name="remarks"></a>Hinweise  
 Die Warnung im Fenster wird automatisch nach der angegebenen Zeit geschlossen, wenn der Benutzer nicht mit dem Fenster interagieren.  
  
##  <a name="setsmallcaption"></a>  CMFCDesktopAlertWnd::SetSmallCaption  
 Wechselt zwischen kleinen und reguläre Größe Beschriftungen.  
  
```  
void SetSmallCaption(BOOL bSmallCaption = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bSmallCaption*  
 True, um anzugeben, dass die Warnung eine kleine Beschriftung angezeigt. andernfalls "false", um anzugeben, dass die Warnung eine Beschriftung für die reguläre Größe angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Beschriftung für kleine oder reguläre Größe angezeigt. Standardmäßig ist der kleinen Überschrift 7 Pixel hoch. Sie können die Größe der regulären Beschriftung abrufen, indem Sie die Windows-API-Funktion aufrufen `GetSystemMetrics(SM_CYCAPTION)`.  
  
##  <a name="settransparency"></a>  CMFCDesktopAlertWnd::SetTransparency  
 Legt die Transparenzebene eines Popup-Fenster fest.  
  
```  
void SetTransparency(BYTE nTransparency);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nTransparency*  
 Gibt die der Transparenzebene. Dieser Wert muss zwischen 0 und 255 (einschließlich) liegen. Je größer der Wert, der den undurchsichtigeren des Fensters.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion zum Festlegen der der Transparenzebene der Popup-Fenster.  
  
##  <a name="getdialogsize"></a>  CMFCDesktopAlertWnd::GetDialogSize  

  
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
