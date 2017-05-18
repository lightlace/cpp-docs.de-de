---
title: Klasse CComTearOffObject | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComTearOffObject
- ATLCOM/ATL::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::AddRef
- ATLCOM/ATL::CComTearOffObject::QueryInterface
- ATLCOM/ATL::CComTearOffObject::Release
- ATLCOM/ATL::CComTearOffObjectBase
- ATLCOM/ATL::m_pOwner
dev_langs:
- C++
helpviewer_keywords:
- tear-off interfaces, ATL
- tear-off interfaces
- CComTearOffObject class
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
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
ms.openlocfilehash: 3e8e997f26df1adca8050bd4d967a38297685831
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="ccomtearoffobject-class"></a>CComTearOffObject-Klasse
Diese Klasse implementiert eine Tearoff Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class Base>
class CComTearOffObject : public Base
```  
  
#### <a name="parameters"></a>Parameter  
 `Base`  
 Die Klasse abtrennbare abgeleitet `CComTearOffObjectBase` und die Schnittstellen, die Ihre abtrennbare Objekt unterstützen soll.  
  
 ATL implementiert seine abtrennbare Schnittstellen in zwei Phasen – der `CComTearOffObjectBase` Methoden behandeln den Verweiszähler und `QueryInterface`, während `CComTearOffObject` implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509).  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComTearOffObject::CComTearOffObject](#ccomtearoffobject)|Der Konstruktor.|  
|[CComTearOffObject:: ~ CComTearOffObject](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComTearOffObject::AddRef](#addref)|Inkrementiert den Verweiszähler für eine `CComTearOffObject` Objekt.|  
|[CComTearOffObject::QueryInterface](#queryinterface)|Gibt einen Zeiger auf die angeforderte Schnittstelle auf Ihre Klasse abtrennbare oder Besitzer-Klasse.|  
|[CComTearOffObject::Release](#release)|Dekrementiert den Verweiszähler für eine `CComTearOffObject` Objekt, und es zerstört.|  
  
### <a name="ccomtearoffobjectbase-methods"></a>CComTearOffObjectBase-Methoden  
  
|||  
|-|-|  
|[CComTearOffObjectBase](#ccomtearoffobjectbase)|Konstruktor.|  
  
### <a name="ccomtearoffobjectbase-data-members"></a>CComTearOffObjectBase-Datenmember  
  
|||  
|-|-|  
|[m_pOwner](#m_powner)|Ein Zeiger auf eine `CComObject` Besitzer-Klasse abgeleitet.|  
  
## <a name="remarks"></a>Hinweise  
 `CComTearOffObject`implementiert eine Tearoff Schnittstelle als separates Objekt, das instanziiert wird, nur, wenn die Schnittstelle abgefragt werden. Die abtrennbare wird gelöscht, wenn der Verweiszähler&0; (null) wird. In der Regel erstellen Sie eine Tearoff Schnittstelle für eine Schnittstelle, die selten verwendet wird, da einen Vtable-Zeiger mit einem abtrennbare in allen Instanzen des Haupt-Objekts gespeichert werden, an.  
  
 Sie müssen die Klasse zur Implementierung der abtrennbare aus ableiten `CComTearOffObjectBase` und unabhängig davon, welche Schnittstellen das abtrennbare Objekt unterstützt werden soll. `CComTearOffObjectBase`ist für die Besitzerklasse und das Threadmodell vorlagenbasiert. Die Besitzerklasse ist die Klasse des Objekts, für die eine abtrennbare implementiert wird. Wenn Sie ein Threadmodell nicht angeben, wird das Standard-Threadmodell verwendet.  
  
 Erstellen Sie eine COM-Zuordnung für die abtrennbare-Klasse. Wenn ATL die abtrennbare instanziiert wird, erstellt es **CComTearOffObject\<CYourTearOffClass >** oder **CComCachedTearOffObject\<CYourTearOffClass >**.  
  
 Im Beispiel BEEPER z. B. die `CBeeper2` -Klasse ist eine Tearoff Klasse und die `CBeeper` -Klasse ist der Besitzer:  
  
 [!code-cpp[NVC_ATL_COM&#43;](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Base`  
  
 `CComTearOffObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="addref"></a>CComTearOffObject::AddRef  
 Inkrementiert den Verweiszähler des dem `CComTearOffObject` von einem Objekt.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise hilfreich für die Diagnose und testen.  
  
##  <a name="ccomtearoffobject"></a>CComTearOffObject::CComTearOffObject  
 Der Konstruktor.  
  
```
CComTearOffObject(void* pv);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 [in] Zeiger, der auf einen Zeiger auf konvertiert werden, wird ein **CComObject\<Besitzer >** Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Besitzer Verweiszähler inkrementiert um eins.  
  
##  <a name="dtor"></a>CComTearOffObject:: ~ CComTearOffObject  
 Der Destruktor.  
  
```
~CComTearOffObject();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordnete Ressourcen frei, ruft FinalRelease und verringert das Modul lock-Anzahl.  
  
##  <a name="ccomtearoffobjectbase"></a>CComTearOffObject::CComTearOffObjectBase  
 Der Konstruktor.  
  
```
CComTearOffObjectBase();
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert die [M_pOwner](#m_powner) Element **NULL**.  
  
##  <a name="m_powner"></a>CComTearOffObject::m_pOwner  
 Ein Zeiger auf eine [CComObject](../../atl/reference/ccomobject-class.md) von abgeleitetes Objekt *Besitzer*.  
  
```
CComObject<Owner>* m_pOwner;
```  
  
### <a name="parameters"></a>Parameter  
 *Besitzer*  
 [in] Die Klasse, für die eine abtrennbare implementiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Der Zeiger wird initialisiert, um **NULL** während der Erstellung.  
  
##  <a name="queryinterface"></a>CComTearOffObject::QueryInterface  
 Ruft einen Zeiger auf die angeforderte Schnittstelle ab.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die IID der angeforderten Schnittstelle.  
  
 `ppvObject`  
 [out] Ein Zeiger auf den Schnittstellenzeiger vom `iid`, oder **NULL** Wenn die Schnittstelle nicht gefunden wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Abfragen für Ihre Klasse abtrennbare Schnittstellen. Wenn die Schnittstelle nicht vorhanden ist, Abfragen für die Schnittstelle in dem Objekt. Wenn die angeforderte Schnittstelle wird **IUnknown**, gibt der **IUnknown** des Besitzers.  
  
##  <a name="release"></a>CComTearOffObject::Release  
 Dekrementiert den Verweiszähler um eins und, wenn der Verweiszähler&0; (null) ist, löscht die `CComTearOffObject`.  
  
```
STDMETHOD_ULONG Release();
```  
  
### <a name="return-value"></a>Rückgabewert  
 In nicht-Debugbuilds gibt immer&0; (null) zurück. In Debugbuilds gibt einen Wert, der möglicherweise hilfreich für die Diagnose oder testen.  
  
## <a name="see-also"></a>Siehe auch  
 [CComCachedTearOffObject-Klasse](../../atl/reference/ccomcachedtearoffobject-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

