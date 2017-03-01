---
title: CNetAddressCtrl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CNetAddressCtrl class
ms.assetid: cb4c6aca-3f49-4b52-b76c-65f57096155b
caps.latest.revision: 32
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
ms.openlocfilehash: 03b08d13a9e456c5533b4dddce7f389a63a69c6d
ms.lasthandoff: 02/24/2017

---
# <a name="cnetaddressctrl-class"></a>CNetAddressCtrl-Klasse
Die Klasse `CNetAddressCtrl` stellt das Netzwerkadressen-Steuerelement dar, das verwendet werden kann, um IPv4-, IPv6- und benannte DNS-Adressen einzugeben und ihr Format zu überprüfen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CNetAddressCtrl : public CEdit  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CNetAddressCtrl::CNetAddressCtrl](#cnetaddressctrl)|Erstellt ein `CNetAddressCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CNetAddressCtrl::Create](#create)|Erstellt eine Netzwerkadressen-Steuerelement mit der angegebenen Formate und fügt Sie es mit dem aktuellen `CNetAddressCtrl` Objekt.|  
|[CNetAddressCtrl::CreateEx](#createex)|Erstellt eine Netzwerkadressen-Steuerelement mit dem angegebenen erweiterten Stile und fügt Sie es mit dem aktuellen `CNetAddressCtrl` Objekt.|  
|[CNetAddressCtrl::DisplayErrorTip](#displayerrortip)|Zeigt eine SprechblasenInfo Fehler, wenn der Benutzer eine nicht unterstützte Netzwerkadresse in der aktuellen Netzwerkadressen-Steuerelement eingibt.|  
|[CNetAddressCtrl::GetAddress](#getaddress)|Ruft eine Darstellung überprüfte und analysierte die Netzwerkadresse, die die aktuellen Netzwerkadressen-Steuerelement zugeordnet.|  
|[CNetAddressCtrl::GetAllowType](#getallowtype)|Ruft den Typ der Adresse, die die aktuellen Netzwerkadressen-Steuerelement unterstützt werden.|  
|[CNetAddressCtrl::SetAllowType](#setallowtype)|Legt den Typ der Adresse, die die aktuellen Netzwerkadressen-Steuerelement unterstützt werden.|  
  
## <a name="remarks"></a>Hinweise  
 Die Netzwerkadressen-Steuerelement stellt sicher, dass das Format der vom Benutzer eingegebene Adresse richtig ist. Das Steuerelement wird an die Netzwerkadresse nicht tatsächlich verbinden. Die [CNetAddressCtrl::SetAllowType](#setallowtype) Methode gibt einen oder mehrere Typen von Adresse, die [CNetAddressCtrl::GetAddress](#getaddress) Methode analysieren und überprüfen kann. Eine Adresse kann in Form eines IPv4, IPv6- oder angegebene Adresse für einen Server, Netzwerk, Host oder Broadcastnachricht Ziel sein. Wenn das Format der Adresse falsch ist, können Sie die [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) Methode, um ein Meldungsfeld Infotipp anzuzeigen, die grafisch in das Textfeld ein, der die Netzwerkadressen-Steuerelement und vordefinierte eine Fehlermeldung angezeigt.  
  
 Die `CNetAddressCtrl` abgeleitete Klasse wird von der [CEdit](../../mfc/reference/cedit-class.md) Klasse. Daher stellt das Netzwerkadressen-Steuerelement Zugriff auf alle Windows-Edit-Steuerelement Nachrichten bereit.  
  
 Die folgende Abbildung zeigt einen Dialog, der einem Netzwerkadressen-Steuerelement enthält. Der Text im Feld (1) für das Netzwerkadressen-Steuerelement enthält eine ungültige Netzwerkadresse. Die QuickInfo-Meldung (2) wird angezeigt, wenn die Adresse ungültig ist.  
  
 ![Dialogfeld mit einem Netzwerkadressen-Steuerelement und Infotipps. ] (../../mfc/reference/media/cnetaddctrl.png "Cnetaddctrl")  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird ein Teil eines Dialogfelds, das eine Netzwerkadresse überprüft. Die Ereignishandler für drei Optionsfelder angeben, dass die Netzwerkadresse einer von drei Adresstypen kann. Der Benutzer gibt eine Adresse in das Textfeld der Netzwerkadressen-Steuerelement und dann eine drückt, um die Adresse zu überprüfen. Wenn die Adresse gültig ist, wird eine Erfolgsmeldung angezeigt. Andernfalls wird die Fehlermeldung vordefinierte Infotipp angezeigt.  
  
 [!code-cpp[NVC_MFC_CNetAddressCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_1.cpp)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird von der Dialogfeld-Headerdatei definiert die [NC_ADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb773345) und [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346) Variablen, die erforderlich sind die [CNetAddressCtrl::GetAddress](#getaddress) Methode.  
  
 [!code-cpp[NVC_MFC_CNetAddressCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_2.h)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 `CNetAddressCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
 Diese Klasse wird in unterstützt [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] und höher.  
  
 Zusätzliche Anforderungen für diese Klasse finden Sie im [erstellen Anforderungen für Windows Vista-Standardsteuerelementen](../../mfc/build-requirements-for-windows-vista-common-controls.md).  
  
##  <a name="a-namecnetaddressctrla--cnetaddressctrlcnetaddressctrl"></a><a name="cnetaddressctrl"></a>CNetAddressCtrl::CNetAddressCtrl  
 Erstellt ein `CNetAddressCtrl`-Objekt.  
  
```  
CNetAddressCtrl();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CNetAddressCtrl::Create](#create) oder [CNetAddressCtrl::CreateEx](#createex) Methode, um ein Netzwerk-Steuerelement erstellen, und fügen Sie es auf die `CNetAddressCtrl` Objekt.  
  
##  <a name="a-namecreatea--cnetaddressctrlcreate"></a><a name="create"></a>CNetAddressCtrl::Create  
 Erstellt eine Netzwerkadressen-Steuerelement mit der angegebenen Formate und fügt Sie es mit dem aktuellen `CNetAddressCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `dwStyle`|Eine bitweise Kombination der Formate auf das Steuerelement angewendet werden. Weitere Informationen finden Sie unter [Stile bearbeiten](../../mfc/reference/edit-styles.md).|  
|[in] `rect`|Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Position und Größe des Steuerelements enthält.|  
|[in] `pParentWnd`|Ein nicht-Null-Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Steuerelements ist.|  
|[in] `nID`|Die ID des Steuerelements.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
##  <a name="a-namecreateexa--cnetaddressctrlcreateex"></a><a name="createex"></a>CNetAddressCtrl::CreateEx  
 Erstellt eine Netzwerkadressen-Steuerelement mit dem angegebenen erweiterten Stile und fügt Sie es mit dem aktuellen `CNetAddressCtrl` Objekt.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,   
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `dwExStyle`|Eine bitweise Kombination (OR) Erweiterte Stile auf das Steuerelement angewendet werden. Weitere Informationen finden Sie unter der `dwExStyle` Parameter von der [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Funktion.|  
|[in] `dwStyle`|Eine bitweise Kombination (OR) der Formate auf das Steuerelement angewendet werden. Weitere Informationen finden Sie unter [Stile bearbeiten](../../mfc/reference/edit-styles.md).|  
|[in] `rect`|Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Position und Größe des Steuerelements enthält.|  
|[in] `pParentWnd`|Ein nicht-Null-Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Steuerelements ist.|  
|[in] `nID`|Die ID des Steuerelements.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
##  <a name="a-namedisplayerrortipa--cnetaddressctrldisplayerrortip"></a><a name="displayerrortip"></a>CNetAddressCtrl::DisplayErrorTip  
 Zeigt eine Fehlermeldung in die SprechblasenInfo, die die aktuellen Netzwerkadressen-Steuerelement zugeordnet ist.  
  
```  
HRESULT DisplayErrorTip();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert `S_OK` ist diese Methode erfolgreich war, andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CNetAddressCtrl::SetAllowType](#setallowtype) Methode, um die Typen von Adressen angeben, die die aktuellen Netzwerkadressen-Steuerelement unterstützt werden. Verwenden der [CNetAddressCtrl::GetAddress](#getaddress) Methode zum Überprüfen und analysieren die Netzwerkadresse, die der Benutzer eingibt. Verwenden der [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) Methode Infotipp Nachricht Fehler anzeigen, wenn die [CNetAddressCtrl::GetAddress](#getaddress) Methode nicht erfolgreich ist.  
  
 Diese Nachricht Ruft die [NetAddr_DisplayErrorTip](http://msdn.microsoft.com/library/windows/desktop/bb774314) -Makro, das in beschriebene der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Dieses Makro sendet die `NCM_DISPLAYERRORTIP` Nachricht.  
  
##  <a name="a-namegetaddressa--cnetaddressctrlgetaddress"></a><a name="getaddress"></a>CNetAddressCtrl::GetAddress  
 Ruft eine geprüfte und analysierte Darstellung der Netzwerkadresse, die die aktuellen Netzwerkadressen-Steuerelement zugeordnet ist.  
  
```  
HRESULT GetAddress(PNC_ADDRESS pAddress) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in, out] `pAddress`|Zeiger auf eine [NC_ADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb773345) Struktur.  Festlegen der `pAddrInfo` Member dieser Struktur auf die Adresse einer [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346) Struktur vor dem Aufrufen der GetAddress-Methode.|  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert `S_OK` ist diese Methode erfolgreich war, andernfalls ein COM-Fehlercode. Weitere Informationen zu den möglichen Fehlercodes finden Sie im Abschnitt "Rückgabewert" von der [NetAddr_GetAddress](http://msdn.microsoft.com/library/windows/desktop/bb774316) Makro.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Methode erfolgreich ist, ist die [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346) Struktur enthält zusätzliche Informationen über die Netzwerkadresse.  
  
 Verwenden der [CNetAddressCtrl::SetAllowType](#setallowtype) Methode, um die Typen von Adressen angeben, kann die aktuellen Netzwerkadressen-Steuerelement unterstützt. Verwenden der [CNetAddressCtrl::GetAddress](#getaddress) Methode zum Überprüfen und analysieren die Netzwerkadresse, die der Benutzer eingibt. Verwenden der [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) Methode Infotipp Nachricht Fehler anzeigen, wenn die [CNetAddressCtrl::GetAddress](#getaddress) Methode nicht erfolgreich ist.  
  
 Diese Methode ruft die [NetAddr_GetAddress](http://msdn.microsoft.com/library/windows/desktop/bb774316) -Makro, das in beschriebene der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Dieses Makro sendet die `NCM_GETADDRESS` Nachricht.  
  
##  <a name="a-namegetallowtypea--cnetaddressctrlgetallowtype"></a><a name="getallowtype"></a>CNetAddressCtrl::GetAllowType  
 Ruft den Typ der Adresse, die die aktuellen Netzwerkadressen-Steuerelement unterstützt werden.  
  
```  
DWORD GetAllowType() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine bitweise Kombination (OR) von Flags, die angibt, welche Adressen unterstützen das Netzwerkadressen-Steuerelement. Weitere Informationen finden Sie unter [NET_STRING](http://msdn.microsoft.com/library/windows/desktop/bb762586).  
  
### <a name="remarks"></a>Hinweise  
 Diese Nachricht Ruft die [NetAddr_GetAllowType](http://msdn.microsoft.com/library/windows/desktop/bb774318) -Makro, das in beschriebene der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Dieses Makro sendet die `NCM_GETALLOWTYPE` Nachricht.  
  
##  <a name="a-namesetallowtypea--cnetaddressctrlsetallowtype"></a><a name="setallowtype"></a>CNetAddressCtrl::SetAllowType  
 Legt den Typ der Adresse, die die aktuellen Netzwerkadressen-Steuerelement unterstützt werden.  
  
```  
HRESULT SetAllowType(DWORD dwAddrMask);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `dwAddrMask`|Eine bitweise Kombination (OR) von Flags, die angibt, welche Adressen unterstützen das Netzwerkadressen-Steuerelement. Weitere Informationen finden Sie unter [NET_STRING](http://msdn.microsoft.com/library/windows/desktop/bb762586).|  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Wenn diese Methode erfolgreich ist; andernfalls ein COM-Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CNetAddressCtrl::SetAllowType](#setallowtype) Methode, um die Typen von Adressen angeben, die die aktuellen Netzwerkadressen-Steuerelement unterstützt werden. Verwenden der [CNetAddressCtrl::GetAddress](#getaddress) Methode zum Überprüfen und analysieren die Netzwerkadresse, die der Benutzer eingibt. Verwenden der [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) Methode Infotipp Nachricht Fehler anzeigen, wenn die [CNetAddressCtrl::GetAddress](#getaddress) Methode nicht erfolgreich ist.  
  
 Diese Nachricht Ruft die [NetAddr_SetAllowType](http://msdn.microsoft.com/library/windows/desktop/bb774320) -Makro, das in beschriebene der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Dieses Makro sendet die `NCM_SETALLOWTYPE` Nachricht.  
  
## <a name="see-also"></a>Siehe auch  
 [CNetAddressCtrl-Klasse](../../mfc/reference/cnetaddressctrl-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CEdit-Klasse](../../mfc/reference/cedit-class.md)

