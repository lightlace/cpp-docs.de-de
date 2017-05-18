---
title: Klasse CComObjectStack | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 19
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 0738eae13fdca5906596194016ce22812fbfcd36
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobjectstack-class"></a>CComObjectStack-Klasse
Diese Klasse erstellt ein temporäre COM-Objekt und bietet es eine skeletal-Implementierung von **IUnknown**.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class  Base>  
class CComObjectStack
 : public Base
```  
  
#### <a name="parameters"></a>Parameter  
 `Base`  
 Die Klasse abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie auch über eine beliebige andere Schnittstelle für das Objekt unterstützt werden sollen.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObjectStack::CComObjectStack](#ccomobjectstack)|Der Konstruktor.|  
|[CComObjectStack:: ~ CComObjectStack](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObjectStack::AddRef](#addref)|Gibt&0; (null) zurück. Ruft den Debugmodus `_ASSERTE`.|  
|[CComObjectStack::QueryInterface](#queryinterface)|Gibt **E_NOINTERFACE**. Ruft den Debugmodus `_ASSERTE`.|  
|[CComObjectStack::Release](#release)|Gibt&0; (null) zurück. Ruft den Debugmodus `_ASSERTE`. ~|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObjectStack::m_hResFinalConstruct](#m_hresfinalconstruct)|Enthält die **HRESULT** während der Erstellung der zurückgegebenen der `CComObjectStack` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CComObjectStack`wird verwendet, um ein temporäres COM-Objekt erstellt, und geben Sie dem Objekt eine skeletal-Implementierung von **IUnknown**. In der Regel wird das Objekt als lokale Variable innerhalb einer Funktion verwendet werden (die auf dem Stapel abgelegt wird). Da das Objekt zerstört wird, wenn die Funktion beendet, Referenzzähler nicht ausgeführt, um Effizienz zu steigern.  
  
 Das folgende Beispiel zeigt, wie zum Erstellen eines COM-Objekts innerhalb einer Funktion verwendet wird:  
  
 [!code-cpp[NVC_ATL_COM&#42;](../../atl/codesnippet/cpp/ccomobjectstack-class_1.cpp)]  
  
 Das temporäre Objekt `Tempobj` wird auf dem Stapel abgelegt, und automatisch ausgeblendet, wenn die Funktion beendet.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Base`  
  
 `CComObjectStack`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="addref"></a>CComObjectStack::AddRef  
 Gibt&0; (null) zurück.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt&0; (null) zurück.  
  
### <a name="remarks"></a>Hinweise  
 Ruft den Debugmodus `_ASSERTE`.  
  
##  <a name="ccomobjectstack"></a>CComObjectStack::CComObjectStack  
 Der Konstruktor.  
  
```
CComObjectStack(void* = NULL);
```  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe `FinalConstruct` und legt dann [M_hResFinalConstruct](#m_hresfinalconstruct) an der `HRESULT` zurückgegebene `FinalConstruct`. Wenn Sie nicht die Basisklasse abgeleitet haben [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md), Sie müssen angeben, eigene `FinalConstruct` Methode. Der Destruktor ruft `FinalRelease` auf.  
  
##  <a name="dtor"></a>CComObjectStack:: ~ CComObjectStack  
 Der Destruktor.  
  
```
CComObjectStack();
```  
  
### <a name="remarks"></a>Hinweise  
 Alle zugeordneten Ressourcen und ruft frei [FinalRelease](ccomobjectrootex-class.md#finalrelease).  
  
##  <a name="m_hresfinalconstruct"></a>CComObjectStack::m_hResFinalConstruct  
 Enthält die `HRESULT` vom Aufruf zurückgegebenen `FinalConstruct` während der Erstellung eines der `CComObjectStack` Objekt.  
  
```
HRESULT    m_hResFinalConstruct;
```  
  
##  <a name="queryinterface"></a>CComObjectStack::QueryInterface  
 Gibt **E_NOINTERFACE**.  
  
```
HRESULT    QueryInterface(REFIID, void**)
 ;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOINTERFACE**.  
  
### <a name="remarks"></a>Hinweise  
 Ruft den Debugmodus `_ASSERTE`.  
  
##  <a name="release"></a>CComObjectStack::Release  
 Gibt&0; (null) zurück.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt&0; (null) zurück.  
  
### <a name="remarks"></a>Hinweise  
 Ruft den Debugmodus `_ASSERTE`.  
  
## <a name="see-also"></a>Siehe auch  
 [CComAggObject-Klasse](../../atl/reference/ccomaggobject-class.md)   
 [CComObject-Klasse](../../atl/reference/ccomobject-class.md)   
 [CComObjectGlobal-Klasse](../../atl/reference/ccomobjectglobal-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

