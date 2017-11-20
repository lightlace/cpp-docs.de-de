---
title: CLinkCtrl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CLinkCtrl
- AFXCMN/CLinkCtrl
- AFXCMN/CLinkCtrl::CLinkCtrl
- AFXCMN/CLinkCtrl::Create
- AFXCMN/CLinkCtrl::CreateEx
- AFXCMN/CLinkCtrl::GetIdealHeight
- AFXCMN/CLinkCtrl::GetIdealSize
- AFXCMN/CLinkCtrl::GetItem
- AFXCMN/CLinkCtrl::GetItemID
- AFXCMN/CLinkCtrl::GetItemState
- AFXCMN/CLinkCtrl::GetItemUrl
- AFXCMN/CLinkCtrl::HitTest
- AFXCMN/CLinkCtrl::SetItem
- AFXCMN/CLinkCtrl::SetItemID
- AFXCMN/CLinkCtrl::SetItemState
- AFXCMN/CLinkCtrl::SetItemUrl
dev_langs: C++
helpviewer_keywords:
- CLinkCtrl [MFC], CLinkCtrl
- CLinkCtrl [MFC], Create
- CLinkCtrl [MFC], CreateEx
- CLinkCtrl [MFC], GetIdealHeight
- CLinkCtrl [MFC], GetIdealSize
- CLinkCtrl [MFC], GetItem
- CLinkCtrl [MFC], GetItemID
- CLinkCtrl [MFC], GetItemState
- CLinkCtrl [MFC], GetItemUrl
- CLinkCtrl [MFC], HitTest
- CLinkCtrl [MFC], SetItem
- CLinkCtrl [MFC], SetItemID
- CLinkCtrl [MFC], SetItemState
- CLinkCtrl [MFC], SetItemUrl
ms.assetid: d1cd876a-ecca-42db-8ac4-9cd327df0cd4
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7d61e3f09b96c236277cdaf3c38008be2a661f40
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="clinkctrl-class"></a>CLinkCtrl-Klasse
Stellt die Funktionalität des allgemeinen Windows-SysLink-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CLinkCtrl : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CLinkCtrl::CLinkCtrl](#clinkctrl)|Erstellt ein `CLinkCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CLinkCtrl::Create](#create)|Erstellt ein Linksteuerelement und fügt es einer `CLinkCtrl` Objekt.|  
|[CLinkCtrl::CreateEx](#createex)|Erstellt ein Linksteuerelement mit erweiterten Stile und fügt es einer `CLinkCtrl` Objekt.|  
|[CLinkCtrl::GetIdealHeight](#getidealheight)|Ruft die optimale Höhe der Link-Steuerelement ab.|  
|[CLinkCtrl::GetIdealSize](#getidealsize)|Berechnet die bevorzugte Höhe der Text des Links für das aktuelle Linksteuerelement, abhängig von die angegebene Breite des Links.|  
|[CLinkCtrl::GetItem](#getitem)|Ruft ab, die Status und Attribute von einem Link-Steuerelement ein Element.|  
|[CLinkCtrl::GetItemID](#getitemid)|Ruft die ID des Elements eine Link-Steuerelement ab.|  
|[CLinkCtrl::GetItemState](#getitemstate)|Ruft den Zustand der Link-Steuerelement ein Element an.|  
|[CLinkCtrl::GetItemUrl](#getitemurl)|Ruft die URL, die durch die Link-Steuerelement ein Element dargestellt wird.|  
|[CLinkCtrl::HitTest](#hittest)|Bestimmt, ob der Benutzer den angegebenen Link geklickt hat.|  
|[CLinkCtrl::SetItem](#setitem)|Legt fest, die Status und Attribute von einem Link-Steuerelement ein Element.|  
|[CLinkCtrl::SetItemID](#setitemid)|Legt die ID des Elements eine Link-Steuerelement fest.|  
|[CLinkCtrl::SetItemState](#setitemstate)|Legt den Zustand des Elements Link-Steuerelement.|  
|[CLinkCtrl::SetItemUrl](#setitemurl)|Legt die URL, die durch die Link-Steuerelement ein Element dargestellt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Eine "link Control" bietet eine praktische Möglichkeit zum Einbetten von Hypertextlinks in einem Fenster. Das aktuelle Steuerelement ist ein Fenster, das markierte Text gerendert und entsprechende Anwendungen startet, wenn der Benutzer einen Link klickt. Mehrere Verknüpfungen werden in einem Steuerelement unterstützt und können durch einen nullbasierten Index zugegriffen werden.  
  
 Dieses Steuerelement (und somit die `CLinkCtrl` Klasse) steht nur für Programme, die unter Windows XP und höher ausgeführt.  
  
 Weitere Informationen finden Sie unter [SysLink-Steuerelements](http://msdn.microsoft.com/library/windows/desktop/bb760706) im Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CLinkCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="clinkctrl"></a>CLinkCtrl::CLinkCtrl  
 Erstellt ein `CLinkCtrl`-Objekt.  
  
```  
CLinkCtrl();
```  
  
##  <a name="create"></a>CLinkCtrl::Create  
 Erstellt ein Linksteuerelement und fügt es einer `CLinkCtrl` Objekt.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszLinkMarkup,   
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);

 
virtual BOOL Create(DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszLinkMarkup`  
 Ein Zeiger auf eine NULL-terminierte Zeichenfolge, die das markierte anzuzeigenden Text enthält. Weitere Informationen finden Sie im Abschnitt "Markup und Link-Zugriff" in diesem Thema [Übersicht-SysLink-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb760706) in der [MSDN Library](http://go.microsoft.com/fwlink/linkid=556).  
  
 `dwStyle`  
 Gibt das Format der Link-Steuerelements an. Wenden Sie eine beliebige Kombination von Steuerelementtypen. Finden Sie unter [Steuerelementtypen für die allgemeine](http://msdn.microsoft.com/library/windows/desktop/bb775498) in der `Windows SDK` für Weitere Informationen.  
  
 `rect`  
 Gibt an, Größe und Position der Link-Steuerelement. Es kann es sich um eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder eine [RECT](../../mfc/reference/rect-structure1.md) Struktur.  
  
 `pParentWnd`  
 Gibt das Linksteuerelement übergeordneten Fenster. Es muss nicht `NULL`.  
  
 `nID`  
 Gibt die Link-Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die Initialisierung erfolgreich war; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CLinkCtrl` Objekt in zwei Schritten. Zunächst den Konstruktor aufrufen und dann `Create`, die das Linksteuerelement erstellt, und fügt es der `CLinkCtrl` Objekt. Wenn Sie die erweiterten Fensterstile mit dem Steuerelement verwenden möchten, rufen Sie [CLinkCtrl::CreateEx](#createex) anstelle von `Create`.  
  
 Die zweite Form der `Create` Methode ist veraltet. Die erste Form, der angibt, die `lpszLinkMarkup` Parameter.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert zwei Variablen, die mit dem Namen `m_Link1` und `m_Link2`, die Zugriff auf zwei Link-Steuerelemente verwendet werden.  
  
 [!code-cpp[NVC_MFC_CLinkCtrl_s1#2](../../mfc/reference/codesnippet/cpp/clinkctrl-class_1.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird ein Linksteuerelement basierend auf den Speicherort der Link-Steuerelement für eine andere erstellt. Das Ressourcenladeprogramm für die erstellt den ersten Link-Steuerelement beim Start der Anwendung. Wenn Ihre Anwendung die OnInitDialog-Methode eingibt, erstellen Sie den zweiten Link-Steuerelement für relativ zur Position des ersten Link-Steuerelement. Dann ändern Sie den zweiten Link-Steuerelement für die Textlänge angepasst, in dem er angezeigt wird.  
  
 [!code-cpp[NVC_MFC_CLinkCtrl_s1#1](../../mfc/reference/codesnippet/cpp/clinkctrl-class_2.cpp)]  
  
##  <a name="createex"></a>CLinkCtrl::CreateEx  
 Erstellt ein Linksteuerelement mit erweiterten Stile und fügt es einer `CLinkCtrl` Objekt.  
  
```  
virtual BOOL CreateEx(
    LPCTSTR lpszLinkMarkup,   
    DWORD dwExStyle,  
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);

 
virtual BOOL CreateEx(DWORD  dwExStyle,
    DWORD  dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT  nID);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszLinkMarkup`  
 Ein Zeiger auf eine NULL-terminierte Zeichenfolge, die das markierte anzuzeigenden Text enthält. Weitere Informationen finden Sie im Abschnitt "Markup und Link-Zugriff" in diesem Thema [Übersicht-SysLink-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb760706) in der [MSDN Library](http://go.microsoft.com/fwlink/linkid=556).  
  
 `dwExStyle`  
 Gibt den erweiterten Stil des Link-Steuerelements an. Eine Liste der erweiterten Fensterstile, finden Sie unter der `dwExStyle` -Parameter für [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) im Windows SDK.  
  
 `dwStyle`  
 Gibt das Format der Link-Steuerelements an. Wenden Sie eine beliebige Kombination von Steuerelementtypen. Weitere Informationen finden Sie unter [Steuerelementtypen für die allgemeine](http://msdn.microsoft.com/library/windows/desktop/bb775498) im Windows SDK.  
  
 `rect`  
 Gibt an, Größe und Position der Link-Steuerelement. Es kann es sich um eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder eine [RECT](../../mfc/reference/rect-structure1.md) Struktur.  
  
 `pParentWnd`  
 Gibt das Linksteuerelement übergeordneten Fenster. Es muss nicht `NULL`.  
  
 `nID`  
 Gibt die Link-Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die Initialisierung erfolgreich war; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von [erstellen](#create) anzuwendende Erweiterte Windows-Style-Konstanten.  
  
 Die zweite Form der `CreateEx` Methode ist veraltet. Die erste Form, der angibt, die `lpszLinkMarkup` Parameter.  
  
##  <a name="getidealheight"></a>CLinkCtrl::GetIdealHeight  
 Ruft die optimale Höhe der Link-Steuerelement ab.  
  
```  
int GetIdealHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die ideale Höhe des Steuerelements in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [LM_GETIDEALHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb760716)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="getidealsize"></a>CLinkCtrl::GetIdealSize  
 Berechnet die bevorzugte Höhe der Text des Links für das aktuelle Linksteuerelement, abhängig von die angegebene Breite des Links.  
  
```  
int GetIdealSize(
    int cxMaxWidth,   
    SIZE* pSize) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `cxMaxWidth`|Die maximale Breite des Links, in Pixel.|  
|[Out] *`pSize`|Ein Zeiger auf ein Windows [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur. Rückkehr dieser Methode die `cy` Mitglied der `SIZE` Struktur enthält die ideale Link Texthöhe für die Breite der Link-Text, der angegebenen `cxMaxWidth`. Die `cx` Member der Struktur enthält die Breite der Link-Text, der tatsächlich benötigt wird.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die bevorzugte Höhe der Text des Links in Pixeln. Der Rückgabewert ist identisch mit dem Wert von der `cy` Mitglied der `SIZE` Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Ein Beispiel für die `GetIdealSize` -Methode, siehe das Beispiel in [CLinkCtrl::Create](#create).  
  
 Diese Methode sendet die [LM_GETIDEALSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760718) Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="getitem"></a>CLinkCtrl::GetItem  
 Ruft ab, die Status und Attribute von einem Link-Steuerelement ein Element.  
  
```  
BOOL GetItem(PLITEM pItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pItem`  
 Ein Zeiger auf eine [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) Struktur Elementinformationen zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg **"false"** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="getitemid"></a>CLinkCtrl::GetItemID  
 Ruft die ID des Elements eine Link-Steuerelement ab.  
  
```  
BOOL GetItemID(
    int iLink,  
    CString& strID) const;  
  
BOOL GetItemID(
    int iLink,  
    LPWSTR szID,  
    UINT cchID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `iLink`  
 Der Index von einem Link-Steuerelement ein Element.  
  
 *strID*  
 Ein [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, das die ID des angegebenen Elements enthält.  
  
 *szID*  
 Eine auf Null endende Zeichenfolge, enthält die ID des angegebenen Elements.  
  
 *cchID*  
 Die Größe in Zeichen von der *SzID* Puffer.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg **"false"** bei einem Fehler.  
  
> [!NOTE]
>  Diese Funktion auch gibt **"false"** Wenn der Puffer des *SzID oder StrID* ist kleiner als **MAX_LINKID_TEXT**.  
  
### <a name="remarks"></a>Hinweise  
 Ruft die ID eines bestimmten Link-Steuerelement-Elements ab. Weitere Informationen finden Sie in der Win32-Meldung [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720) im Windows SDK.  
  
##  <a name="getitemstate"></a>CLinkCtrl::GetItemState  
 Ruft den Zustand der Link-Steuerelement ein Element an.  
  
```  
BOOL GetItemState(
    int iLink,  
    UINT* pnState,  
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `iLink`  
 Der Index von einem Link-Steuerelement ein Element.  
  
 `pnState`  
 Der Wert des angegebenen Elements.  
  
 `stateMask`  
 Kombination von Flags, welche Status, der abzurufende Element beschreibt. Eine Liste von Werten, finden Sie unter der Beschreibung der der **Status** Element in der [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) Struktur. Zulässige Elemente sind identisch mit denen in zulässig **Zustand**.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg **"false"** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Ruft den Wert des Elements angegebenen Zustand eines bestimmten Link-Steuerelement-Elements. Weitere Informationen finden Sie in der Win32-Meldung [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720) im Windows SDK.  
  
##  <a name="getitemurl"></a>CLinkCtrl::GetItemUrl  
 Ruft die URL, die durch die Link-Steuerelement ein Element dargestellt wird.  
  
```  
BOOL GetItemUrl(
    int iLink,  
    CString& strUrl) const;  
  
BOOL GetItemUrl(
    int iLink,  
    LPWSTR szUrl,  
    UINT cchUrl) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `iLink`  
 Der Index von einem Link-Steuerelement ein Element.  
  
 `strUrl`  
 Ein [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, das die URL, dargestellt durch das angegebene Element enthält  
  
 `szUrl`  
 Eine Null-terminierte Zeichenfolge, der die URL, die durch das angegebene Element dargestellt wird  
  
 *cchUrl*  
 Die Größe in Zeichen von der *SzURL* Puffer.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg **"false"** bei einem Fehler.  
  
> [!NOTE]
>  Diese Funktion auch gibt **"false"** Wenn der Puffer des *SzUrl oder StrUrl* ist kleiner als **MAX_LINKID_TEXT**.  
  
### <a name="remarks"></a>Hinweise  
 Ruft die URL, die durch den angegebenen Link-Steuerelement ein Element dargestellt wird. Weitere Informationen finden Sie in der Win32-Meldung [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720) im Windows SDK.  
  
##  <a name="hittest"></a>CLinkCtrl::HitTest  
 Bestimmt, ob der Benutzer den angegebenen Link geklickt hat.  
  
```  
BOOL HitTest(PLHITTESTINFO phti) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *phti*  
 Zeiger auf eine **LHITTESTINFO** Struktur, enthält keine Informationen über den Link der Benutzer geklickt hat.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg **"false"** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [LM_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb760722)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="setitem"></a>CLinkCtrl::SetItem  
 Legt fest, die Status und Attribute von einem Link-Steuerelement ein Element.  
  
```  
BOOL SetItem(PLITEM pItem);
```  
  
### <a name="parameters"></a>Parameter  
 `pItem`  
 Ein Zeiger auf eine [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) Struktur mit Informationen über das festlegen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg **"false"** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="setitemid"></a>CLinkCtrl::SetItemID  
 Ruft die ID des Elements eine Link-Steuerelement ab.  
  
```  
BOOL SetItemID(
    int iLink,  
    LPCWSTR szID);
```  
  
### <a name="parameters"></a>Parameter  
 `iLink`  
 Der Index von einem Link-Steuerelement ein Element.  
  
 *szID*  
 Eine auf Null endende Zeichenfolge, enthält die ID des angegebenen Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg **"false"** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Legt die ID von einer bestimmten Link-Steuerelement ein Element fest. Weitere Informationen finden Sie in der Win32-Meldung [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724) im Windows SDK.  
  
##  <a name="setitemstate"></a>CLinkCtrl::SetItemState  
 Ruft den Zustand der Link-Steuerelement ein Element an.  
  
```  
BOOL SetItemState(
    int iLink,  
    UINT state,  
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED);
```  
  
### <a name="parameters"></a>Parameter  
 `iLink`  
 Der Index von einem Link-Steuerelement ein Element.  
  
 `pnState`  
 Der Wert des angegebenen Zustand Elements festgelegt wird.  
  
 `stateMask`  
 Kombination von Flags, beschreiben das State-Element, das festgelegt wird. Eine Liste von Werten, finden Sie unter der Beschreibung der der **Status** Element in der [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) Struktur. Zulässige Elemente sind identisch mit denen in zulässig **Zustand**.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg **"false"** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Legt den Wert des Elements angegebenen Zustand eines bestimmten Link-Steuerelement-Elements. Weitere Informationen finden Sie in der Win32-Meldung [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724) im Windows SDK.  
  
##  <a name="setitemurl"></a>CLinkCtrl::SetItemUrl  
 Legt die URL, die durch die Link-Steuerelement ein Element dargestellt wird.  
  
```  
BOOL SetItemUrl(
    int iLink,  
    LPCWSTR szUrl);
```  
  
### <a name="parameters"></a>Parameter  
 `iLink`  
 Der Index von einem Link-Steuerelement ein Element.  
  
 `szUrl`  
 Eine Null-terminierte Zeichenfolge, der die URL, die durch das angegebene Element dargestellt wird  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg **"false"** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Legt die URL, die durch den angegebenen Link-Steuerelement ein Element dargestellt wird. Weitere Informationen finden Sie in der Win32-Meldung [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)
