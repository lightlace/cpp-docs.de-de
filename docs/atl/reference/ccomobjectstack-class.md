---
title: CComObjectStack-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComObjectStack
- ATLCOM/ATL::CComObjectStack
- ATLCOM/ATL::CComObjectStack::CComObjectStack
- ATLCOM/ATL::CComObjectStack::AddRef
- ATLCOM/ATL::CComObjectStack::QueryInterface
- ATLCOM/ATL::CComObjectStack::Release
- ATLCOM/ATL::CComObjectStack::m_hResFinalConstruct
helpviewer_keywords:
- CComObjectStack class
ms.assetid: 3da72c40-c834-45f6-bb76-6ac204028d80
ms.openlocfilehash: 19fd226e617e4cdb1bba8a113b8984c36bf28d59
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287160"
---
# <a name="ccomobjectstack-class"></a>CComObjectStack-Klasse

Diese Klasse erstellt ein temporäre COM-Objekt, und bietet es eine skeletal-Implementierung der `IUnknown`.

## <a name="syntax"></a>Syntax

```
template <class  Base>
class CComObjectStack : public Base
```

#### <a name="parameters"></a>Parameter

*Basis*<br/>
Abgeleitet von die Klasse [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie auch über eine beliebige andere Schnittstelle für das Objekt unterstützt werden sollen.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComObjectStack::CComObjectStack](#ccomobjectstack)|Der Konstruktor.|
|[CComObjectStack::~CComObjectStack](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComObjectStack::AddRef](#addref)|Gibt NULL zurück. Im Debugmodus befindet, ruft `_ASSERTE`.|
|[CComObjectStack::QueryInterface](#queryinterface)|Gibt einen E_NOINTERFACE zurück. Im Debugmodus befindet, ruft `_ASSERTE`.|
|[CComObjectStack::Release](#release)|Gibt NULL zurück. Im Debugmodus befindet, ruft `_ASSERTE`. ~|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComObjectStack::m_hResFinalConstruct](#m_hresfinalconstruct)|Das während der Erstellung der zurückgegebene HRESULT enthält die `CComObjectStack` Objekt.|

## <a name="remarks"></a>Hinweise

`CComObjectStack` wird verwendet, um ein temporäres COM-Objekt erstellt, und geben Sie dem Objekt eine skeletal-Implementierung der `IUnknown`. Das Objekt wird in der Regel als lokale Variable innerhalb einer Funktion verwendet (die auf dem Stapel abgelegt wird). Da das Objekt zerstört wird, wenn die Funktion abgeschlossen ist, zählen der Verweise nicht durchgeführt, um Effizienz zu steigern.

Das folgende Beispiel zeigt, wie zum Erstellen eines COM-Objekts, das innerhalb einer Funktion verwendet wird:

[!code-cpp[NVC_ATL_COM#42](../../atl/codesnippet/cpp/ccomobjectstack-class_1.cpp)]

Das temporäre Objekt `Tempobj` wird auf dem Stapel abgelegt und automatisch ausgeblendet, wenn die Funktion abgeschlossen ist.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`Base`

`CComObjectStack`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="addref"></a>  CComObjectStack::AddRef

Gibt NULL zurück.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Rückgabewert

Gibt NULL zurück.

### <a name="remarks"></a>Hinweise

Im Debugmodus befindet, ruft `_ASSERTE`.

##  <a name="ccomobjectstack"></a>  CComObjectStack::CComObjectStack

Der Konstruktor.

```
CComObjectStack(void* = NULL);
```

### <a name="remarks"></a>Hinweise

Aufrufe `FinalConstruct` und legt dann [M_hResFinalConstruct](#m_hresfinalconstruct) zurückgegebenes HRESULT `FinalConstruct`. Wenn Sie nicht Ihre Basisklasse von abgeleiteten [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md), geben Sie an Ihre eigenen `FinalConstruct` Methode. Der Destruktor ruft `FinalRelease` auf.

##  <a name="dtor"></a>  CComObjectStack:: ~ CComObjectStack

Der Destruktor.

```
CComObjectStack();
```

### <a name="remarks"></a>Hinweise

Gibt Sie frei, alle zugeordneten Ressourcen und ruft [FinalRelease](ccomobjectrootex-class.md#finalrelease).

##  <a name="m_hresfinalconstruct"></a>  CComObjectStack::m_hResFinalConstruct

Vom Aufruf zurückgegebene HRESULT enthält `FinalConstruct` während der Erstellung der `CComObjectStack` Objekt.

```
HRESULT    m_hResFinalConstruct;
```

##  <a name="queryinterface"></a>  CComObjectStack::QueryInterface

Gibt einen E_NOINTERFACE zurück.

```
HRESULT    QueryInterface(REFIID, void**);
```

### <a name="return-value"></a>Rückgabewert

Gibt einen E_NOINTERFACE zurück.

### <a name="remarks"></a>Hinweise

Im Debugmodus befindet, ruft `_ASSERTE`.

##  <a name="release"></a>  CComObjectStack::Release

Gibt NULL zurück.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Rückgabewert

Gibt NULL zurück.

### <a name="remarks"></a>Hinweise

Im Debugmodus befindet, ruft `_ASSERTE`.

## <a name="see-also"></a>Siehe auch

[CComAggObject-Klasse](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject-Klasse](../../atl/reference/ccomobject-class.md)<br/>
[CComObjectGlobal-Klasse](../../atl/reference/ccomobjectglobal-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
