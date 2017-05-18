---
title: Klasse IEnumOnSTLImpl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl::Clone
- ATLCOM/ATL::IEnumOnSTLImpl::Init
- ATLCOM/ATL::IEnumOnSTLImpl::Next
- ATLCOM/ATL::IEnumOnSTLImpl::Reset
- ATLCOM/ATL::IEnumOnSTLImpl::Skip
- ATLCOM/ATL::IEnumOnSTLImpl::m_iter
- ATLCOM/ATL::IEnumOnSTLImpl::m_pcollection
- ATLCOM/ATL::IEnumOnSTLImpl::m_spUnk
dev_langs:
- C++
helpviewer_keywords:
- IEnumOnSTLImpl class
ms.assetid: 1789e77b-88b8-447d-a490-806b918912ce
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 291993d2914d6082b69bfe7816d7c805e93494c4
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="ienumonstlimpl-class"></a>IEnumOnSTLImpl-Klasse
Diese Klasse definiert eine Enumeratorschnittstelle auf Grundlage einer C++-Standardbibliothek-Auflistung.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Base,
    const IID* piid, class T, class Copy, class CollType>  
class ATL_NO_VTABLE IEnumOnSTLImpl : public Base
```  
  
#### <a name="parameters"></a>Parameter  
 `Base`  
 Eine COM-Enumerator ( [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx)) Schnittstelle.  
  
 `piid`  
 Ein Zeiger auf die Schnittstellen-ID der Enumeratorschnittstelle.  
  
 `T`  
 Der Typ des Elements, die von der Enumeratorschnittstelle verfügbar gemacht werden.  
  
 `Copy`  
 Ein [kopieren Richtlinienklasse](../../atl/atl-copy-policy-classes.md).  
  
 `CollType`  
 Eine C++-Standardbibliothek Container-Klasse.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IEnumOnSTLImpl::Clone](#clone)|Die Implementierung der [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx).|  
|[IEnumOnSTLImpl::Init](#init)|Initialisiert den Enumerator.|  
|[IEnumOnSTLImpl::Next](#next)|Die Implementierung der [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx).|  
|[IEnumOnSTLImpl::Reset](#reset)|Die Implementierung der [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx).|  
|[IEnumOnSTLImpl::Skip](#skip)|Die Implementierung der [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx).|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IEnumOnSTLImpl::m_iter](#m_iter)|Der Iterator, der aktuellen Position des Enumerators, in der Auflistung darstellt.|  
|[IEnumOnSTLImpl::m_pcollection](#m_pcollection)|Ein Zeiger auf die C++-Standardbibliothek Containers, der die Elemente aufgelistet werden sollen.|  
|[IEnumOnSTLImpl::m_spUnk](#m_spunk)|Die **IUnknown** -Zeiger des Objekts, das die Auflistung bereitstellen.|  
  
## <a name="remarks"></a>Hinweise  
 `IEnumOnSTLImpl`Stellt die Implementierung für eine COM-Enumerator-Schnittstelle, in dem die aufzulistenden Elemente in einem C++-Standard-Bibliothek-kompatiblen Container gespeichert sind. Diese Klasse entspricht dem [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md) -Klasse, die eine Implementierung für eine Enumeratorschnittstelle bereitstellt, basierend auf einem Array.  
  
> [!NOTE]
>  Finden Sie unter [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init) ausführliche Informationen über weitere Unterschiede zwischen `CComEnumImpl` und `IEnumOnSTLImpl`.  
  
 In der Regel werden Sie *nicht* müssen Ihre eigenen Enumerator-Klasse durch Ableiten von dieser Implementierung zu erstellen. Wenn Sie einen ATL bereitgestellten Enumerator basierend auf einen Container für die C++-Standardbibliothek verwenden möchten, es ist üblicher zum Erstellen einer Instanz von [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md), oder erstellen eine Auflistungsklasse, die einen Enumerator zurückgibt, durch Ableiten von [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md).  
  
 Sie müssen einen benutzerdefinierten Enumerator (z. B. eine, die zusätzlich zu der Enumeratorschnittstelle-Schnittstellen bereitstellen) bereitstellen, können Sie von dieser Klasse ableiten. In diesem Fall ist es unwahrscheinlich, dass Sie überschreiben müssen die [Klon](#clone) Methode, um Ihre eigene Implementierung bereitzustellen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Base`  
  
 `IEnumOnSTLImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="init"></a>IEnumOnSTLImpl::Init  
 Initialisiert den Enumerator.  
  
```
HRESULT Init(
    IUnknown* pUnkForRelease,
    CollType& collection);
```  
  
### <a name="parameters"></a>Parameter  
 `pUnkForRelease`  
 [in] Die **IUnknown** Zeiger eines Objekts, die während der Lebensdauer des Enumerators beibehalten werden muss. Übergeben Sie **NULL** Wenn kein solches Objekt vorhanden ist.  
  
 `collection`  
 Ein Verweis auf den C++-Standardbibliothek Container, die Elemente aufgelistet werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie übergeben `Init` frei, die ein Verweis auf eine Auflistung in einem anderen Objekt können Sie die `pUnkForRelease` Parameter, um sicherzustellen, dass das Objekt, und die Auflistung, die er hält, für verfügbar ist, solange der Enumerator benötigt.  
  
 Sie müssen diese Methode aufrufen, bevor Sie einen Zeiger auf die Enumeratorschnittstelle für den zurück auf Clients übergeben.  
  
##  <a name="clone"></a>IEnumOnSTLImpl::Clone  
 Diese Methode stellt die Implementierung der [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx) Methode erstellen Sie ein Objekt vom Typ `CComEnumOnSTL`, initialisieren mit der gleichen Auflistung und Iterator vom aktuellen Objekt verwendet, und die Schnittstelle für das neu erstellte Objekt zurückgibt.  
  
```
STDMETHOD(Clone)(Base** ppEnum);
```  
  
### <a name="parameters"></a>Parameter  
 `ppEnum`  
 [out] Der Enumeratorschnittstelle auf ein neu erstelltes Objekt, das aus dem aktuellen Enumerator geklont werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="m_spunk"></a>IEnumOnSTLImpl::m_spUnk  
 Die **IUnknown** -Zeiger des Objekts, das die Auflistung bereitstellen.  
  
```
CComPtr<IUnknown> m_spUnk;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese intelligente Zeiger unterhält einen Verweis auf das Objekt übergeben [IEnumOnSTLImpl::Init](#init), sicherstellen, dass während der Lebensdauer des Enumerators aktiv bleibt.  
  
##  <a name="m_pcollection"></a>IEnumOnSTLImpl::m_pcollection  
 Bei diesem Member verweist auf die Auflistung, über die Daten, die die Implementierung der Enumeratorschnittstelle gesteuert.  
  
```
CollType* m_pcollection;
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Member wird initialisiert, indem ein Aufruf von [IEnumOnSTLImpl::Init](#init).  
  
##  <a name="m_iter"></a>IEnumOnSTLImpl::m_iter  
 Dieser Member enthält, den Iterator, der die aktuelle Position innerhalb der Auflistung zu markieren, und wechseln zu nachfolgenden Elemente verwendet wird.  
  
```
CollType::iterator m_iter;
```  
  
##  <a name="next"></a>IEnumOnSTLImpl::Next  
 Diese Methode stellt die Implementierung der [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) Methode.  
  
```
STDMETHOD(Next)(
    ULONG celt,
    T* rgelt,
    ULONG* pceltFetched);
```  
  
### <a name="parameters"></a>Parameter  
 `celt`  
 [in] Die Anzahl der angeforderten Elemente.  
  
 `rgelt`  
 [out] Das Array, das die Elemente eingetragen werden.  
  
 `pceltFetched`  
 [out] Die Anzahl der Elemente, die tatsächlich im zurückgegebenen `rgelt`. Dies kann weniger als `celt` Wenn weniger als `celt` Elemente bleiben in der Liste.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="reset"></a>IEnumOnSTLImpl::Reset  
 Diese Methode stellt die Implementierung der [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx) Methode.  
  
```
STDMETHOD(Reset)(void);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="skip"></a>IEnumOnSTLImpl::Skip  
 Diese Methode stellt die Implementierung der [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx) Methode.  
  
```
STDMETHOD(Skip)(ULONG celt);
```  
  
### <a name="parameters"></a>Parameter  
 `celt`  
 [in] Die Anzahl der zu überspringenden Elemente.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

