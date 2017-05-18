---
title: CComEnumImpl Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComEnumImpl
- ATLCOM/ATL::CComEnumImpl
- ATLCOM/ATL::CComEnumImpl::CComEnumImpl
- ATLCOM/ATL::CComEnumImpl::Clone
- ATLCOM/ATL::CComEnumImpl::Init
- ATLCOM/ATL::CComEnumImpl::Next
- ATLCOM/ATL::CComEnumImpl::Reset
- ATLCOM/ATL::CComEnumImpl::Skip
- ATLCOM/ATL::CComEnumImpl::m_begin
- ATLCOM/ATL::CComEnumImpl::m_dwFlags
- ATLCOM/ATL::CComEnumImpl::m_end
- ATLCOM/ATL::CComEnumImpl::m_iter
- ATLCOM/ATL::CComEnumImpl::m_spUnk
dev_langs:
- C++
helpviewer_keywords:
- CComEnumImpl class
ms.assetid: cc0d8e76-e608-46db-87cd-4c7161fe32d2
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 6dc6a8ed6a318642efe58dfb94835d45b2163b54
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="ccomenumimpl-class"></a>CComEnumImpl-Klasse
Diese Klasse stellt die Implementierung für eine COM-Enumerator-Schnittstelle, wo die aufzulistenden Elemente in einem Array gespeichert werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Base,
    const IID* piid, class T, class Copy>  
class ATL_NO_VTABLE CComEnumImpl : public Base
```  
  
#### <a name="parameters"></a>Parameter  
 `Base`  
 Eine COM-Enumerator ( [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx)) Schnittstelle.  
  
 `piid`  
 Ein Zeiger auf die Schnittstellen-ID der Enumeratorschnittstelle.  
  
 `T`  
 Der Typ des Elements, die von der Enumeratorschnittstelle verfügbar gemacht werden.  
  
 `Copy`  
 Eine homogene [kopieren Richtlinienklasse](../../atl/atl-copy-policy-classes.md).  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComEnumImpl::CComEnumImpl](#ccomenumimpl)|Der Konstruktor.|  
|[CComEnumImpl:: ~ CComEnumImpl](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComEnumImpl::Clone](#clone)|Die Implementierung der [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx).|  
|[CComEnumImpl::Init](#init)|Initialisiert den Enumerator.|  
|[CComEnumImpl::Next](#next)|Die Implementierung der [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx).|  
|[CComEnumImpl::Reset](#reset)|Die Implementierung der [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx).|  
|[CComEnumImpl:: Skip](#skip)|Die Implementierung der [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx).|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComEnumImpl::m_begin](#m_begin)|Ein Zeiger auf das erste Element im Array.|  
|[CComEnumImpl::m_dwFlags](#m_dwflags)|Kopieren Sie Flags übergeben `Init`.|  
|[CComEnumImpl::m_end](#m_end)|Ein Zeiger auf die Position direkt hinter das letzte Element im Array.|  
|[CComEnumImpl::m_iter](#m_iter)|Ein Zeiger auf das aktuelle Element im Array.|  
|[CComEnumImpl::m_spUnk](#m_spunk)|Die **IUnknown** -Zeiger des Objekts, das die Auflistung bereitstellt.|  
  
## <a name="remarks"></a>Hinweise  
 `CComEnumImpl`Stellt die Implementierung für eine COM-Enumerator-Schnittstelle, wo die aufzulistenden Elemente in einem Array gespeichert werden. Diese Klasse entspricht der `IEnumOnSTLImpl` -Klasse, die eine Implementierung einer Schnittstelle Enumerator bereitstellt, auf Basis einer C++-Standardbibliothek Containers.  
  
> [!NOTE]
>  Weitere Informationen zu weiteren Unterschieden zwischen `CComEnumImpl` und `IEnumOnSTLImpl`, finden Sie unter [CComEnumImpl::Init](#init).  
  
 In der Regel werden Sie *nicht* müssen Ihre eigenen Enumerator-Klasse durch Ableiten von dieser Implementierung zu erstellen. Wenn Sie einen ATL bereitgestellten Enumerator basierend auf einem Array verwenden möchten, es ist üblicher zum Erstellen einer Instanz von [CComEnum](../../atl/reference/ccomenum-class.md).  
  
 Sie müssen einen benutzerdefinierten Enumerator (z. B. eine, die zusätzlich zu der Enumeratorschnittstelle-Schnittstellen bereitstellen) bereitstellen, können Sie von dieser Klasse ableiten. In diesem Fall ist es wahrscheinlich, dass Sie überschreiben müssen die [CComEnumImpl::Clone](#clone) Methode, um Ihre eigene Implementierung bereitzustellen.  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungen und-Enumerationen](../../atl/atl-collections-and-enumerators.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Base`  
  
 `CComEnumImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="ccomenumimpl"></a>CComEnumImpl::CComEnumImpl  
 Der Konstruktor.  
  
```
CComEnumImpl();
```  
  
##  <a name="dtor"></a>CComEnumImpl:: ~ CComEnumImpl  
 Der Destruktor.  
  
```
~CComEnumImpl();
```  
  
##  <a name="init"></a>CComEnumImpl::Init  
 Sie müssen diese Methode aufrufen, bevor Sie einen Zeiger auf die Enumeratorschnittstelle für den zurück auf Clients übergeben.  
  
```
HRESULT Init(
    T* begin,
    T* end,
    IUnknown* pUnk,
    CComEnumFlags flags = AtlFlagNoCopy);
```  
  
### <a name="parameters"></a>Parameter  
 *begin*  
 Ein Zeiger auf das erste Element des Arrays mit den Elementen aufgelistet werden sollen.  
  
 `end`  
 Ein Zeiger auf die Position direkt hinter dem letzten Element des Arrays mit den Elementen aufgelistet werden sollen.  
  
 *pUnk*  
 [in] Die **IUnknown** Zeiger eines Objekts, die während der Lebensdauer des Enumerators beibehalten werden muss. Übergeben Sie **NULL** Wenn kein solches Objekt vorhanden ist.  
  
 `flags`  
 Flags, die angibt, ob der Enumerator des Arrays Besitz oder erstellen Sie eine Kopie davon sollten. Eine Beschreibung der möglichen Werte finden Sie unter.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode nur einmal – den Enumerator zu initialisieren, verwenden Sie diese, und wegwerfen.  
  
 Wenn Sie Zeiger auf Elemente in einem Array in ein anderes Objekt enthaltene übergeben (und Sie nicht den Enumerator zum Kopieren der Daten mehr), können Sie die *pUnk* Parameter, um sicherzustellen, dass das Objekt und das Array, das sie enthält für verfügbar sind, solange der Enumerator benötigt. Der Enumerator enthält einfach einen COM-Verweis auf das Objekt, das beibehalten werden soll. Die COM-Verweis wird automatisch freigegeben, wenn der Enumerator zerstört wird.  
  
 Die `flags` Parameter können Sie angeben, wie der Enumerator die Elemente des Arrays übergeben werden soll. `flags`akzeptiert einen der Werte aus den **CComEnumFlags** Enumeration unten:  
  
```  
enum CComEnumFlags  
   {  
   AtlFlagNoCopy = 0,  
   AtlFlagTakeOwnership = 2, // BitOwn  
   AtlFlagCopy = 3           // BitOwn | BitCopy  
   };  
```  
  
 **AtlFlagNoCopy** bedeutet, dass das Array Lebensdauer nicht vom Enumerator gesteuert wird. In diesem Fall entweder das Array werden statische oder identifizierte Objekt *pUnk* ist zuständig für das Array freigeben, wenn er nicht mehr benötigt wird.  
  
 **AtlFlagTakeOwnership** bedeutet, dass die Zerstörung des Arrays ist vom Enumerator gesteuert werden. In diesem Fall das Array muss dynamisch zugeordnet wurde mit **neue**. Der Enumerator wird das Array in seinem Destruktor gelöscht. Übergeben Sie i. d. r. **NULL** für *pUnk*, obwohl Sie noch einen gültigen Zeiger übergeben können, wenn aus irgendeinem Grund die Zerstörung des Enumerators benachrichtigt werden sollen.  
  
 **AtlFlagCopy** bedeutet, dass ein neues Array erstellt werden, durch Kopieren der übergebenen Arrays auf `Init`. Das neue Array Lebensdauer wird vom Enumerator gesteuert werden. Der Enumerator wird das Array in seinem Destruktor gelöscht. Übergeben Sie i. d. r. **NULL** für *pUnk*, obwohl Sie noch einen gültigen Zeiger übergeben können, wenn aus irgendeinem Grund die Zerstörung des Enumerators benachrichtigt werden sollen.  
  
> [!NOTE]
>  Der Prototyp dieser Methode gibt die Elemente des Arrays als Typ **T**, wobei **T** als einen Vorlagenparameter an die Klasse definiert wurde. Dies ist die desselben Typs, die durch die COM-Schnittstelle-Methode verfügbar gemacht wird [CComEnumImpl::Next](#next). Dies besteht darin, dass im Gegensatz zu [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md), diese Klasse unterstützt keine anderen Speicher und Datentypen verfügbar. Der Datentyp der Elemente im Array muss identisch mit dem Datentyp, der mithilfe der COM-Schnittstelle verfügbar gemacht werden.  
  
##  <a name="clone"></a>CComEnumImpl::Clone  
 Diese Methode stellt die Implementierung der [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx) Methode erstellen Sie ein Objekt vom Typ `CComEnum`, initialisieren es mit dem gleichen Array und Iterator vom aktuellen Objekt verwendet, und die Schnittstelle für das neu erstellte Objekt zurückgibt.  
  
```
STDMETHOD(Clone)(Base** ppEnum);
```  
  
### <a name="parameters"></a>Parameter  
 `ppEnum`  
 [out] Der Enumeratorschnittstelle auf ein neu erstelltes Objekt, das aus dem aktuellen Enumerator geklont werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass die geklonte Enumeratoren nicht ihre eigenen, kopieren (oder Besitz übernehmen) der Daten vom ursprünglichen Enumerator verwendet. Bei Bedarf werden geklonte Enumeratoren den ursprünglichen Enumerator (mithilfe eines COM-Verweis) aufrechtzuerhalten um sicherzustellen, dass die Daten für verfügbar ist, solange sie sie benötigen.  
  
##  <a name="m_spunk"></a>CComEnumImpl::m_spUnk  
 Diese intelligente Zeiger unterhält einen Verweis auf das Objekt übergeben [CComEnumImpl::Init](#init), sicherstellen, dass während der Lebensdauer des Enumerators aktiv bleibt.  
  
```
CComPtr<IUnknown> m_spUnk;
```  
  
##  <a name="m_begin"></a>CComEnumImpl::m_begin  
 Ein Zeiger auf die Position direkt hinter dem letzten Element des Arrays mit den Elementen aufgelistet werden sollen.  
  
```
T* m_begin;
```  
  
##  <a name="m_end"></a>CComEnumImpl::m_end  
 Ein Zeiger auf das erste Element des Arrays mit den Elementen aufgelistet werden sollen.  
  
```
T* m_end;
```  
  
##  <a name="m_iter"></a>CComEnumImpl::m_iter  
 Ein Zeiger auf das aktuelle Element des Arrays mit den Elementen aufgelistet werden sollen.  
  
```
T* m_iter;
```  
  
##  <a name="m_dwflags"></a>CComEnumImpl::m_dwFlags  
 Die Flags übergeben [CComEnumImpl::Init](#init).  
  
```
DWORD m_dwFlags;
```  
  
##  <a name="next"></a>CComEnumImpl::Next  
 Diese Methode stellt die Implementierung der [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) Methode.  
  
```
STDMETHOD(Next)(ULONG celt, T* rgelt, ULONG* pceltFetched);
```  
  
### <a name="parameters"></a>Parameter  
 `celt`  
 [in] Die Anzahl der angeforderten Elemente.  
  
 `rgelt`  
 [out] Das Array mit den Elementen gefüllt werden soll.  
  
 `pceltFetched`  
 [out] Die Anzahl der Elemente, die tatsächlich im zurückgegebenen `rgelt`. Dies kann weniger als `celt` Wenn weniger als `celt` Elemente in der Liste verblieben ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="reset"></a>CComEnumImpl::Reset  
 Diese Methode stellt die Implementierung der [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx) Methode.  
  
```
STDMETHOD(Reset)(void);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="skip"></a>CComEnumImpl:: Skip  
 Diese Methode stellt die Implementierung der [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx) Methode.  
  
```
STDMETHOD(Skip)(ULONG celt);
```  
  
### <a name="parameters"></a>Parameter  
 `celt`  
 [in] Die Anzahl der zu überspringenden Elemente.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Gibt E_INVALIDARG zurück, wenn `celt` NULL ist, gibt S_FALSE zurück, wenn es weniger als `celt` Elemente zurückgegeben werden, andernfalls wird S_OK zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [IEnumOnSTLImpl-Klasse](../../atl/reference/ienumonstlimpl-class.md)   
 [CComEnum-Klasse](../../atl/reference/ccomenum-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

