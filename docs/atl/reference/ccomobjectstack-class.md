---
title: CComObjectStack-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObjectStack
- ATLCOM/ATL::CComObjectStack
- ATLCOM/ATL::CComObjectStack::CComObjectStack
- ATLCOM/ATL::CComObjectStack::AddRef
- ATLCOM/ATL::CComObjectStack::QueryInterface
- ATLCOM/ATL::CComObjectStack::Release
- ATLCOM/ATL::CComObjectStack::m_hResFinalConstruct
dev_langs:
- C++
helpviewer_keywords:
- CComObjectStack class
ms.assetid: 3da72c40-c834-45f6-bb76-6ac204028d80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3abbd69a69205b0dd7f4ee9fb43d5889e2824552
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882717"
---
# <a name="ccomobjectstack-class"></a>CComObjectStack-Klasse
Diese Klasse erstellt ein temporäre COM-Objekt, und bietet es eine skeletal-Implementierung der `IUnknown`.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class  Base>  
class CComObjectStack
 : public Base
```  
  
#### <a name="parameters"></a>Parameter  
 *Basis*  
 Abgeleitet von die Klasse [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie auch über eine beliebige andere Schnittstelle für das Objekt unterstützt werden sollen.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObjectStack::CComObjectStack](#ccomobjectstack)|Der Konstruktor.|  
|[CComObjectStack:: ~ CComObjectStack](#dtor)|Der Destruktor.|  
  
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
HRESULT    QueryInterface(REFIID, void**)
 ;
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
 [CComAggObject-Klasse](../../atl/reference/ccomaggobject-class.md)   
 [CComObject-Klasse](../../atl/reference/ccomobject-class.md)   
 [CComObjectGlobal-Klasse](../../atl/reference/ccomobjectglobal-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
