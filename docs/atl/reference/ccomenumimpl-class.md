---
title: CComEnumImpl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords: CComEnumImpl class
ms.assetid: cc0d8e76-e608-46db-87cd-4c7161fe32d2
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7cda4598f5d5b0e5b3dbca265066c8366cfd6d67
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccomenumimpl-class"></a>CComEnumImpl-Klasse
Diese Klasse stellt die Implementierung für eine COM-Enumerator-Schnittstelle, in dem die Elemente, die aufgezählt werden in einem Array gespeichert werden.  
  
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
  
## <a name="members"></a>Member  
  
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
|[CComEnumImpl::m_end](#m_end)|Ein Zeiger auf die Position direkt hinter dem letzten Element im Array.|  
|[CComEnumImpl::m_iter](#m_iter)|Ein Zeiger auf das aktuelle Element im Array.|  
|[CComEnumImpl::m_spUnk](#m_spunk)|Die **IUnknown** Zeiger, der das Objekt, das Angeben der Auflistung aufgezählt werden.|  
  
## <a name="remarks"></a>Hinweise  
 `CComEnumImpl`Stellt die Implementierung für eine COM-Enumerator-Schnittstelle, in dem die Elemente, die aufgezählt werden in einem Array gespeichert werden. Diese Klasse ist analog zu den `IEnumOnSTLImpl` -Klasse, die eine Implementierung einer Schnittstelle Enumerator bereitstellt, basierend auf einen Container für die C++-Standardbibliothek.  
  
> [!NOTE]
>  Weitere Informationen zu weiteren Unterschieden zwischen `CComEnumImpl` und `IEnumOnSTLImpl`, finden Sie unter [CComEnumImpl::Init](#init).  
  
 Sehen Sie in der Regel *nicht* müssen eigene Enumeratorklasse durch Ableiten von dieser Implementierung zu erstellen. Wenn Sie einen ATL bereitgestellte basierten auf ein Array-Enumerator verwenden möchten, ist eher üblich, dass das Erstellen einer Instanz des [CComEnum](../../atl/reference/ccomenum-class.md).  
  
 Sie benötigen, geben Sie einen benutzerdefinierten Enumerator (z. B. eine, die Schnittstellen, die zusätzlich zu den Enumeratorschnittstelle verfügbar macht), können Sie von dieser Klasse ableiten. In diesem Fall ist es wahrscheinlich, dass Sie außer Kraft setzen müssen die [CComEnumImpl::Clone](#clone) Methode, um Ihre eigene Implementierung bereitzustellen.  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungen und-Enumerationen](../../atl/atl-collections-and-enumerators.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Base`  
  
 `CComEnumImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
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
 Sie müssen diese Methode aufrufen, bevor die Übergabe eines Zeigers auf die Enumeratorschnittstelle an alle Clients.  
  
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
 [in] Die **IUnknown** Zeiger eines Objekts, das während der Lebensdauer des Enumerators beibehalten werden muss. Übergeben Sie **NULL** Wenn kein solches Objekt vorhanden ist.  
  
 `flags`  
 Flags, die angibt, ob der Enumerator des Arrays Inbesitznahme sollte, oder erstellen Sie eine Kopie des Zertifikats. Mögliche Werte sind unten beschrieben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode nur einmal – Initialisieren des Enumerators, verwenden Sie es, und wirft den Zettel unterwegs.  
  
 Wenn Sie Elemente in einem Array in ein anderes Objekt gespeicherten Zeiger übergeben (und nicht, Sie den Enumerator bitten auf die Daten zu kopieren), können Sie mithilfe der *pUnk* Parameter, um sicherzustellen, dass das Objekt und das Array er enthält so lange als den Enumerator verfügbar sind benötigt. Der Enumerator ist einfach einen COM-Verweis auf das Objekt, das am Leben zu erhalten. Der COM-Verweis wird automatisch freigegeben, wenn der Enumerator zerstört wird.  
  
 Die `flags` Parameter können Sie angeben, wie der Enumerator die Array-Elemente, die an sie übergebenen behandeln soll. `flags`akzeptiert einen der Werte aus den **CComEnumFlags** Enumeration unten angezeigt:  
  
```  
enum CComEnumFlags  
   {  
   AtlFlagNoCopy = 0,  
   AtlFlagTakeOwnership = 2, // BitOwn  
   AtlFlagCopy = 3           // BitOwn | BitCopy  
   };  
```  
  
 **AtlFlagNoCopy** bedeutet, dass die Lebensdauer des Arrays nicht vom Enumerator gesteuert wird. In diesem Fall wird entweder das Array werden statische oder das identifizierte Objekt *pUnk* ist zuständig für das Array freigeben, wenn er nicht mehr benötigt wird.  
  
 **AtlFlagTakeOwnership** darauf hin, dass die Zerstörung des Arrays vom Enumerator gesteuert werden. In diesem Fall das Array muss zugeordnet worden sein dynamisch mit **neue**. Der Enumerator löscht das Array in seinem Destruktor. Übergeben Sie in der Regel **NULL** für *pUnk*, obwohl Sie immer noch einen gültigen Zeiger übergeben können, wenn Sie aus irgendeinem Grund die Zerstörung des Enumerators benachrichtigt werden müssen.  
  
 **AtlFlagCopy** darauf hin, dass ein neues Array erstellt werden, durch Kopieren der übergebenen Arrays auf `Init`. Lebensdauer für das neue Array wird vom Enumerator gesteuert werden. Der Enumerator löscht das Array in seinem Destruktor. Übergeben Sie in der Regel **NULL** für *pUnk*, obwohl Sie immer noch einen gültigen Zeiger übergeben können, wenn Sie aus irgendeinem Grund die Zerstörung des Enumerators benachrichtigt werden müssen.  
  
> [!NOTE]
>  Der Prototyp dieser Methode gibt die Elemente des Arrays als Typ **T**, wobei **T** als Vorlagenparameter für die Klasse definiert wurde. Dies ist der gleichen Typ, der über die Schnittstellenmethode COM verfügbar gemacht wird [CComEnumImpl::Next](#next). Die Implikation hiervon ist, dass im Gegensatz zu [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md), diese Klasse unterstützt keine anderen Speicher und verfügbar gemacht werden Datentypen. Der Datentyp der Elemente im Array muss identisch mit dem Datentyp, der mittels der COM-Schnittstelle verfügbar gemacht werden.  
  
##  <a name="clone"></a>CComEnumImpl::Clone  
 Diese Methode stellt die Implementierung des der [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx) Methode durch das Erstellen eines Objekts vom Typ `CComEnum`, initialisieren es mit dem gleichen Array und Iterator vom aktuellen Objekt verwendet, und Zurückgeben der Benutzeroberfläche für die neu erstellte Objekt.  
  
```
STDMETHOD(Clone)(Base** ppEnum);
```  
  
### <a name="parameters"></a>Parameter  
 `ppEnum`  
 [out] Der Enumeratorschnittstelle in einem neu erstellten Objekt aus dem aktuellen Enumerator geklont werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass die geklonte Enumeratoren eigene nehmen Sie niemals kopieren (oder Take Ownership) der Daten vom ursprünglichen Enumerator verwendet. Bei Bedarf werden geklonte Enumeratoren den ursprünglichen Enumerator (mit einem COM-Verweis) aufrechtzuerhalten um sicherzustellen, dass die Daten für verfügbar sind, wie sie ihn benötigen.  
  
##  <a name="m_spunk"></a>CComEnumImpl::m_spUnk  
 Diese intelligente Zeiger behält einen Verweis auf das übergebene Objekt [CComEnumImpl::Init](#init), um sicherzustellen, dass es während der Lebensdauer des Enumerators aktiv bleibt.  
  
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
 Die Flags an übergeben [CComEnumImpl::Init](#init).  
  
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
 [out] Die Anzahl der Elemente, die tatsächlich im zurückgegebenen `rgelt`. Dies kann weniger als `celt` Wenn weniger als `celt` Elemente in der Liste verblieben sind.  
  
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
 Gibt E_INVALIDARG zurück, wenn `celt` 0 (null) ist, gibt "S_FALSE" zurück, wenn weniger als `celt` Elemente zurückgegeben werden, andernfalls gibt S_OK zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [IEnumOnSTLImpl-Klasse](../../atl/reference/ienumonstlimpl-class.md)   
 [CComEnum-Klasse](../../atl/reference/ccomenum-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
