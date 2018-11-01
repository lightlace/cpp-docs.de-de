---
title: ATL-Typedefs
ms.date: 11/04/2016
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
helpviewer_keywords:
- typedefs, ATL
- typedefs
- ATL, typedefs
ms.assetid: 7dd05baa-3efb-4e3b-af23-793c610f4560
ms.openlocfilehash: c723d76f17ad1c74ab98e7348450cea3f03c4d78
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429314"
---
# <a name="atl-typedefs"></a>ATL-Typedefs

Die Active Template Library enthält die folgenden typedefs-Elementen.

|||
|-|-|
|[_ATL_BASE_MODULE](#_atl_base_module)|Definiert als Typedef basierend auf [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md).|
|[_ATL_COM_MODULE](#_atl_com_module)|Definiert als Typedef basierend auf [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md).|
|[_ATL_MODULE](#_atl_module)|Definiert als Typedef basierend auf [_ATL_MODULE70](../../atl/reference/atl-module70-structure.md).|
|[_ATL_WIN_MODULE](#_atl_win_module)|Definiert als Typedef basierend auf [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)|
|[ATL_URL_PORT](#atl_url_port)|Der Typ, der von verwendeten [CUrl](../../atl/reference/curl-class.md) für Sie keine Portnummer angeben.|
|[CComDispatchDriver](#ccomdispatchdriver)|Diese Klasse verwaltet die COM-Schnittstellenzeiger.|
|[CComGlobalsThreadModel](#ccomglobalsthreadmodel)|Ruft den entsprechenden Thread Objektmodellmethoden, unabhängig davon, das threading-Modell verwendet wird.|
|[CComObjectThreadModel](#ccomobjectthreadmodel)|Ruft den entsprechenden Thread Objektmodellmethoden, unabhängig davon, das threading-Modell verwendet wird.|
|[CContainedWindow](#ccontainedwindow)|Diese Klasse ist eine Spezialisierung der `CContainedWindowT`.|
|[CPath](#cpath)|Eine Spezialisierung der [CPathT](../../atl/reference/cpatht-class.md) mit `CString`.|
|[CPathA](#cpatha)|Eine Spezialisierung der [CPathT](../../atl/reference/cpatht-class.md) mit `CStringA`.|
|[CPathW](#cpathw)|Eine Spezialisierung der [CPathT](../../atl/reference/cpatht-class.md) mit `CStringW`.|
|[CSimpleValArray](#csimplevalarray)|Ein Array zum Speichern von einfachen Typen darstellt.|
|[DefaultThreadTraits](#defaultthreadtraits)|Der Standard-Thread-Traits-Klasse.|
|[LPCURL](#lpcurl)|Ein Zeiger auf eine Konstante [CUrl](../../atl/reference/curl-class.md) Objekt.|
|[LPURL](#lpurl)|Ein Zeiger auf eine [CUrl](../../atl/reference/curl-class.md) Objekt.|

##  <a name="_atl_base_module"></a>  _ATL_BASE_MODULE

Eine Typedef, die basierend auf _ATL_BASE_MODULE70 definiert.

```
typedef ATL::_ATL_BASE_MODULE70 _ATL_BASE_MODULE;
```

### <a name="remarks"></a>Hinweise

In jedem ATL-Projekt verwendet. Basierend auf [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md).

Klassen Bestandteil der ATL 7.0-Modul-Klassen sind abgeleitet werden, aus der _ATL_BASE_MODULE-Struktur.  Weitere Informationen zu ATL-Modulklassen, finden Sie unter [COM-Modulklassen](../../atl/com-modules-classes.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlcore.h

##  <a name="_atl_com_module"></a>  _ATL_COM_MODULE

Eine Typedef, die basierend auf _ATL_COM_MODULE70 definiert.

```
typedef ATL::_ATL_COM_MODULE70 _ATL_COM_MODULE;
```

### <a name="remarks"></a>Hinweise

Verwendet von ATL-Projekte, die COM-Funktionen verwenden. Basierend auf [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="_atl_module"></a>  _ATL_MODULE

Eine Typedef, die basierend auf _ATL_MODULE70 definiert.

```
typedef ATL::_ATL_MODULE70 _ATL_MODULE;
```

## <a name="requirements"></a>Anforderungen

**Header:**

### <a name="remarks"></a>Hinweise

Basierend auf [_ATL_MODULE70](../../atl/reference/atl-module70-structure.md).

##  <a name="_atl_win_module"></a>  _ATL_WIN_MODULE

Eine Typedef, die basierend auf _ATL_WIN_MODULE70 definiert.

```
typedef ATL::_ATL_WIN_MODULE70 _ATL_WIN_MODULE;
```

### <a name="remarks"></a>Hinweise

Ein, die alle ATL-Projekte die Windowing-Funktionen verwenden. Basierend auf [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="atl_url_port"></a>  ATL_URL_PORT

Der Typ, der von verwendeten [CUrl](curl-class.md) für Sie keine Portnummer angeben.

```
typedef WORD ATL_URL_PORT;
```

## <a name="requirements"></a>Anforderungen

**Header:** "atlutil.h"

##  <a name="ccomdispatchdriver"></a>  CComDispatchDriver

Diese Klasse verwaltet die COM-Schnittstellenzeiger.

```
typedef CComQIPtr<IDispatch, &__uuidof(IDispatch)> CComDispatchDriver;
```

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="ccomglobalsthreadmodel"></a>  CComGlobalsThreadModel

Ruft den entsprechenden Thread Objektmodellmethoden, unabhängig davon, das threading-Modell verwendet wird.

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

Je nach den threading-Modell, die von Ihrer Anwendung verwendet die **Typedef** Namen `CComGlobalsThreadModel` verweist entweder auf [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) oder [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md). Diese Klassen bieten zusätzliche `typedef` Namen auf eine kritischen Abschnitt-Klasse verweisen.

> [!NOTE]
> `CComGlobalsThreadModel` verweist nicht auf Klasse [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).

Mithilfe von `CComGlobalsThreadModel` erspart Ihnen das Angeben einer bestimmten threading Modellklasse. Unabhängig von der threading-Modell verwendet wird werden die entsprechenden Methoden aufgerufen werden.

Zusätzlich zu `CComGlobalsThreadModel`, ATL stellt die **Typedef** Namen [CComObjectThreadModel](#ccomobjectthreadmodel). Die Klasse, die auf die verwiesen wird von den einzelnen `typedef` , hängt das Threadingmodell verwendet, wie in der folgenden Tabelle dargestellt:

|Typedef|Single-threading|Apartmentthreading für Anwendungen|Freies threading|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel`; M = `CComMultiThreadModel`

Verwendung `CComObjectThreadModel` innerhalb einer einzelnen Objekt-Klasse. Verwendung `CComGlobalsThreadModel` in einem Objekt, mit dem Programm global verfügbar ist oder wenn Sie die Modulressourcen über mehrere Threads hinweg schützen möchten.

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="ccomobjectthreadmodel"></a>  CComObjectThreadModel

Ruft den entsprechenden Thread Objektmodellmethoden, unabhängig davon, das threading-Modell verwendet wird.

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

Je nach den threading-Modell, die von Ihrer Anwendung verwendet die `typedef` Namen `CComObjectThreadModel` verweist entweder auf [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) oder [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md). Diese Klassen bieten zusätzliche `typedef` Namen auf eine kritischen Abschnitt-Klasse verweisen.

> [!NOTE]
> `CComObjectThreadModel` verweist nicht auf Klasse [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).

Mithilfe von `CComObjectThreadModel` erspart Ihnen das Angeben einer bestimmten threading Modellklasse. Unabhängig von der threading-Modell verwendet wird werden die entsprechenden Methoden aufgerufen werden.

Zusätzlich zu `CComObjectThreadModel`, ATL stellt die **Typedef** Namen [CComGlobalsThreadModel](#ccomglobalsthreadmodel). Die Klasse, die auf die verwiesen wird von den einzelnen **Typedef** , hängt das Threadingmodell verwendet, wie in der folgenden Tabelle dargestellt:

|Typedef|Single-threading|Apartmentthreading für Anwendungen|Freies threading|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel`; M = `CComMultiThreadModel`

Verwendung `CComObjectThreadModel` innerhalb einer einzelnen Objekt-Klasse. Verwendung `CComGlobalsThreadModel` in einem Objekt, das entweder global verfügbar, mit dem Programm oder wenn die Modulressourcen über mehrere Threads hinweg geschützt werden sollen.

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="ccontainedwindow"></a>  CContainedWindow

Diese Klasse ist eine Spezialisierung der `CContainedWindowT`.

```
typedef CContainedWindowT<CWindow> CContainedWindow;
```

## <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

### <a name="remarks"></a>Hinweise

`CContainedWindow` ist eine Spezialisierung der [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md). Wenn Sie die Basisklasse oder die "traits" ändern möchten, verwenden Sie `CContainedWindowT` direkt.

##  <a name="cpath"></a>  CPath

Eine Spezialisierung der [CPathT](../../atl/reference/cpatht-class.md) mit `CString`.

```
typedef CPathT<CString> CPath;
```

## <a name="requirements"></a>Anforderungen

**Header:** "atlpath.h"

##  <a name="cpatha"></a>  CPathA

Eine Spezialisierung der [CPathT](../../atl/reference/cpatht-class.md) mit `CStringA`.

```
typedef CPathT<CStringA> CPathA;
```

## <a name="requirements"></a>Anforderungen

**Header:** "atlpath.h"

##  <a name="cpathw"></a>  CPathW

Eine Spezialisierung der [CPathT](../../atl/reference/cpatht-class.md) mit `CStringW`.

```
typedef ATL::CPathT<CStringW> CPathW;
```

## <a name="requirements"></a>Anforderungen

**Header:** "atlpath.h"

##  <a name="csimplevalarray"></a>  CSimpleValArray

Ein Array zum Speichern von einfachen Typen darstellt.

```
#define CSimpleValArray CSimpleArray
```

### <a name="remarks"></a>Hinweise

`CSimpleValArray` Dient zum Erstellen und Verwalten von Arrays mit einfachen Datentypen an. Es ist eine einfache # von define [CSimpleArray](../../atl/reference/csimplearray-class.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlsimpcoll.h

##  <a name="lpcurl"></a>  LPCURL

Ein Zeiger auf eine Konstante [CUrl](../../atl/reference/curl-class.md) Objekt.

```
typedef const CUrl* LPCURL;
```

## <a name="requirements"></a>Anforderungen

**Header:** "atlutil.h"

##  <a name="defaultthreadtraits"></a>  DefaultThreadTraits

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

Wenn das aktuelle Projekt die Multithread-CTR verwendet wird, wird die DefaultThreadTraits als CRTThreadTraits definiert. Andernfalls wird die Win32ThreadTraits verwendet.

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="lpurl"></a>  LPURL

Ein Zeiger auf eine [CUrl](../../atl/reference/curl-class.md) Objekt.

```
typedef CUrl* LPURL;
```

## <a name="requirements"></a>Anforderungen

**Header:** "atlutil.h"

## <a name="see-also"></a>Siehe auch

[ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)<br/>
[Funktionen](../../atl/reference/atl-functions.md)<br/>
[Globale Variablen](../../atl/reference/atl-global-variables.md)<br/>
[Klassen und Strukturen](../../atl/reference/atl-classes.md)<br/>
[Makros](../../atl/reference/atl-macros.md)
