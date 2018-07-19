---
title: CAxWindow2T-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAxWindow2T
- ATLWIN/ATL::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::Create
- ATLWIN/ATL::CAxWindow2T::CreateControlLic
- ATLWIN/ATL::CAxWindow2T::CreateControlLicEx
- ATLWIN/ATL::CAxWindow2T::GetWndClassName
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow2 class
ms.assetid: b87bc943-7991-4537-b902-2138d7f4d837
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ad57d843aad19d5df51f2a6f0261df857eb280e9
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885131"
---
# <a name="caxwindow2t-class"></a>CAxWindow2T-Klasse
Diese Klasse stellt Methoden zum Bearbeiten eines Fensters, das ein ActiveX-Steuerelement hostet, und bietet auch Unterstützung für die lizenzierten ActiveX-Steuerelemente hosten.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class TBase = CWindow>
    class CAxWindow2T :
    public CAxWindowT<TBase>
```  
  
#### <a name="parameters"></a>Parameter  
 *TBase*  
 Die Klasse, von der `CAxWindowT` abgeleitet wird.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAxWindow2T::CAxWindow2T](#caxwindow2t)|Erstellt ein `CAxWindow2T`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAxWindow2T::Create](#create)|Erstellt ein Hostfenster an.|  
|[CAxWindow2T::CreateControlLic](#createcontrollic)|Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster.|  
|[CAxWindow2T::CreateControlLicEx](#createcontrollicex)|Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert wird, hostet es im angegebenen Fenster und ruft einen Schnittstellenzeiger (oder Zeiger) aus dem Steuerelement ab.|  
|[CAxWindow2T::GetWndClassName](#getwndclassname)|Statische Methode, die den Namen der Fensterklasse abruft.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAxWindow2T::operator =](#operator_eq)|Weist ein HWND zu einem vorhandenen `CAxWindow2T` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CAxWindow2T` Stellt Methoden zum Bearbeiten eines Fensters, hostet ein ActiveX-Steuerelement bereit. `CAxWindow2T` bietet auch Unterstützung für das Hosten von lizenzierter ActiveX-Steuerelementen. Das hosting erfolgt über " **AtlAxWinLic80**", der umschlossen ist `CAxWindow2T`.  
  
 Klasse `CAxWindow2` wird als eine Spezialisierung der implementiert die `CAxWindow2T` Klasse. Diese Spezialisierung wird folgendermaßen deklariert:  
  
 `typedef CAxWindow2T <CWindow> CAxWindow2;`  
  
> [!NOTE]
> `CAxWindowT` Elemente sind unter dokumentiert [CAxWindow](../../atl/reference/caxwindow-class.md).  
  
 Finden Sie unter [Hosten von ActiveX-Steuerelemente mithilfe von ATL-xhost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, die Member dieser Klasse verwendet.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `TBase`  
  
 `CAxWindowT`  
  
 `CAxWindow2T`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  
  
##  <a name="caxwindow2t"></a>  CAxWindow2T::CAxWindow2T  
 Erstellt ein `CAxWindow2T`-Objekt.  
  
```
CAxWindow2T(HWND  hWnd = NULL) : CAxWindowT<TBase>(hWnd)
```  
  
### <a name="parameters"></a>Parameter  
 *hWnd*  
 Ein Handle eines vorhandenen-Fensters.  
  
##  <a name="create"></a>  CAxWindow2T::Create  
 Erstellt ein Hostfenster an.  
  
```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```  
  
### <a name="remarks"></a>Hinweise  
 `CAxWindow2T::Create` Aufrufe [CWindow::Create](../../atl/reference/cwindow-class.md#create) mit der LPCTSTR *LpstrWndClass* Parameter festgelegt wird, um die Fensterklasse, das Steuerelementhosting bereitstellt (`AtlAxWinLic80`).  
  
 Finden Sie unter `CWindow::Create` eine Beschreibung der Parameter und Rückgabewert.  
  
 **Beachten Sie** Wenn 0, als Wert für verwendet wird die *MenuOrID* -Parameter muss als 0 HE angegeben werden (Standardwert), einen Compilerfehler zu vermeiden.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [Hosten von ActiveX-Steuerelemente mithilfe von ATL-xhost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, verwendet `CAxWindow2T::Create`.  
  
##  <a name="createcontrollic"></a>  CAxWindow2T::CreateControlLic  
 Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster.  
  
```
HRESULT CreateControlLic(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);

HRESULT CreateControlLic(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *bstrLicKey*  
 Der Lizenzschlüssel des Steuerelements; NULL, wenn ein Lizenzpaketdatei Steuerelement zu erstellen.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [CAxWindow::CreateControl](../../atl/reference/caxwindow-class.md#createcontrol) eine Beschreibung der verbleibende Parameter und Rückgabewert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [Hosten von ActiveX-Steuerelemente mithilfe von ATL-xhost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, verwendet `CAxWindow2T::CreateControlLic`.  
  
##  <a name="createcontrollicex"></a>  CAxWindow2T::CreateControlLicEx  
 Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert wird, hostet es im angegebenen Fenster und ruft einen Schnittstellenzeiger (oder Zeiger) aus dem Steuerelement ab.  
  
```
HRESULT CreateControlLicEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLicKey = NULL);

    HRESULT CreateControlLicEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLickey = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *bstrLicKey*  
 Der Lizenzschlüssel des Steuerelements; NULL, wenn ein Lizenzpaketdatei Steuerelement zu erstellen.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [CAxWindow::CreateControlEx](../../atl/reference/caxwindow-class.md#createcontrolex) eine Beschreibung der verbleibende Parameter und Rückgabewert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [Hosten von ActiveX-Steuerelemente mithilfe von ATL-xhost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, verwendet `CAxWindow2T::CreateControlLicEx`.  
  
##  <a name="getwndclassname"></a>  CAxWindow2T::GetWndClassName  
 Ruft den Namen der Fensterklasse ab.  
  
```
static LPCTSTR GetWndClassName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen der Fensterklasse (`AtlAxWinLic80`) lizenzierter und vollständiger Lizenzpaketdatei ActiveX-Steuerelemente hosten kann.  
  
##  <a name="operator_eq"></a>  CAxWindow2T::operator =  
 Weist ein HWND zu einem vorhandenen `CAxWindow2T` Objekt.  
  
```
CAxWindow2T<TBase>& operator= (HWND hWnd);
```  
  
### <a name="parameters"></a>Parameter  
 *hWnd*  
 Ein Handle eines vorhandenen-Fensters.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Steuerelementkapselung – häufig gestellte Fragen](../../atl/atl-control-containment-faq.md)
