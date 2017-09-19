---
title: CLinkCtrl Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- CLinkCtrl class
- Web pages, link control
- controls [MFC], links
- links [C++], link control
- SysLink control
ms.assetid: d1cd876a-ecca-42db-8ac4-9cd327df0cd4
caps.latest.revision: 23
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
ms.openlocfilehash: 710fef79306c906e13e99beac15401835422ecbe
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

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
|[CLinkCtrl::Create](#create)|Erstellt ein Linksteuerelement und fügt es ein `CLinkCtrl` Objekt.|  
|[CLinkCtrl::CreateEx](#createex)|Erstellt ein Linksteuerelement mit erweiterten Stile und fügt es ein `CLinkCtrl` Objekt.|  
|[CLinkCtrl::GetIdealHeight](#getidealheight)|Ruft die optimale Höhe der Link-Steuerelement ab.|  
|[CLinkCtrl::GetIdealSize](#getidealsize)|Berechnet die bevorzugte Höhe der Text des Links für das aktuelle Linksteuerelement, je nach der angegebenen Breite des Links.|  
|[CLinkCtrl::GetItem](#getitem)|Ruft die Zustände und die Attribute eines Elements der Link-Steuerelement.|  
|[CLinkCtrl::GetItemID](#getitemid)|Ruft die ID des Elements ein Link-Steuerelement ab.|  
|[CLinkCtrl::GetItemState](#getitemstate)|Ruft den Zustand des Elements Link-Steuerelement.|  
|[CLinkCtrl::GetItemUrl](#getitemurl)|Ruft die URL durch die Link-Steuerelement ein Element dargestellt wird.|  
|[CLinkCtrl::HitTest](#hittest)|Bestimmt, ob der Benutzer den angegebenen Link geklickt hat.|  
|[CLinkCtrl::SetItem](#setitem)|Legt fest, die Zustände und die Attribute eines Elements der Link-Steuerelement.|  
|[CLinkCtrl::SetItemID](#setitemid)|Legt die ID des Elements ein Link-Steuerelement fest.|  
|[CLinkCtrl::SetItemState](#setitemstate)|Legt den Zustand des Elements Link-Steuerelement.|  
|[CLinkCtrl::SetItemUrl](#setitemurl)|Legt die URL durch die Link-Steuerelement ein Element dargestellt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Eine "link Control" bietet eine bequeme Möglichkeit, Hypertextlinks in einem Fenster einzubetten. Das aktuelle Steuerelement ist ein Fenster, wird der markierte Text gerendert und entsprechende Anwendung startet, klickt der Benutzer auf einen Link. Mehrere Links werden in einem Steuerelement unterstützt und können durch einen nullbasierten Index zugegriffen werden.  
  
 Dieses Steuerelement (und somit die `CLinkCtrl` Klasse) ist nur für Programme unter Windows XP und höher verfügbar.  
  
 Weitere Informationen finden Sie unter [SysLink-Steuerelements](http://msdn.microsoft.com/library/windows/desktop/bb760706) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
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
 Erstellt ein Linksteuerelement und fügt es ein `CLinkCtrl` Objekt.  
  
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
 Ein Zeiger auf eine NULL-terminierte Zeichenfolge, die das markierte anzuzeigenden Text enthält. Weitere Informationen finden Sie im Abschnitt "Markup and Link Access" im Thema [Overview-SysLink-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb760706) in der [MSDN Library](http://go.microsoft.com/fwlink/linkid=556).  
  
 `dwStyle`  
 Gibt die Link-Steuerelement-Stil. Wenden Sie eine beliebige Kombination von Steuerelementtypen. Finden Sie unter [Steuerelementtypen für die allgemeine](http://msdn.microsoft.com/library/windows/desktop/bb775498) in den `Windows SDK` Weitere Informationen.  
  
 `rect`  
 Gibt die Link-Steuerelement Größe und Position. Es kann entweder eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT](../../mfc/reference/rect-structure1.md) Struktur.  
  
 `pParentWnd`  
 Gibt die Link-Steuerelement übergeordnetes Fenster. Er darf nicht sein `NULL`.  
  
 `nID`  
 Gibt die Link-Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die Initialisierung erfolgreich war; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen ein `CLinkCtrl` Objekt in zwei Schritten. Erstens den Konstruktor aufrufen und dann `Create`, die das Linksteuerelement erstellt, und fügt es der `CLinkCtrl` Objekt. Wenn Sie erweiterte Fensterstile mit dem Steuerelement verwenden möchten, rufen Sie [CLinkCtrl::CreateEx](#createex) anstelle von `Create`.  
  
 Die zweite Form der `Create` Methode ist veraltet. Die erste Form, der angibt, die `lpszLinkMarkup` Parameter.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert zwei Variablen, die mit dem Namen `m_Link1` und `m_Link2`, die Zugriff auf zwei Link-Steuerelemente verwendet werden.  
  
 [!code-cpp[NVC_MFC_CLinkCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/clinkctrl-class_1.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird ein Linksteuerelement basierend auf dem Standort von einem anderen Linksteuerelement erstellt. Das Ressourcenladeprogramm wird das erste Linksteuerelement beim Start der Anwendung erstellt. Ihre Anwendung die OnInitDialog-Methode ein, erstellen Sie das zweite Linksteuerelement relativ zu der Position des ersten Link-Steuerelement. Dann ändern Sie den zweiten Link-Steuerelement den Text an, dem es anzeigt.  
  
 [!code-cpp[NVC_MFC_CLinkCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/clinkctrl-class_2.cpp)]  
  
##  <a name="createex"></a>CLinkCtrl::CreateEx  
 Erstellt ein Linksteuerelement mit erweiterten Stile und fügt es ein `CLinkCtrl` Objekt.  
  
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
 Ein Zeiger auf eine NULL-terminierte Zeichenfolge, die das markierte anzuzeigenden Text enthält. Weitere Informationen finden Sie im Abschnitt "Markup and Link Access" im Thema [Overview-SysLink-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb760706) in der [MSDN Library](http://go.microsoft.com/fwlink/linkid=556).  
  
 `dwExStyle`  
 Gibt den erweiterten Stil des Link-Steuerelements. Eine Liste der erweiterten Fensterstile, finden Sie unter der `dwExStyle` -Parameter für [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwStyle`  
 Gibt die Link-Steuerelement-Stil. Wenden Sie eine beliebige Kombination von Steuerelementtypen. Weitere Informationen finden Sie unter [Steuerelementtypen für die allgemeine](http://msdn.microsoft.com/library/windows/desktop/bb775498) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Gibt die Link-Steuerelement Größe und Position. Es kann entweder eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT](../../mfc/reference/rect-structure1.md) Struktur.  
  
 `pParentWnd`  
 Gibt die Link-Steuerelement übergeordnetes Fenster. Er darf nicht sein `NULL`.  
  
 `nID`  
 Gibt die Link-Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die Initialisierung erfolgreich war; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von [erstellen](#create) Erweiterte Windows-Style-Konstanten angewendet.  
  
 Die zweite Form der `CreateEx` Methode ist veraltet. Die erste Form, der angibt, die `lpszLinkMarkup` Parameter.  
  
##  <a name="getidealheight"></a>CLinkCtrl::GetIdealHeight  
 Ruft die optimale Höhe der Link-Steuerelement ab.  
  
```  
int GetIdealHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die optimale Höhe des Steuerelements in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [LM_GETIDEALHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb760716), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getidealsize"></a>CLinkCtrl::GetIdealSize  
 Berechnet die bevorzugte Höhe der Text des Links für das aktuelle Linksteuerelement, je nach der angegebenen Breite des Links.  
  
```  
int GetIdealSize(
    int cxMaxWidth,   
    SIZE* pSize) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `cxMaxWidth`|Die maximale Breite der Verbindung, in Pixel.|  
|[Out] *`pSize`|Ein Zeiger auf ein Windows [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur. Bei dieser Methode wird die `cy` Mitglied der `SIZE` Struktur enthält die ideale Link Texthöhe für die Breite der Link-Text, der durch angegeben ist `cxMaxWidth`. Der `cx` Member der Struktur enthält die Breite der Link-Text, der tatsächlich benötigt wird.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die bevorzugte Höhe des Link-Texts in Pixel. Der Rückgabewert ist identisch mit der Wert der `cy` Mitglied der `SIZE` Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Ein Beispiel für die `GetIdealSize` -Methode finden Sie im Beispiel [CLinkCtrl::Create](#create).  
  
 Diese Methode sendet die [LM_GETIDEALSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760718) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getitem"></a>CLinkCtrl::GetItem  
 Ruft die Zustände und die Attribute eines Elements der Link-Steuerelement.  
  
```  
BOOL GetItem(PLITEM pItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pItem`  
 Ein Zeiger auf eine [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) Struktur, um Informationen zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getitemid"></a>CLinkCtrl::GetItemID  
 Ruft die ID des Elements ein Link-Steuerelement ab.  
  
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
 Der Index eines Elements der Link-Steuerelement.  
  
 *strID*  
 Ein [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, das die ID des angegebenen Elements enthält.  
  
 *szID*  
 Eine auf Null endende Zeichenfolge, die die ID des angegebenen Elements enthält.  
  
 *cchID*  
 Die Größe in Zeichen von der *SzID* Puffer.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
> [!NOTE]
>  Diese Funktion gibt auch **FALSE** Wenn der Puffer des *SzID oder StrID* ist kleiner als **MAX_LINKID_TEXT**.  
  
### <a name="remarks"></a>Hinweise  
 Ruft die ID des Elements einen bestimmten Link-Steuerelement ab. Weitere Informationen finden Sie unter Win32-Meldung [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getitemstate"></a>CLinkCtrl::GetItemState  
 Ruft den Zustand des Elements Link-Steuerelement.  
  
```  
BOOL GetItemState(
    int iLink,  
    UINT* pnState,  
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `iLink`  
 Der Index eines Elements der Link-Steuerelement.  
  
 `pnState`  
 Der Wert des angegebenen Elements.  
  
 `stateMask`  
 Kombination von Flags, beschreiben die Status-Element abgerufen. Eine Liste der Werte finden Sie unter der Beschreibung der **Status** Element in der [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) Struktur. Zulässige Elemente sind identisch mit denen **Zustand**.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Ruft den Wert des angegebenen Elements in der einen bestimmten Link-Steuerelement ein Element ab. Weitere Informationen finden Sie unter Win32-Meldung [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getitemurl"></a>CLinkCtrl::GetItemUrl  
 Ruft die URL durch die Link-Steuerelement ein Element dargestellt wird.  
  
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
 Der Index eines Elements der Link-Steuerelement.  
  
 `strUrl`  
 Ein [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, das die URL dargestellt, die durch das angegebene Element enthält  
  
 `szUrl`  
 Eine Null endende Zeichenfolge, die mit der URL, die durch das angegebene Element dargestellt wird  
  
 *cchUrl*  
 Die Größe in Zeichen von der *SzURL* Puffer.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
> [!NOTE]
>  Diese Funktion gibt auch **FALSE** Wenn der Puffer des *SzUrl oder StrUrl* ist kleiner als **MAX_LINKID_TEXT**.  
  
### <a name="remarks"></a>Hinweise  
 Ruft die URL, die durch den angegebenen Link-Steuerelement ein Element dargestellt wird. Weitere Informationen finden Sie unter Win32-Meldung [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="hittest"></a>CLinkCtrl::HitTest  
 Bestimmt, ob der Benutzer den angegebenen Link geklickt hat.  
  
```  
BOOL HitTest(PLHITTESTINFO phti) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *phti*  
 Zeiger auf eine **LHITTESTINFO** -Struktur, enthält keine Informationen über den Link geklickt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [LM_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb760722), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setitem"></a>CLinkCtrl::SetItem  
 Legt fest, die Zustände und die Attribute eines Elements der Link-Steuerelement.  
  
```  
BOOL SetItem(PLITEM pItem);
```  
  
### <a name="parameters"></a>Parameter  
 `pItem`  
 Ein Zeiger auf eine [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) Struktur mit den Informationen festlegen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setitemid"></a>CLinkCtrl::SetItemID  
 Ruft die ID des Elements ein Link-Steuerelement ab.  
  
```  
BOOL SetItemID(
    int iLink,  
    LPCWSTR szID);
```  
  
### <a name="parameters"></a>Parameter  
 `iLink`  
 Der Index eines Elements der Link-Steuerelement.  
  
 *szID*  
 Eine auf Null endende Zeichenfolge, die die ID des angegebenen Elements enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Legt die ID des Elements einen bestimmten Link-Steuerelement fest. Weitere Informationen finden Sie unter Win32-Meldung [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setitemstate"></a>CLinkCtrl::SetItemState  
 Ruft den Zustand des Elements Link-Steuerelement.  
  
```  
BOOL SetItemState(
    int iLink,  
    UINT state,  
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED);
```  
  
### <a name="parameters"></a>Parameter  
 `iLink`  
 Der Index eines Elements der Link-Steuerelement.  
  
 `pnState`  
 Der Wert des angegebenen Elements festgelegt wird.  
  
 `stateMask`  
 Kombination von Flags, beschreiben das State-Element festgelegt wird. Eine Liste der Werte finden Sie unter der Beschreibung der **Status** Element in der [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) Struktur. Zulässige Elemente sind identisch mit denen **Zustand**.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Legt den Wert des angegebenen Elements in der einen bestimmten Link-Steuerelement ein Element. Weitere Informationen finden Sie unter Win32-Meldung [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setitemurl"></a>CLinkCtrl::SetItemUrl  
 Legt die URL durch die Link-Steuerelement ein Element dargestellt wird.  
  
```  
BOOL SetItemUrl(
    int iLink,  
    LPCWSTR szUrl);
```  
  
### <a name="parameters"></a>Parameter  
 `iLink`  
 Der Index eines Elements der Link-Steuerelement.  
  
 `szUrl`  
 Eine Null endende Zeichenfolge, die mit der URL, die durch das angegebene Element dargestellt wird  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Legt die URL, die durch den angegebenen Link-Steuerelement ein Element dargestellt wird. Weitere Informationen finden Sie unter Win32-Meldung [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)

