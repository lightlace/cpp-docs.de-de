---
title: ATL-Typedefs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlcore/ATL::_ATL_BASE_MODULE
- atlbase/ATL::_ATL_COM_MODULE
- atlbase/ATL::_ATL_MODULE
- atlbase/ATL::_ATL_WIN_MODULE
- atlutil/ATL::ATL_URL_PORT
- atlbase/ATL::CComDispatchDriver
- atlbase/ATL::CComGlobalsThreadModel
- atlbase/ATL::CComObjectThreadModel
- atlwin/ATL::CContainedWindow
- atlpath/ATL::CPath
- atlpath/ATL::CPathA
- atlpath/ATL::CPathW
- " atlsimpcoll/ATL::CSimpleValArray"
- " atlutil/ATL::LPCURL"
- atlbase/ATL::DefaultThreadTraits
- atlutil/ATL::LPURL
dev_langs:
- C++
helpviewer_keywords:
- typedefs, ATL
- typedefs
- ATL, typedefs
ms.assetid: 7dd05baa-3efb-4e3b-af23-793c610f4560
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9d721cefd20ae5eb208c74d973069fb9365273d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="atl-typedefs"></a>ATL-Typdefinitionen
Der Active Template Library enthält die folgenden typedefs-Elementen.  
  
|||  
|-|-|  
|[_ATL_BASE_MODULE](#_atl_base_module)|Definiert als Typedef basierend auf [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md).|  
|[_ATL_COM_MODULE](#_atl_com_module)|Definiert als Typedef basierend auf [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md).|  
|[_ATL_MODULE](#_atl_module)|Definiert als Typedef basierend auf [_ATL_MODULE70](../../atl/reference/atl-module70-structure.md).|  
|[_ATL_WIN_MODULE](#_atl_win_module)|Definiert als Typedef basierend auf [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)|  
|[ATL_URL_PORT](#atl_url_port)|Vom verwendeten [CUrl](../../atl/reference/curl-class.md) für keine Portnummer angeben.|  
|[CComDispatchDriver](#ccomdispatchdriver)|Diese Klasse verwaltet die COM-Schnittstellenzeiger auf.|  
|[CComGlobalsThreadModel](#ccomglobalsthreadmodel)|Ruft den entsprechenden Thread Objektmodellmethoden, unabhängig von der verwendeten Threadingmodell.|  
|[CComObjectThreadModel](#ccomobjectthreadmodel)|Ruft den entsprechenden Thread Objektmodellmethoden, unabhängig von der verwendeten Threadingmodell.|  
|[CContainedWindow](#ccontainedwindow)|Diese Klasse ist eine Spezialisierung der **CContainedWindow.**|  
|[CPath](#cpath)|Eine Spezialisierung der [CPathT](../../atl/reference/cpatht-class.md) mit `CString`.|  
|[CPathA](#cpatha)|Eine Spezialisierung der [CPathT](../../atl/reference/cpatht-class.md) mit `CStringA`.|  
|[CPathW](#cpathw)|Eine Spezialisierung der [CPathT](../../atl/reference/cpatht-class.md) mit `CStringW`.|  
|[CSimpleValArray](#csimplevalarray)|Stellt ein Array zum Speichern von einfachen Typen.|  
|[DefaultThreadTraits](#defaultthreadtraits)|Die Standardeinstellung Thread trait-Klasse.|  
|[LPCURL](#lpcurl)|Ein Zeiger auf eine Konstante [CUrl](../../atl/reference/curl-class.md) Objekt.|  
|[LPURL](#lpurl)|Ein Zeiger auf eine [CUrl](../../atl/reference/curl-class.md) Objekt.|  
  
##  <a name="_atl_base_module"></a>_ATL_BASE_MODULE  
 Definiert als Typedef basierend auf _ATL_BASE_MODULE70.  
  
```   
typedef ATL::_ATL_BASE_MODULE70 _ATL_BASE_MODULE;   
```  
  
### <a name="remarks"></a>Hinweise  
 In jedem ATL-Projekt verwendet. Basierend auf [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md).  
  
 Klassen Teil der ATL-Modulklassen 7.0 sind abgeleitet werden, aus der _ATL_BASE_MODULE-Struktur.  Weitere Informationen zu ATL-Modulklassen, finden Sie unter [com-Module Klassen](../../atl/com-modules-classes.md).  

## <a name="requirements"></a>Anforderungen
**Header:** atlcore.h

##  <a name="_atl_com_module"></a>_ATL_COM_MODULE  
 Definiert als Typedef basierend auf _ATL_COM_MODULE70.  
  
```   
typedef ATL::_ATL_COM_MODULE70 _ATL_COM_MODULE;   
```  
  
### <a name="remarks"></a>Hinweise  
 Verwendet von ATL-Projekte, die COM-Funktionen verwenden. Basierend auf [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md).  

## <a name="requirements"></a>Anforderungen
**Header:** atlbase.h
  
##  <a name="_atl_module"></a>_ATL_MODULE  
 Definiert als Typedef basierend auf _ATL_MODULE70.  
  
```   
typedef ATL::_ATL_MODULE70 _ATL_MODULE;   
```  
## <a name="requirements"></a>Anforderungen
**Header:** 
  
### <a name="remarks"></a>Hinweise  
 Basierend auf [_ATL_MODULE70](../../atl/reference/atl-module70-structure.md).  
  
##  <a name="_atl_win_module"></a>_ATL_WIN_MODULE  
 Definiert als Typedef basierend auf _ATL_WIN_MODULE70.  
  
```   
typedef ATL::_ATL_WIN_MODULE70 _ATL_WIN_MODULE; 
 
```  
  
### <a name="remarks"></a>Hinweise  
 Verwendet von ATL-Projekte die Windowing-Features verwenden. Basierend auf [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md).  

## <a name="requirements"></a>Anforderungen
**Header:** atlbase.h 
  
##  <a name="atl_url_port"></a>ATL_URL_PORT 
  Vom verwendeten [CUrl](curl-class.md) für keine Portnummer angeben.
```  
typedef WORD ATL_URL_PORT;
```  

## <a name="requirements"></a>Anforderungen
**Header:** atlutil.h

##  <a name="ccomdispatchdriver"></a>CComDispatchDriver  
 Diese Klasse verwaltet die COM-Schnittstellenzeiger auf.  
  
```   
typedef CComQIPtr<IDispatch, &__uuidof(IDispatch)> CComDispatchDriver;   
```  
## <a name="requirements"></a>Anforderungen
**Header:** atlbase.h
  
##  <a name="ccomglobalsthreadmodel"></a>CComGlobalsThreadModel  
 Ruft den entsprechenden Thread Objektmodellmethoden, unabhängig von der verwendeten Threadingmodell.  
  
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
 Je nach Threadingmodell von Ihrer Anwendung verwendet die `typedef` Namen `CComGlobalsThreadModel` verweist entweder [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) oder [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md). Diese Klassen bieten zusätzliche `typedef` Namen auf eine kritischen Abschnittsklasse verweisen.  
  
> [!NOTE]
> `CComGlobalsThreadModel`verweist nicht auf die Klasse [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).  
  
 Mithilfe von `CComGlobalsThreadModel` erspart Ihnen das Angeben einer bestimmten Threadingmodell Modellklasse. Unabhängig von der Threadingmodell verwendet wird werden die entsprechenden Methoden aufgerufen werden.  
  
 Zusätzlich zu `CComGlobalsThreadModel`, ATL stellt die `typedef` Namen [CComObjectThreadModel](#ccomobjectthreadmodel). Die Klasse verwiesen, die von jedem `typedef` hängt von der Threadingmodell verwendet, wie in der folgenden Tabelle dargestellt:  
  
|Typedef|Single-threading|Apartmentthreading|Freies threading|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S = `CComSingleThreadModel`; M =`CComMultiThreadModel`  
  
 Verwendung `CComObjectThreadModel` innerhalb einer einzelnen Objektklasse. Verwendung `CComGlobalsThreadModel` in ein Objekt, die global für Ihr Programm verfügbar ist, oder wenn Sie über mehrere Threads hinweg Modulressourcen schützen möchten.  

## <a name="requirements"></a>Anforderungen
**Header:** atlbase.h
  
##  <a name="ccomobjectthreadmodel"></a>CComObjectThreadModel  
 Ruft den entsprechenden Thread Objektmodellmethoden, unabhängig von der verwendeten Threadingmodell.  
  
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
 Je nach Threadingmodell von Ihrer Anwendung verwendet die `typedef` Namen `CComObjectThreadModel` verweist entweder [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) oder [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md). Diese Klassen bieten zusätzliche `typedef` Namen auf eine kritischen Abschnittsklasse verweisen.  
  
> [!NOTE]
> `CComObjectThreadModel`verweist nicht auf die Klasse [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).  
  
 Mithilfe von `CComObjectThreadModel` erspart Ihnen das Angeben einer bestimmten Threadingmodell Modellklasse. Unabhängig von der Threadingmodell verwendet wird werden die entsprechenden Methoden aufgerufen werden.  
  
 Zusätzlich zu `CComObjectThreadModel`, ATL stellt die `typedef` Namen [CComGlobalsThreadModel](#ccomglobalsthreadmodel). Die Klasse verwiesen, die von jedem `typedef` hängt von der Threadingmodell verwendet, wie in der folgenden Tabelle dargestellt:  
  
|Typedef|Single-threading|Apartmentthreading|Freies threading|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S = `CComSingleThreadModel`; M =`CComMultiThreadModel`  
  
 Verwendung `CComObjectThreadModel` innerhalb einer einzelnen Objektklasse. Verwendung `CComGlobalsThreadModel` in ein Objekt, das entweder global verfügbar sind, für Ihr Programm ist, oder wenn Sie über mehrere Threads hinweg Modulressourcen schützen möchten.  

## <a name="requirements"></a>Anforderungen
**Header:** atlbase.h
  
##  <a name="ccontainedwindow"></a>CContainedWindow  
 Diese Klasse ist eine Spezialisierung der **CContainedWindow.**  
  
```   
typedef CContainedWindowT<CWindow> CContainedWindow;   
```  

## <a name="requirements"></a>Anforderungen
**Header:** atlwin.h vorhanden
  
### <a name="remarks"></a>Hinweise  
 `CContainedWindow`ist eine Spezialisierung der [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md). Wenn Sie die Basisklasse oder die Merkmale ändern möchten, verwenden Sie `CContainedWindowT` direkt.  
  
##  <a name="cpath"></a>CPath  
 Eine Spezialisierung der [CPathT](../../atl/reference/cpatht-class.md) mit `CString`.  
  
```   
typedef CPathT<CString> CPath;   
```  

## <a name="requirements"></a>Anforderungen
**Header:** atlpath.h
  
##  <a name="cpatha"></a>CPathA  
 Eine Spezialisierung der [CPathT](../../atl/reference/cpatht-class.md) mit `CStringA`.  
  
```   
typedef CPathT<CStringA> CPathA;   
```

## <a name="requirements"></a>Anforderungen
**Header:** atlpath.h  
  
##  <a name="cpathw"></a>CPathW  
 Eine Spezialisierung der [CPathT](../../atl/reference/cpatht-class.md) mit `CStringW`.  
  
```   
typedef ATL::CPathT<CStringW> CPathW;   
```  
## <a name="requirements"></a>Anforderungen
**Header:** atlpath.h
  
##  <a name="csimplevalarray"></a>CSimpleValArray  
 Stellt ein Array zum Speichern von einfachen Typen.  
  
```   
#define CSimpleValArray CSimpleArray   
```  

  
### <a name="remarks"></a>Hinweise  
 `CSimpleValArray`wird zum Erstellen und Verwalten von Arrays mit einfachen Datentypen bereitgestellt. Es ist eine einfache #define von [CSimpleArray](../../atl/reference/csimplearray-class.md).  


## <a name="requirements"></a>Anforderungen
**Header:** atlsimpcoll.h
  
##  <a name="lpcurl"></a>LPCURL  
 Ein Zeiger auf eine Konstante [CUrl](../../atl/reference/curl-class.md) Objekt.  
  
```   
typedef const CUrl* LPCURL;   
```  

## <a name="requirements"></a>Anforderungen
**Header:** atlutil.h

##  <a name="defaultthreadtraits"></a>DefaultThreadTraits
Die Standardeinstellung Thread trait-Klasse.

### <a name="syntax"></a>Syntax
```  
      #if defined(_MT)  
   typedef CRTThreadTraits DefaultThreadTraits;  
#else  
   typedef Win32ThreadTraits DefaultThreadTraits;  
#endif  
```

## <a name="remarks"></a>Hinweise
Wenn das aktuelle Projekt die Multithread-CTR verwendet wird, wird als CRTThreadTraits DefaultThreadTraits definiert. Andernfalls wird Win32ThreadTraits verwendet.


## <a name="requirements"></a>Anforderungen
**Header:** atlbase.h
  
##  <a name="lpurl"></a>LPURL  
 Ein Zeiger auf eine [CUrl](../../atl/reference/curl-class.md) Objekt.  
  
```   
typedef CUrl* LPURL;   
```  

## <a name="requirements"></a>Anforderungen
**Header:** atlutil.h


## <a name="see-also"></a>Siehe auch  
 [ATL COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)   
 [Funktionen](../../atl/reference/atl-functions.md)   
 [Global Variables (Globale Variablen)](../../atl/reference/atl-global-variables.md)   
 [Strukturen](../../atl/reference/atl-structures.md)   
 [Makros](../../atl/reference/atl-macros.md)   
 [Klassen](../../atl/reference/atl-classes.md)