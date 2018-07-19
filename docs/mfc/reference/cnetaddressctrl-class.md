---
title: CNetAddressCtrl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CNetAddressCtrl
- AFXCMN/CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::Create
- AFXCMN/CNetAddressCtrl::CreateEx
- AFXCMN/CNetAddressCtrl::DisplayErrorTip
- AFXCMN/CNetAddressCtrl::GetAddress
- AFXCMN/CNetAddressCtrl::GetAllowType
- AFXCMN/CNetAddressCtrl::SetAllowType
dev_langs:
- C++
helpviewer_keywords:
- CNetAddressCtrl [MFC], CNetAddressCtrl
- CNetAddressCtrl [MFC], Create
- CNetAddressCtrl [MFC], CreateEx
- CNetAddressCtrl [MFC], DisplayErrorTip
- CNetAddressCtrl [MFC], GetAddress
- CNetAddressCtrl [MFC], GetAllowType
- CNetAddressCtrl [MFC], SetAllowType
ms.assetid: cb4c6aca-3f49-4b52-b76c-65f57096155b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c58090351829f6a12ae90d56e8985bf615966f65
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852269"
---
# <a name="cnetaddressctrl-class"></a>CNetAddressCtrl-Klasse
Die Klasse `CNetAddressCtrl` stellt das Netzwerkadressen-Steuerelement dar, das verwendet werden kann, um IPv4-, IPv6- und benannte DNS-Adressen einzugeben und ihr Format zu überprüfen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CNetAddressCtrl : public CEdit  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CNetAddressCtrl::CNetAddressCtrl](#cnetaddressctrl)|Erstellt ein `CNetAddressCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CNetAddressCtrl::Create](#create)|Erstellt eine Netzwerkadressen-Steuerelement mit der angegebenen Formate und hängt es an der aktuellen `CNetAddressCtrl` Objekt.|  
|[CNetAddressCtrl::CreateEx](#createex)|Erstellt eine Netzwerkadressen-Steuerelement mit dem angegebenen erweiterten Stile und hängt es an der aktuellen `CNetAddressCtrl` Objekt.|  
|[CNetAddressCtrl::DisplayErrorTip](#displayerrortip)|Zeigt eine SprechblasenInfo für Fehler, wenn der Benutzer eine nicht unterstützte Netzwerkadresse in der aktuellen Netzwerkadressen-Steuerelement eingibt.|  
|[CNetAddressCtrl::GetAddress](#getaddress)|Ruft eine Darstellung überprüft und analysiert die Netzwerkadresse, die die aktuellen Netzwerkadressen-Steuerelement zugeordnete ab.|  
|[CNetAddressCtrl::GetAllowType](#getallowtype)|Ruft den Typ der Netzwerkadresse, die die aktuellen Netzwerkadressen-Steuerelement unterstützt werden.|  
|[CNetAddressCtrl::SetAllowType](#setallowtype)|Legt fest, den Typ der Netzwerkadresse, die die aktuellen Netzwerkadressen-Steuerelement unterstützt werden.|  
  
## <a name="remarks"></a>Hinweise  
 Das Netzwerkadressen-Steuerelement stellt sicher, dass das Format der vom Benutzer eingegebene Adresse richtig ist. Das Steuerelement ist nicht tatsächlich an die Netzwerkadresse eine Verbindung herstellen. Die [CNetAddressCtrl::SetAllowType](#setallowtype) Methode gibt einen oder mehrere Typen der Adresse, die die [CNetAddressCtrl::GetAddress](#getaddress) Methode analysieren und überprüfen kann. Eine Adresse kann in Form einer IPv4, IPv6- oder benannte Adresse für einen Server, Netzwerk, Host oder -Broadcastnachricht Ziel sein. Wenn das Format der Adresse falsch ist, können Sie die [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) Methode, um ein Meldungsfeld Infotipp anzuzeigen, die grafisch verweist auf das Textfeld ein, der das Netzwerkadressen-Steuerelement und zeigt eine vordefinierte Fehlermeldung.  
  
 Die `CNetAddressCtrl` abgeleitete Klasse wird die [CEdit](../../mfc/reference/cedit-class.md) Klasse. Das Netzwerkadressen-Steuerelement bietet daher den Zugriff auf alle Windows bearbeiten-Steuerelement-Nachrichten.  
  
 Die folgende Abbildung zeigt ein Dialogfeld, das eine Netzwerkadressen-Steuerelement enthält. Der Text Box (1) für das Netzwerkadressen-Steuerelement enthält eine ungültige Netzwerk-Adresse. Die QuickInfo-Meldung (2) wird angezeigt, wenn die Netzwerkadresse ungültig ist.  
  
 ![Dialogfeld mit einem Netzwerkadressen-Steuerelement und Infotipps. ] (../../mfc/reference/media/cnetaddctrl.png "Cnetaddctrl")  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird ein Teil eines Dialogfelds, das eine Netzwerkadresse überprüft. Die Ereignishandler für drei Optionsfeldern angeben, dass die Netzwerkadresse auf einem von drei Adresstypen sein kann. Der Benutzer gibt eine Adresse in das Textfeld des Netzwerk-Steuerelements, und dann eine drückt, um die Adresse zu überprüfen. Wenn die Adresse gültig ist, wird eine Erfolgsmeldung angezeigt; Andernfalls wird die Fehlermeldung für den vordefinierten Infotipp angezeigt.  
  
 [!code-cpp[NVC_MFC_CNetAddressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_1.cpp)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird aus der Dialogfeld-Headerdatei definiert die [NC_ADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb773345) und [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346) Variablen, die erforderlich sind die [CNetAddressCtrl::GetAddress](#getaddress)Methode.  
  
 [!code-cpp[NVC_MFC_CNetAddressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_2.h)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 `CNetAddressCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
 Diese Klasse wird von unterstützt [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] und höher.  
  
 Zusätzliche Anforderungen für diese Klasse werden in beschrieben [erstellen Anforderungen für Windows Vista-Standardsteuerelementen](../../mfc/build-requirements-for-windows-vista-common-controls.md).  
  
##  <a name="cnetaddressctrl"></a>  CNetAddressCtrl::CNetAddressCtrl  
 Erstellt ein `CNetAddressCtrl`-Objekt.  
  
```  
CNetAddressCtrl();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CNetAddressCtrl::Create](#create) oder [CNetAddressCtrl::CreateEx](#createex) Methode zum Erstellen eines Netzwerk-Steuerelements, und fügen Sie ihn auf die `CNetAddressCtrl` Objekt.  
  
##  <a name="create"></a>  CNetAddressCtrl::Create  
 Erstellt eine Netzwerkadressen-Steuerelement mit der angegebenen Formate und hängt es an der aktuellen `CNetAddressCtrl` Objekt.  
  
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
|[in] *DwStyle*|Eine bitweise Kombination der Formate auf das Steuerelement angewendet werden. Weitere Informationen finden Sie unter [Stile bearbeiten](../../mfc/reference/styles-used-by-mfc.md#edit-styles).|  
|[in] *Rect*|Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Position und Größe des Steuerelements enthält.|  
|[in] *pParentWnd*|Ein nicht-Null-Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Steuerelements ist.|  
|[in] *nID*|Die ID des Steuerelements.|  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn diese Methode erfolgreich ist. andernfalls "false".  
  
##  <a name="createex"></a>  CNetAddressCtrl::CreateEx  
 Erstellt eine Netzwerkadressen-Steuerelement mit dem angegebenen erweiterten Stile und hängt es an der aktuellen `CNetAddressCtrl` Objekt.  
  
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
|[in] *DwExStyle*|Eine bitweise Kombination (OR) von erweiterten Stile, die auf das Steuerelement angewendet werden. Weitere Informationen finden Sie unter den *DwExStyle* Parameter, der die [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Funktion.|  
|[in] *DwStyle*|Eine bitweise Kombination (OR) von Formatvorlagen, die auf das Steuerelement angewendet werden. Weitere Informationen finden Sie unter [Stile bearbeiten](../../mfc/reference/styles-used-by-mfc.md#edit-styles).|  
|[in] *Rect*|Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Position und Größe des Steuerelements enthält.|  
|[in] *pParentWnd*|Ein nicht-Null-Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Steuerelements ist.|  
|[in] *nID*|Die ID des Steuerelements.|  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn diese Methode erfolgreich ist. andernfalls "false".  
  
##  <a name="displayerrortip"></a>  CNetAddressCtrl::DisplayErrorTip  
 Zeigt eine Fehlermeldung in der QuickInfo-Sprechblase, die die aktuellen Netzwerkadressen-Steuerelement zugeordnet ist.  
  
```  
HRESULT DisplayErrorTip();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert `S_OK` , wenn diese Methode erfolgreich; andernfalls ist ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CNetAddressCtrl::SetAllowType](#setallowtype) Methode, um die Typen von Adressen anzugeben, die die aktuellen Netzwerkadressen-Steuerelement unterstützt werden. Verwenden der [CNetAddressCtrl::GetAddress](#getaddress) Methode, um zu überprüfen und analysieren die Netzwerkadresse, die der Benutzer eingibt. Verwenden der [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) Methode einen Fehler Nachricht Infotipp anzuzeigen, wenn die [CNetAddressCtrl::GetAddress](#getaddress) Methode nicht erfolgreich ist.  
  
 Diese Nachricht Ruft die [NetAddr_DisplayErrorTip](http://msdn.microsoft.com/library/windows/desktop/bb774314) Makro, das im Windows SDK beschrieben wird. Dieses Makro sendet die `NCM_DISPLAYERRORTIP` Nachricht.  
  
##  <a name="getaddress"></a>  CNetAddressCtrl::GetAddress  
 Ruft eine Darstellung überprüfte und analysierte die Netzwerkadresse, die die aktuellen Netzwerkadressen-Steuerelement zugeordnet ist.  
  
```  
HRESULT GetAddress(PNC_ADDRESS pAddress) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in, out] *pAddress*|Zeiger auf ein [NC_ADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb773345) Struktur.  Legen Sie die *pAddrInfo* Member der Struktur an die Adresse des eine [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346) strukturieren, bevor Sie die GetAddress-Methode aufrufen.|  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert S_OK zurück, wenn diese Methode erfolgreich ist; andernfalls, eine COM-Fehlercode. Weitere Informationen zu den möglichen Fehlercodes finden Sie im Abschnitt Rückgabewert der [NetAddr_GetAddress](http://msdn.microsoft.com/library/windows/desktop/bb774316) Makro.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Methode erfolgreich ist, ist die [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346) Struktur enthält zusätzliche Informationen über die Netzwerkadresse.  
  
 Verwenden der [CNetAddressCtrl::SetAllowType](#setallowtype) Methode, um die Typen von Adressen anzugeben, kann die aktuellen Netzwerkadressen-Steuerelement zu unterstützen. Verwenden der [CNetAddressCtrl::GetAddress](#getaddress) Methode, um zu überprüfen und analysieren die Netzwerkadresse, die der Benutzer eingibt. Verwenden der [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) Methode einen Fehler Nachricht Infotipp anzuzeigen, wenn die [CNetAddressCtrl::GetAddress](#getaddress) Methode nicht erfolgreich ist.  
  
 Diese Methode ruft die [NetAddr_GetAddress](http://msdn.microsoft.com/library/windows/desktop/bb774316) Makro, das im Windows SDK beschrieben wird. Dieses Makro sendet die Nachricht NCM_GETADDRESS.  
  
##  <a name="getallowtype"></a>  CNetAddressCtrl::GetAllowType  
 Ruft den Typ der Netzwerkadresse, die die aktuellen Netzwerkadressen-Steuerelement unterstützt werden.  
  
```  
DWORD GetAllowType() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine bitweise Kombination (OR) von Flags, die angibt, die Typen von Adressen unterstützen das Netzwerkadressen-Steuerelement. Weitere Informationen finden Sie unter [NET_STRING](http://msdn.microsoft.com/library/windows/desktop/bb762586).  
  
### <a name="remarks"></a>Hinweise  
 Diese Nachricht Ruft die [NetAddr_GetAllowType](http://msdn.microsoft.com/library/windows/desktop/bb774318) Makro, das im Windows SDK beschrieben wird. Dieses Makro sendet die Nachricht NCM_GETALLOWTYPE.  
  
##  <a name="setallowtype"></a>  CNetAddressCtrl::SetAllowType  
 Legt fest, den Typ der Netzwerkadresse, die die aktuellen Netzwerkadressen-Steuerelement unterstützt werden.  
  
```  
HRESULT SetAllowType(DWORD dwAddrMask);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] *DwAddrMask*|Eine bitweise Kombination (OR) von Flags, die angibt, die Typen von Adressen unterstützen das Netzwerkadressen-Steuerelement. Weitere Informationen finden Sie unter [NET_STRING](http://msdn.microsoft.com/library/windows/desktop/bb762586).|  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn diese Methode erfolgreich ist; andernfalls, eine COM-Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CNetAddressCtrl::SetAllowType](#setallowtype) Methode, um die Typen von Adressen anzugeben, die die aktuellen Netzwerkadressen-Steuerelement unterstützt werden. Verwenden der [CNetAddressCtrl::GetAddress](#getaddress) Methode, um zu überprüfen und analysieren die Netzwerkadresse, die der Benutzer eingibt. Verwenden der [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) Methode einen Fehler Nachricht Infotipp anzuzeigen, wenn die [CNetAddressCtrl::GetAddress](#getaddress) Methode nicht erfolgreich ist.  
  
 Diese Nachricht Ruft die [NetAddr_SetAllowType](http://msdn.microsoft.com/library/windows/desktop/bb774320) Makro, das im Windows SDK beschrieben wird. Dieses Makro sendet die Nachricht NCM_SETALLOWTYPE.  
  
## <a name="see-also"></a>Siehe auch  
 [CNetAddressCtrl-Klasse](../../mfc/reference/cnetaddressctrl-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CEdit-Klasse](../../mfc/reference/cedit-class.md)
