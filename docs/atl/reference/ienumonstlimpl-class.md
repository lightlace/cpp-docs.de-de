---
title: IEnumOnSTLImpl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords: IEnumOnSTLImpl class
ms.assetid: 1789e77b-88b8-447d-a490-806b918912ce
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 50cb78893eeca685f0b538fad397aca445502776
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ienumonstlimpl-class"></a>IEnumOnSTLImpl-Klasse
Diese Klasse definiert eine Enumeratorschnittstelle, die auf Grundlage einer C++-Standardbibliothek-Auflistung.  
  
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
  
## <a name="members"></a>Member  
  
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
|[IEnumOnSTLImpl::m_pcollection](#m_pcollection)|Ein Zeiger auf die C++-Standardbibliothek Container enthalten die Elemente aufgelistet werden sollen.|  
|[IEnumOnSTLImpl::m_spUnk](#m_spunk)|Die **IUnknown** Zeiger, der das Objekt die Auflistung bereitstellen.|  
  
## <a name="remarks"></a>Hinweise  
 `IEnumOnSTLImpl`Stellt die Implementierung für eine COM-Enumerator-Schnittstelle, in dem die Elemente, die aufgezählt werden in einem C++-Standard-Bibliothek-kompatiblen Container gespeichert werden. Diese Klasse ist analog zu den [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md) Klasse, die eine Implementierung für eine Enumeratorschnittstelle bereitstellt, basierend auf einem Array.  
  
> [!NOTE]
>  Finden Sie unter [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init) Weitere Informationen zu weiteren Unterschieden zwischen `CComEnumImpl` und `IEnumOnSTLImpl`.  
  
 Sehen Sie in der Regel *nicht* müssen eigene Enumeratorklasse durch Ableiten von dieser Implementierung zu erstellen. Wenn Sie einen ATL bereitgestellte Enumerator basierend auf einem C++-Standardbibliothek Container verwenden möchten, ist eher üblich, dass das Erstellen einer Instanz des [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md), oder erstellen eine Auflistungsklasse, die einen Enumerator durch Ableiten von zurückgibt[ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md).  
  
 Sie benötigen, geben Sie einen benutzerdefinierten Enumerator (z. B. eine, die Schnittstellen, die zusätzlich zu den Enumeratorschnittstelle verfügbar macht), können Sie von dieser Klasse ableiten. In diesem Fall ist es wahrscheinlich, dass Sie außer Kraft setzen müssen die [Klon](#clone) Methode, um Ihre eigene Implementierung bereitzustellen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Base`  
  
 `IEnumOnSTLImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="init"></a>IEnumOnSTLImpl::Init  
 Initialisiert den Enumerator.  
  
```
HRESULT Init(
    IUnknown* pUnkForRelease,
    CollType& collection);
```  
  
### <a name="parameters"></a>Parameter  
 `pUnkForRelease`  
 [in] Die **IUnknown** Zeiger eines Objekts, das während der Lebensdauer des Enumerators beibehalten werden muss. Übergeben Sie **NULL** Wenn kein solches Objekt vorhanden ist.  
  
 `collection`  
 Ein Verweis auf den C++-Standardbibliothek Container, die Elemente aufgelistet werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie übergeben `Init` ein Verweis auf eine Auflistung in ein anderes Objekt gespeicherten können Sie die `pUnkForRelease` Parameter, um sicherzustellen, dass das Objekt, und der Auflistung, die es enthält, ist für verfügbar, solange der Enumerator notwendig.  
  
 Sie müssen diese Methode aufrufen, bevor die Übergabe eines Zeigers auf die Enumeratorschnittstelle an alle Clients.  
  
##  <a name="clone"></a>IEnumOnSTLImpl::Clone  
 Diese Methode stellt die Implementierung des der [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx) Methode durch das Erstellen eines Objekts vom Typ `CComEnumOnSTL`, initialisieren es mit dem gleichen Auflistung und Iterator vom aktuellen Objekt verwendet, und Zurückgeben der Benutzeroberfläche für das neu erstellte Objekt.  
  
```
STDMETHOD(Clone)(Base** ppEnum);
```  
  
### <a name="parameters"></a>Parameter  
 `ppEnum`  
 [out] Der Enumeratorschnittstelle in einem neu erstellten Objekt aus dem aktuellen Enumerator geklont werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="m_spunk"></a>IEnumOnSTLImpl::m_spUnk  
 Die **IUnknown** Zeiger, der das Objekt die Auflistung bereitstellen.  
  
```
CComPtr<IUnknown> m_spUnk;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese intelligente Zeiger behält einen Verweis auf das übergebene Objekt [IEnumOnSTLImpl::Init](#init), um sicherzustellen, dass es während der Lebensdauer des Enumerators aktiv bleibt.  
  
##  <a name="m_pcollection"></a>IEnumOnSTLImpl::m_pcollection  
 Bei diesem Member verweist auf die Auflistung, die die Daten, die die Implementierung der Enumeratorschnittstelle driving bereitstellt.  
  
```
CollType* m_pcollection;
```  
  
### <a name="remarks"></a>Hinweise  
 Bei diesem Member wird durch einen Aufruf von initialisiert [IEnumOnSTLImpl::Init](#init).  
  
##  <a name="m_iter"></a>IEnumOnSTLImpl::m_iter  
 Bei diesem Member enthält den Iterator zum Markieren der aktuellen Position innerhalb der Auflistung, und navigieren zu nachfolgenden Elemente.  
  
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
 [out] Das Array mit den Elementen gefüllt werden soll.  
  
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
 [Klassenübersicht](../../atl/atl-class-overview.md)
