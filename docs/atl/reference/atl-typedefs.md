---
title: ATL-Typedefs | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs:
- C++
helpviewer_keywords:
- typedefs, ATL
- typedefs
- ATL, typedefs
ms.assetid: 7dd05baa-3efb-4e3b-af23-793c610f4560
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
ms.sourcegitcommit: 347e7bf7cd9173fb2815f44fc052ec23ab4055a6
ms.openlocfilehash: aa57212b602538e4e8d2854c6075562e72472796
ms.lasthandoff: 02/24/2017

---
# <a name="atl-typedefs"></a>ATL-Typdefinitionen
Der Active Template Library umfasst die folgenden Typedefs.  
  
|||  
|-|-|  
|[_ATL_BASE_MODULE](#_atl_base_module)|Definiert, wie eine Typedef, die auf der Grundlage [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md).|  
|[_ATL_COM_MODULE](#_atl_com_module)|Definiert, wie eine Typedef, die auf der Grundlage [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md).|  
|[_ATL_MODULE](#_atl_module)|Definiert, wie eine Typedef, die auf der Grundlage [_ATL_MODULE70](../../atl/reference/atl-module70-structure.md).|  
|[_ATL_WIN_MODULE](#_atl_win_module)|Definiert, wie eine Typedef, die auf der Grundlage [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)|  
|[ATL_URL_PORT](#atl_url_port)|Vom verwendeten [CUrl](../../atl/reference/curl-class.md) für eine Portnummer angeben.|  
|[CComDispatchDriver](#ccomdispatchdriver)|Diese Klasse verwaltet die COM-Schnittstellenzeiger.|  
|[CComGlobalsThreadModel](#ccomglobalsthreadmodel)|Ruft den entsprechenden Thread Objektmodellmethoden, unabhängig von der threading-Modell verwendet wird.|  
|[CComObjectThreadModel](#ccomobjectthreadmodel)|Ruft den entsprechenden Thread Objektmodellmethoden, unabhängig von der threading-Modell verwendet wird.|  
|[CContainedWindow](#ccontainedwindow)|Diese Klasse ist eine Spezialisierung der **CContainedWindow.**|  
|[CPath](#cpath)|Eine Spezialisierung der [CPathT](../../atl/reference/cpatht-class.md) mit `CString`.|  
|[CPathA](#cpatha)|Eine Spezialisierung der [CPathT](../../atl/reference/cpatht-class.md) mit `CStringA`.|  
|[CPathW](#cpathw)|Eine Spezialisierung der [CPathT](../../atl/reference/cpatht-class.md) mit `CStringW`.|  
|[CSimpleValArray](#csimplevalarray)|Stellt ein Array zum Speichern von einfachen Typen.|  
|[DefaultThreadTraits](#defaultthreadtraits)|Der Standard-Thread-Traits-Klasse.|  
|[LPCURL](#lpcurl)|Ein Zeiger auf eine Konstante [CUrl](../../atl/reference/curl-class.md) Objekt.|  
|[LPURL](#lpurl)|Ein Zeiger auf eine [CUrl](../../atl/reference/curl-class.md) Objekt.|  
  
##  <a name="a-nameatlbasemodulea--atlbasemodule"></a><a name="_atl_base_module"></a>_ATL_BASE_MODULE  
 Definiert, wie eine Typedef, die basierend auf _ATL_BASE_MODULE70.  
  
```   
typedef ATL::_ATL_BASE_MODULE70 _ATL_BASE_MODULE;   
```  
  
### <a name="remarks"></a>Hinweise  
 In jedem ATL-Projekt verwendet. Auf der Grundlage [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md).  
  
 Klassen, die Teil der ATL-Modulklassen 7.0 leiten Sie von der _ATL_BASE_MODULE-Struktur.  Weitere Informationen zu ATL-Modulklassen, finden Sie unter [com-Module Klassen](../../atl/com-modules-classes.md).  
  
##  <a name="a-nameatlcommodulea--atlcommodule"></a><a name="_atl_com_module"></a>_ATL_COM_MODULE  
 Definiert, wie eine Typedef, die basierend auf _ATL_COM_MODULE70.  
  
```   
typedef ATL::_ATL_COM_MODULE70 _ATL_COM_MODULE;   
```  
  
### <a name="remarks"></a>Hinweise  
 Verwendet von ATL-Projekte, die COM-Funktionen verwenden. Auf der Grundlage [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md).  
  
##  <a name="a-nameatlmodulea--atlmodule"></a><a name="_atl_module"></a>_ATL_MODULE  
 Definiert, wie eine Typedef, die basierend auf _ATL_MODULE70.  
  
```   
typedef ATL::_ATL_MODULE70 _ATL_MODULE;   
```  
  
### <a name="remarks"></a>Hinweise  
 Auf der Grundlage [_ATL_MODULE70](../../atl/reference/atl-module70-structure.md).  
  
##  <a name="a-nameatlwinmodulea--atlwinmodule"></a><a name="_atl_win_module"></a>_ATL_WIN_MODULE  
 Definiert, wie eine Typedef, die basierend auf _ATL_WIN_MODULE70.  
  
```   
typedef ATL::_ATL_WIN_MODULE70 _ATL_WIN_MODULE; 
 
```  
  
### <a name="remarks"></a>Hinweise  
 Verwendet von ATL-Projekte die Windowing-Funktionen verwenden. Auf der Grundlage [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md).  
  
##  <a name="a-nameatlurlporta--atlurlport"></a><a name="atl_url_port"></a>ATL_URL_PORT 
  Vom verwendeten [CUrl](curl-class.md) für eine Portnummer angeben.
```  
typedef WORD ATL_URL_PORT;
```  

##  <a name="a-nameccomdispatchdrivera--ccomdispatchdriver"></a><a name="ccomdispatchdriver"></a>CComDispatchDriver  
 Diese Klasse verwaltet die COM-Schnittstellenzeiger.  
  
```   
typedef CComQIPtr<IDispatch, &__uuidof(IDispatch)> CComDispatchDriver;   
```  
  
##  <a name="a-nameccomglobalsthreadmodela--ccomglobalsthreadmodel"></a><a name="ccomglobalsthreadmodel"></a>CComGlobalsThreadModel  
 Ruft den entsprechenden Thread Objektmodellmethoden, unabhängig von der threading-Modell verwendet wird.  
  
```   
#if defined(_ATL_SINGLE_THREADED)  
typedef CComSingleThreadModel CComGlobalsThreadModel;  
#elif defined(_ATL_APARTMENT_THREADED)  
typedef CComMultiThreadModel CComGlobalsThreadModel;  
#elif defined(_ATL_FREE_THREADED)  
typedef CComMultiThreadModel CComGlobalsThreadModel;  
#else  
#pragma message ("No global threading model defined")  
#endif   
```  
  
### <a name="remarks"></a>Hinweise  
 Je nach der von der Anwendung verwendeten Threadingmodell der `typedef` Namen `CComGlobalsThreadModel` verweist entweder auf [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) oder [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md). Diese Klassen bieten zusätzliche `typedef` Namen auf eine kritischen Abschnittsklasse verweisen.  
  
> [!NOTE]
> `CComGlobalsThreadModel`verweist nicht auf die Klasse [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).  
  
 Mithilfe von `CComGlobalsThreadModel` erspart Ihnen das Angeben einer bestimmten threading Modellklasse. Unabhängig von der threading-Modell verwendet wird werden die entsprechenden Methoden aufgerufen werden.  
  
 Zusätzlich zu `CComGlobalsThreadModel`, ATL stellt die `typedef` Namen [CComObjectThreadModel](#ccomobjectthreadmodel). Die Klasse verwiesen, die von den einzelnen `typedef` hängt von der threading-Modell verwendet, wie in der folgenden Tabelle dargestellt:  
  
|typedef|Single-threading|Apartmentthreading|Freies threading|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S= `CComSingleThreadModel`; M =`CComMultiThreadModel`  
  
 Verwendung `CComObjectThreadModel` in ein einzelnes Objekt-Klasse. Verwendung `CComGlobalsThreadModel` in ein Objekt Global an Ihr Programm verfügbar ist oder wenn Modulressourcen über mehrere Threads geschützt werden sollen.  
  
##  <a name="a-nameccomobjectthreadmodela--ccomobjectthreadmodel"></a><a name="ccomobjectthreadmodel"></a>CComObjectThreadModel  
 Ruft den entsprechenden Thread Objektmodellmethoden, unabhängig von der threading-Modell verwendet wird.  
  
```   
#if defined(_ATL_SINGLE_THREADED)  
typedef CComSingleThreadModel CComObjectThreadModel;  
#elif defined(_ATL_APARTMENT_THREADED)  
typedef CComSingleThreadModel CComObjectThreadModel;  
#elif defined(_ATL_FREE_THREADED)  
typedef CComMultiThreadModel CComObjectThreadModel;  
#else  
#pragma message ("No global threading model defined")  
#endif   
```  
  
### <a name="remarks"></a>Hinweise  
 Je nach der von der Anwendung verwendeten Threadingmodell der `typedef` Namen `CComObjectThreadModel` verweist entweder auf [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) oder [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md). Diese Klassen bieten zusätzliche `typedef` Namen auf eine kritischen Abschnittsklasse verweisen.  
  
> [!NOTE]
> `CComObjectThreadModel`verweist nicht auf die Klasse [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).  
  
 Mithilfe von `CComObjectThreadModel` erspart Ihnen das Angeben einer bestimmten threading Modellklasse. Unabhängig von der threading-Modell verwendet wird werden die entsprechenden Methoden aufgerufen werden.  
  
 Zusätzlich zu `CComObjectThreadModel`, ATL stellt die `typedef` Namen [CComGlobalsThreadModel](#ccomglobalsthreadmodel). Die Klasse verwiesen, die von den einzelnen `typedef` hängt von der threading-Modell verwendet, wie in der folgenden Tabelle dargestellt:  
  
|typedef|Single-threading|Apartmentthreading|Freies threading|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S= `CComSingleThreadModel`; M =`CComMultiThreadModel`  
  
 Verwendung `CComObjectThreadModel` in ein einzelnes Objekt-Klasse. Verwendung `CComGlobalsThreadModel` in ein Objekt, das entweder global verfügbar, das Programm, oder wenn Sie über mehrere Threads hinweg Modulressourcen schützen möchten.  
  
##  <a name="a-nameccontainedwindowa--ccontainedwindow"></a><a name="ccontainedwindow"></a>CContainedWindow  
 Diese Klasse ist eine Spezialisierung der **CContainedWindow.**  
  
```   
typedef CContainedWindowT<CWindow> CContainedWindow;   
```  
  
### <a name="remarks"></a>Hinweise  
 `CContainedWindow`ist eine Spezialisierung von [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md). Wenn Sie die Basisklasse oder die Merkmale ändern möchten, verwenden Sie `CContainedWindowT` direkt.  
  
##  <a name="a-namecpatha--cpath"></a><a name="cpath"></a>CPath  
 Eine Spezialisierung der [CPathT](../../atl/reference/cpatht-class.md) mit `CString`.  
  
```   
typedef CPathT<CString> CPath;   
```  
  
##  <a name="a-namecpathaa--cpatha"></a><a name="cpatha"></a>CPathA  
 Eine Spezialisierung der [CPathT](../../atl/reference/cpatht-class.md) mit `CStringA`.  
  
```   
typedef CPathT<CStringA> CPathA;   
```  
  
##  <a name="a-namecpathwa--cpathw"></a><a name="cpathw"></a>CPathW  
 Eine Spezialisierung der [CPathT](../../atl/reference/cpatht-class.md) mit `CStringW`.  
  
```   
typedef ATL::CPathT<CStringW> CPathW;   
```  
  
##  <a name="a-namecsimplevalarraya--csimplevalarray"></a><a name="csimplevalarray"></a>CSimpleValArray  
 Stellt ein Array zum Speichern von einfachen Typen.  
  
```   
#define CSimpleValArray CSimpleArray   
```  
  
### <a name="remarks"></a>Hinweise  
 `CSimpleValArray`Dient zum Erstellen und Verwalten von Arrays mit einfachen Datentypen. Es ist eine einfache #define des [CSimpleArray](../../atl/reference/csimplearray-class.md).  
  
##  <a name="a-namelpcurla--lpcurl"></a><a name="lpcurl"></a>LPCURL  
 Ein Zeiger auf eine Konstante [CUrl](../../atl/reference/curl-class.md) Objekt.  
  
```   
typedef const CUrl* LPCURL;   
```  

##  <a name="a-namedefaultthreadtraitsa--defaultthreadtraits"></a><a name="defaultthreadtraits"></a>DefaultThreadTraits
Der Standard-Thread-Traits-Klasse.

### <a name="syntax"></a>Syntax
```  
      #if defined(_MT)  
   typedef CRTThreadTraits DefaultThreadTraits;  
#else  
   typedef Win32ThreadTraits DefaultThreadTraits;  
#endif  
```

## <a name="remarks"></a>Hinweise
Wenn das aktuelle Projekt die Multithread-CTR verwendet wird, wird DefaultThreadTraits als CRTThreadTraits definiert. Andernfalls wird Win32ThreadTraits verwendet.
  
##  <a name="a-namelpurla--lpurl"></a><a name="lpurl"></a>LPURL  
 Ein Zeiger auf eine [CUrl](../../atl/reference/curl-class.md) Objekt.  
  
```   
typedef CUrl* LPURL;   
```  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)   
 [Funktionen](../../atl/reference/atl-functions.md)   
 [Globale Variablen](../../atl/reference/atl-global-variables.md)   
 [Strukturen](../../atl/reference/atl-structures.md)   
 [Makros](../../atl/reference/atl-macros.md)   
 [Klassen](../../atl/reference/atl-classes.md)
