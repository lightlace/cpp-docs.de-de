---
title: CMFCDesktopAlertWnd-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
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
caps.latest.revision: "33"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cfebb488921d81c36f842885ad49eae3f40a37fb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcdesktopalertwnd-class"></a>CMFCDesktopAlertWnd Class
Die `CMFCDesktopAlertWnd` Klasse implementiert die Funktion ein nicht modales Dialogfeld angezeigt wird, auf dem Bildschirm, um den Benutzer zu einem Ereignis zu informieren.  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]    
## <a name="syntax"></a>Syntax  
  
```  
class CMFCDesktopAlertWnd : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Cmfcdesktopalertwnd:: Create](#create)|Erstellt und initialisiert die Warnung Desktopfenster.|  
|[CMFCDesktopAlertWnd::GetAnimationSpeed](#getanimationspeed)|Gibt die Geschwindigkeit der Animation.|  
|[CMFCDesktopAlertWnd::GetAnimationType](#getanimationtype)|Gibt den Animationstyp.|  
|[CMFCDesktopAlertWnd::GetAutoCloseTime](#getautoclosetime)|Gibt das Timeout automatisch geschlossen.|  
|[CMFCDesktopAlertWnd::GetCaptionHeight](#getcaptionheight)|Gibt die Höhe der Beschriftung.|  
|[CMFCDesktopAlertWnd::GetDialogSize](#getdialogsize)||  
|[CMFCDesktopAlertWnd::GetLastPos](#getlastpos)|Gibt die letzte gültige Position des Fensters desktop Warnung auf dem Bildschirm an.|  
|[CMFCDesktopAlertWnd::GetTransparency](#gettransparency)|Gibt die der Transparenzebene zurück.|  
|[CMFCDesktopAlertWnd::HasSmallCaption](#hassmallcaption)|Bestimmt, ob die Warnung Desktopfenster mit kleiner Beschriftung angezeigt wird.|  
|[CMFCDesktopAlertWnd::OnBeforeShow](#onbeforeshow)||  
|[CMFCDesktopAlertWnd::OnClickLinkButton](#onclicklinkbutton)|Vom Framework aufgerufen, wenn der Benutzer eine Linkschaltfläche befindet sich auf den desktop Warnung im Menü klickt.|  
|[CMFCDesktopAlertWnd::OnCommand](#oncommand)|Das Framework ruft diese Memberfunktion auf, wenn der Benutzer ein Element aus einem Menü auswählt, wenn ein untergeordnetes Steuerelement eine Benachrichtigung sendet oder ein Accelerator Tastatureingabe übersetzt wird. (Überschreibt [Memberfunktion CWnd:: OnCommand](../../mfc/reference/cwnd-class.md#oncommand).)|  
|[CMFCDesktopAlertWnd::OnDraw](#ondraw)||  
|[CMFCDesktopAlertWnd::ProcessCommand](#processcommand)||  
|[CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed)|Legt die neue animationsgeschwindigkeit fest.|  
|[CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype)|Legt den Animationstyp fest.|  
|[CMFCDesktopAlertWnd::SetAutoCloseTime](#setautoclosetime)|Legt das Automatisches Schließen-Timeout fest.|  
|[CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption)|Wechselt zwischen normalem und kleinen Beschriftungen.|  
|[CMFCDesktopAlertWnd::SetTransparency](#settransparency)|Bestimmt die der Transparenzebene.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Warnung Desktopfenster transparent sein kann, kann mit Animationseffekte angezeigt werden und können sie (nach der angegebenen Verzögerung oder wenn der Benutzer durch Klicken auf die Schaltfläche "Schließen" schließt) verschwinden.  
  
 Eine Warnung Desktopfenster kann auch ein Standarddialogfeld enthalten, die wiederum ein Symbol, Meldungstext (eine Bezeichnung) und einen Link enthält. Alternativ kann eine Warnung Desktopfenster ein benutzerdefiniertes Dialogfelds von Ressourcen der Anwendung enthalten.  
  
 Erstellen Sie eine Warnung Desktopfenster in zwei Schritten. Rufen Sie zunächst den Konstruktor zum Erstellen der `CMFCDesktopAlertWnd` Objekt. Zweitens, rufen Sie die [cmfcdesktopalertwnd:: Create](#create) Memberfunktion versucht, erstellen Sie das Fenster, und fügen Sie es auf die `CMFCDesktopAlertWnd` Objekt.  
  
 Die `CMFCDesktopAlertWnd` -Objekt erstellt, einen speziellen untergeordneten (Dialogfeld), die den Clientbereich der Warnung Desktopfenster ausfüllt. Das Dialogfeld beinhaltet alle Steuerelemente, die darauf positioniert ist.  
  
 Um ein benutzerdefiniertes Dialogfeld im Popupfenster anzuzeigen, gehen Sie folgendermaßen vor:  
  
1.  Leiten Sie eine Klasse von `CMFCDesktopAlertDialog` ab.  
  
2.  Erstellen Sie eine untergeordnete Dialogfeldvorlage in den Ressourcen.  
  
3.  Rufen Sie [cmfcdesktopalertwnd:: Create](#create) Verwendung der Ressourcen-ID der Dialogfeldvorlage und einem Zeiger auf die laufzeitklasseninformationen der abgeleiteten Klasse.  
  
4.  Programmieren Sie das benutzerdefinierte Dialogfeld alle Benachrichtigungen, die von den gehosteten Steuerelementen behandeln, oder programmieren Sie die gehosteten Steuerelemente so diese Benachrichtigungen direkt verarbeiten.  
  
 Verwenden Sie die folgenden Funktionen zum Steuern des Verhaltens von die Warnung Desktopfenster:  
  
-   Legen Sie den Animationstyp, durch den Aufruf [CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype). Die gültigen Optionen umfassen erweitern, schieben und abgeblendet.  
  
-   Legen Sie die Frame-animationsgeschwindigkeit durch Aufrufen [CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed).  
  
-   Legen Sie die der Transparenzebene durch Aufrufen von [CMFCDesktopAlertWnd::SetTransparency](#settransparency).  
  
-   Ändern Sie die Größe der Beschriftung um kleine durch Aufrufen von [CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption). Der kleinen Überschrift für ist 7 Pixel hoch.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie mithilfe verschiedener Methoden in der `CMFCDesktopAlertWnd` Klasse zum Konfigurieren einer `CMFCDesktopAlertWnd` Objekt. Das Beispiel zeigt das Festlegen eines Animationstyps, legen Sie die Transparenz des Popupfensters, angeben, dass die Warnung im Fenster eine kleine Beschriftung angezeigt, und legen Sie die Zeit, die verstreicht, bevor das Benachrichtigungsfenster automatisch geschlossen wird. Darüber hinaus wird das Erstellen und initialisieren die Warnung Desktopfenster veranschaulicht. Dieser Codeausschnitt ist Teil der [Desktop Warnung Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#1](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwnd-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxDesktopAlertWnd.h  
  
##  <a name="create"></a>Cmfcdesktopalertwnd:: Create  
 Erstellt und initialisiert die Warnung Desktopfenster.  
  
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
 Gibt den Besitzer des Fensters Warnung. Dieser Besitzer erhält alle Benachrichtigungen für die Warnung Desktopfenster. Dieser Wert darf nicht `NULL` sein.  
  
 [in] `uiDlgResID`  
 Gibt die Ressourcen-ID des Fensters Warnung an.  
  
 [in] `hMenu`  
 Gibt an, das Menü, das angezeigt wird, wenn der Benutzer die Schaltfläche klickt. Wenn `NULL`, die Menüschaltfläche wird nicht angezeigt.  
  
 [in] `ptPos`  
 Gibt die erste Position, in dem die Warnung wird angezeigt, die anhand der Bildschirmkoordinaten. Wenn dieser Parameter ist (-1, -1), wird die Warnung im Fenster in der unteren rechten Ecke des Bildschirms angezeigt.  
  
 [in] `pRTIDlgBar`  
 Laufzeit-Klasseninformationen für eine benutzerdefinierte Dialogfeldklasse, die das Benachrichtigungsfenster Clientbereich abdeckt.  
  
 [in] `params`  
 Gibt Parameter an, die beim Erstellen einer Warnung Fensters verwendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Warnung Fenster erfolgreich erstellt wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um eine Warnung Fenster zu erstellen. Das den Clientbereich des Fensters Warnung enthält einen untergeordneten (Dialogfeld), der alle Steuerelemente hostet, die dem Benutzer angezeigt werden.  
  
 Die erste methodenüberladung erstellt eine Warnung Fenster, das ein untergeordnetes Element enthält, die von Ressourcen der Anwendung geladen wird. Die erste methodenüberladung kann auch die laufzeitklasseninformationen für ein benutzerdefiniertes Dialogfeldklasse angeben.  
  
 Die zweite methodenüberladung erstellt eine Warnung Fenster, die Standardsteuerelemente enthält. Sie können angeben, welche Steuerelemente für die anzuzeigenden durch Ändern der [CMFCDesktopAlertWndInfo-Klasse](../../mfc/reference/cmfcdesktopalertwndinfo-class.md).  
  
##  <a name="getanimationspeed"></a>CMFCDesktopAlertWnd::GetAnimationSpeed  
 Gibt die Geschwindigkeit der Animation.  
  
```  
UINT GetAnimationSpeed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die animationsgeschwindigkeit des Fensters Warnung in Millisekunden.  
  
### <a name="remarks"></a>Hinweise  
 Die animationsgeschwindigkeit wird beschrieben, wie schnell der Warnung im Fenster geöffnet und geschlossen wird.  
  
##  <a name="getanimationtype"></a>CMFCDesktopAlertWnd::GetAnimationType  
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
  
##  <a name="getautoclosetime"></a>CMFCDesktopAlertWnd::GetAutoCloseTime  
 Gibt das Timeout automatisch geschlossen.  
  
```  
int GetAutoCloseTime() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Zeit in Millisekunden, nach denen die Warnung Fenster automatisch geschlossen wird.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um zu bestimmen, wie viel Zeit vergehen soll, bevor die Warnung Fenster automatisch geschlossen wird.  
  
##  <a name="getcaptionheight"></a>CMFCDesktopAlertWnd::GetCaptionHeight  
 Gibt die Höhe der Beschriftung.  
  
```  
virtual int GetCaptionHeight();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe der Beschriftung in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann in einer abgeleiteten Klasse überschrieben werden. Die standardmäßige Implementierung entweder: Wert für die Höhe der kleinen Überschrift für (7 in Pixel) zurückgibt, wenn das Popupfenster der kleinen Überschrift für oder den Wert der Windows-API-Funktion anzeigen soll `GetSystemMetrics(SM_CYSMCAPTION)`.  
  
##  <a name="getlastpos"></a>CMFCDesktopAlertWnd::GetLastPos  
 Gibt die letzte Position des Fensters Warnung Desktops auf dem Bildschirm zurück.  
  
```  
CPoint GetLastPos() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Punkt in Bildschirmkoordinaten.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt die letzte gültige Position des Fensters Warnung auf dem Bildschirm.  
  
##  <a name="gettransparency"></a>CMFCDesktopAlertWnd::GetTransparency  
 Gibt die der Transparenzebene zurück.  
  
```  
BYTE GetTransparency() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine der Transparenzebene zwischen 0 und 255. Je größer der Wert, der weitere undurchsichtig des Fensters.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die aktuelle der Transparenzebene des Fensters Warnung abzurufen.  
  
##  <a name="hassmallcaption"></a>CMFCDesktopAlertWnd::HasSmallCaption  
 Bestimmt, ob die Warnung Desktopfenster einer kleinen Beschriftung oder eine Beschriftung, die reguläre Größe hat.  
  
```  
BOOL HasSmallCaption() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn mit einem kleinen Überschrift für das Popupfenster angezeigt wird; `FALSE` Wenn Popup-Fenster mit einem Titel normal großen angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um zu bestimmen, ob das Popupfenster ein kleiner Beschriftung oder eine Beschriftung, die reguläre Größe hat. Standardmäßig ist der kleinen Überschrift für 7 Pixel hoch. Sie erhalten die Höhe der Beschriftung reguläre Größe durch Aufrufen der Windows-API-Funktion `GetSystemMetrics(SM_CYCAPTION)`.  
  
##  <a name="onbeforeshow"></a>CMFCDesktopAlertWnd::OnBeforeShow  

  
```  
virtual BOOL OnBeforeShow(CPoint&);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `CPoint&`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onclicklinkbutton"></a>CMFCDesktopAlertWnd::OnClickLinkButton  
 Vom Framework aufgerufen, wenn der Benutzer eine Linkschaltfläche befindet sich auf den desktop Warnung im Menü klickt.  
  
```  
virtual BOOL OnClickLinkButton(UINT uiCmdID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdID`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, wenn Sie benachrichtigt werden, wenn ein Benutzer auf den Link auf die Warnung im Fenster klickt möchten.  
  
##  <a name="oncommand"></a>CMFCDesktopAlertWnd::OnCommand  

  
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
  
##  <a name="ondraw"></a>CMFCDesktopAlertWnd::OnDraw  

  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="processcommand"></a>CMFCDesktopAlertWnd::ProcessCommand  

  
```  
BOOL ProcessCommand(HWND hwnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hwnd`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setanimationspeed"></a>CMFCDesktopAlertWnd::SetAnimationSpeed  
 Legt die neue animationsgeschwindigkeit fest.  
  
```  
void SetAnimationSpeed(UINT nSpeed);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nSpeed`  
 Gibt die neue animationsgeschwindigkeit in Millisekunden an.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Geschwindigkeit der Animation für die Warnung Fenster festzulegen. Die animationsgeschwindigkeit Standardwert beträgt 30 Millisekunden.  
  
##  <a name="setanimationtype"></a>CMFCDesktopAlertWnd::SetAnimationType  
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
  
##  <a name="setautoclosetime"></a>CMFCDesktopAlertWnd::SetAutoCloseTime  
 Legt das Automatisches Schließen-Timeout fest.  
  
```  
void SetAutoCloseTime(int nTime);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nTime`  
 Die Zeit in Millisekunden die, verstreicht, die vor dem Fenster Warnungen automatisch geschlossen wird.  
  
### <a name="remarks"></a>Hinweise  
 Die Warnung im Fenster wird automatisch nach der angegebenen Zeit geschlossen, wenn der Benutzer nicht mit dem Fenster interagieren.  
  
##  <a name="setsmallcaption"></a>CMFCDesktopAlertWnd::SetSmallCaption  
 Wechselt zwischen klein und reguläre Größe Beschriftungen.  
  
```  
void SetSmallCaption(BOOL bSmallCaption = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bSmallCaption`  
 `TRUE`um anzugeben, dass die Warnung im Fenster eine kleine Beschriftung anzeigt; andernfalls `FALSE` um anzugeben, dass die Warnung eine Beschriftung für die reguläre Größe angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Beschriftung für kleine oder reguläre Größe anzuzeigen. Standardmäßig ist der kleinen Überschrift für 7 Pixel hoch. Sie können die Größe der regulären Beschriftung abrufen, durch Aufrufen der Windows-API-Funktion `GetSystemMetrics(SM_CYCAPTION)`.  
  
##  <a name="settransparency"></a>CMFCDesktopAlertWnd::SetTransparency  
 Bestimmt die der Transparenzebene im Popup-Fenster.  
  
```  
void SetTransparency(BYTE nTransparency);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nTransparency`  
 Gibt die der Transparenzebene. Dieser Wert muss zwischen 0 und 255 einschließlich liegen. Je größer der Wert, der weitere undurchsichtig des Fensters.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Festlegen der der Transparenzebene der Popup-Fenster.  
  
##  <a name="getdialogsize"></a>CMFCDesktopAlertWnd::GetDialogSize  

  
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
