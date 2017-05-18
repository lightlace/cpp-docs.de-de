---
title: Klasse CAxWindow2T | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 22
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
ms.sourcegitcommit: 1a00023e4d3e31ddb6381e90a50231449b1de18d
ms.openlocfilehash: a0724b0ea8922d1f39d8cf7ccd630068c32ea3ac
ms.contentlocale: de-de
ms.lasthandoff: 02/28/2017

---
# <a name="caxwindow2t-class"></a>CAxWindow2T-Klasse
Diese Klasse stellt Methoden zum Bearbeiten eines Fensters, das ein ActiveX-Steuerelement hostet und auch Unterstützung für das Hosten von lizenzierter ActiveX-Steuerelementen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class TBase = CWindow>
    class CAxWindow2T :
    public CAxWindowT<TBase>
```  
  
#### <a name="parameters"></a>Parameter  
 *TBase*  
 Die Klasse, von der `CAxWindowT` abgeleitet wird.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAxWindow2T::CAxWindow2T](#caxwindow2t)|Erstellt ein `CAxWindow2T`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAxWindow2T::Create](#create)|Erstellt ein Hostfenster.|  
|[CAxWindow2T::CreateControlLic](#createcontrollic)|Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster.|  
|[CAxWindow2T::CreateControlLicEx](#createcontrollicex)|Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es, hostet es im angegebenen Fenster und ruft einen Schnittstellenzeiger (oder Zeiger) des Steuerelements ab.|  
|[CAxWindow2T::GetWndClassName](#getwndclassname)|Statische Methode, die den Namen der Window-Klasse abruft.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAxWindow2T::operator =](#operator_eq)|Weist eine `HWND` zu einer vorhandenen `CAxWindow2T` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CAxWindow2T`Stellt Methoden zum Bearbeiten eines Fensters, hostet ein ActiveX-Steuerelement bereit. `CAxWindow2T`Außerdem verfügt über Unterstützung für das Hosten von lizenzierter ActiveX-Steuerelementen. Das hosting erfolgt über " **AtlAxWinLic80**", die vom umschlossen ist `CAxWindow2T`.  
  
 Klasse `CAxWindow2` wird als eine Spezialisierung der implementiert die `CAxWindow2T` Klasse. Diese Spezialisierung wird folgendermaßen deklariert:  
  
 `typedef CAxWindow2T <CWindow> CAxWindow2;`  
  
> [!NOTE]
> `CAxWindowT`Mitglieder sind unter dokumentiert [CAxWindow](../../atl/reference/caxwindow-class.md).  
  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, das die Member dieser Klasse verwendet.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `TBase`  
  
 `CAxWindowT`  
  
 `CAxWindow2T`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  
  
##  <a name="caxwindow2t"></a>CAxWindow2T::CAxWindow2T  
 Erstellt ein `CAxWindow2T`-Objekt.  
  
```
CAxWindow2T(HWND  hWnd = NULL) : CAxWindowT<TBase>(hWnd)
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 Ein Handle für ein vorhandenes Fenster.  
  
##  <a name="create"></a>CAxWindow2T::Create  
 Erstellt ein Hostfenster.  
  
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
 `CAxWindow2T::Create`Aufrufe [CWindow::Create](../../atl/reference/cwindow-class.md#create) mit der `LPCTSTR lpstrWndClass` Parameter festgelegt werden, um die Fensterklasse, das Hosten von Steuerelementen bereitstellt ( **AtlAxWinLic80**).  
  
 Finden Sie unter `CWindow::Create` eine Beschreibung der Parameter und Rückgabewert.  
  
 **Hinweis** 0 als Wert für wird der `MenuOrID` -Parameter muss angegeben werden, als 0 HE (Standardwert), einen Compilerfehler zu vermeiden.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel mit `CAxWindow2T::Create`.  
  
##  <a name="createcontrollic"></a>CAxWindow2T::CreateControlLic  
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
 `bstrLicKey`  
 Der Lizenzschlüssel für das Steuerelement; NULL, wenn ein Steuerelement Lizenzpaketdatei erstellen.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [CAxWindow::CreateControl](../../atl/reference/caxwindow-class.md#createcontrol) eine Beschreibung der verbleibenden Parameter und Rückgabewert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel mit `CAxWindow2T::CreateControlLic`.  
  
##  <a name="createcontrollicex"></a>CAxWindow2T::CreateControlLicEx  
 Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es, hostet es im angegebenen Fenster und ruft einen Schnittstellenzeiger (oder Zeiger) des Steuerelements ab.  
  
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
 `bstrLicKey`  
 Der Lizenzschlüssel für das Steuerelement; NULL, wenn ein Steuerelement Lizenzpaketdatei erstellen.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [CAxWindow::CreateControlEx](../../atl/reference/caxwindow-class.md#createcontrolex) eine Beschreibung der verbleibenden Parameter und Rückgabewert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel mit `CAxWindow2T::CreateControlLicEx`.  
  
##  <a name="getwndclassname"></a>CAxWindow2T::GetWndClassName  
 Ruft den Namen der Fensterklasse ab.  
  
```
static LPCTSTR GetWndClassName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen der Fensterklasse ( **AtlAxWinLic80**) lizenzierte und Lizenzpaketdatei ActiveX-Steuerelemente hosten können.  
  
##  <a name="operator_eq"></a>CAxWindow2T::operator =  
 Weist eine `HWND` zu einer vorhandenen `CAxWindow2T` Objekt.  
  
```
CAxWindow2T<TBase>& operator= (HWND hWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 Ein Handle für ein vorhandenes Fenster.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Steuerelementcontainern – häufig gestellte Fragen](../../atl/atl-control-containment-faq.md)

