---
title: CComObjectStack Klasse | Microsoft Docs
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
ms.openlocfilehash: 8ac37ac5abc193082aaccb8d5de1a4f75f8a3f7c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ccomobjectstack-class"></a>CComObjectStack-Klasse
Diese Klasse wird ein temporäres COM-Objekt erstellt und bietet es eine skeletal Implementierung der **IUnknown**.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class  Base>  
class CComObjectStack
 : public Base
```  
  
#### <a name="parameters"></a>Parameter  
 `Base`  
 Die Klasse abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie gut wie aus einer beliebigen anderen Schnittstelle für das Objekt unterstützt werden sollen.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObjectStack::CComObjectStack](#ccomobjectstack)|Der Konstruktor.|  
|[CComObjectStack:: ~ CComObjectStack](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObjectStack::AddRef](#addref)|Gibt 0 (null). Im Debugmodus befindet, ruft `_ASSERTE`.|  
|[CComObjectStack::QueryInterface](#queryinterface)|Gibt **E_NOINTERFACE**. Im Debugmodus befindet, ruft `_ASSERTE`.|  
|[CComObjectStack::Release](#release)|Gibt 0 (null). Im Debugmodus befindet, ruft `_ASSERTE`. ~|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObjectStack::m_hResFinalConstruct](#m_hresfinalconstruct)|Enthält die **HRESULT** während der Erstellung der zurückgegebenen der `CComObjectStack` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CComObjectStack` Dient zum Erstellen eines temporären COM-Objekts und dem Objekt eine skeletal Implementierung bereitstellen, **IUnknown**. Das Objekt wird in der Regel als lokale Variable innerhalb einer Funktion verwendet (die auf dem Stapel abgelegt wird). Da das Objekt zerstört wird, wenn die Funktion beendet wird, wird verweiszählung nicht ausgeführt, um Effizienz steigern.  
  
 Im folgende Beispiel wird gezeigt, wie zum Erstellen eines COM-Objekts, die innerhalb einer Funktion verwendet wird:  
  
 [!code-cpp[NVC_ATL_COM#42](../../atl/codesnippet/cpp/ccomobjectstack-class_1.cpp)]  
  
 Das temporäre Objekt `Tempobj` wird auf dem Stapel abgelegt und automatisch ausgeblendet, wenn die Funktion beendet.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Base`  
  
 `CComObjectStack`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="addref"></a>  CComObjectStack::AddRef  
 Gibt 0 (null).  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Im Debugmodus befindet, ruft `_ASSERTE`.  
  
##  <a name="ccomobjectstack"></a>  CComObjectStack::CComObjectStack  
 Der Konstruktor.  
  
```
CComObjectStack(void* = NULL);
```  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe `FinalConstruct` und legt dann [M_hResFinalConstruct](#m_hresfinalconstruct) auf die `HRESULT` zurückgegebenes `FinalConstruct`. Wenn Sie nicht die Basisklasse aus abgeleiteten [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md), geben Sie an Ihre eigenen `FinalConstruct` Methode. Der Destruktor ruft `FinalRelease` auf.  
  
##  <a name="dtor"></a>  CComObjectStack:: ~ CComObjectStack  
 Der Destruktor.  
  
```
CComObjectStack();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordneten Ressourcen und ruft [FinalRelease](ccomobjectrootex-class.md#finalrelease).  
  
##  <a name="m_hresfinalconstruct"></a>  CComObjectStack::m_hResFinalConstruct  
 Enthält die `HRESULT` vom Aufruf zurückgegebene `FinalConstruct` während der Erstellung der `CComObjectStack` Objekt.  
  
```
HRESULT    m_hResFinalConstruct;
```  
  
##  <a name="queryinterface"></a>  CComObjectStack::QueryInterface  
 Gibt **E_NOINTERFACE**.  
  
```
HRESULT    QueryInterface(REFIID, void**)
 ;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOINTERFACE**.  
  
### <a name="remarks"></a>Hinweise  
 Im Debugmodus befindet, ruft `_ASSERTE`.  
  
##  <a name="release"></a>  CComObjectStack::Release  
 Gibt 0 (null).  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Im Debugmodus befindet, ruft `_ASSERTE`.  
  
## <a name="see-also"></a>Siehe auch  
 [CComAggObject-Klasse](../../atl/reference/ccomaggobject-class.md)   
 [CComObject-Klasse](../../atl/reference/ccomobject-class.md)   
 [CComObjectGlobal-Klasse](../../atl/reference/ccomobjectglobal-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
