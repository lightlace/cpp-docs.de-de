---
title: CComTearOffObject Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- tear-off interfaces, ATL
- tear-off interfaces
- CComTearOffObject class
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c4f6782e2e873e844fa1d2eb7a9c1090d887dac9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ccomtearoffobject-class"></a>CComTearOffObject-Klasse
Diese Klasse implementiert eine Schnittstelle abtrennbare.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class Base>
class CComTearOffObject : public Base
```  
  
#### <a name="parameters"></a>Parameter  
 `Base`  
 Abgeleitet von die Klasse abtrennbare `CComTearOffObjectBase` und die Schnittstellen, die Ihre abtrennbare Objekt unterstützen soll.  
  
 ATL implementiert die abtrennbare Schnittstellen in zwei Phasen – die `CComTearOffObjectBase` Methoden behandeln den Verweiszähler und `QueryInterface`, während `CComTearOffObject` implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509).  
  
## <a name="members"></a>Member  
  
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
 `CComTearOffObject`implementiert eine Schnittstelle abtrennbare als separates Objekt, das instanziiert wird, nur, wenn für diese Schnittstelle abgefragt wird. Die abtrennbare wird gelöscht, wenn der Verweiszähler auf 0 (null) wird. In der Regel erstellen Sie eine Schnittstelle abtrennbare für eine Schnittstelle, die nur selten verwendet wird, da einen Vtable Zeiger mit einem abtrennbare in allen Instanzen von Ihrem Hauptobjekt speichert,.  
  
 Sollten Sie die Klasse zur Implementierung der abtrennbare aus ableiten `CComTearOffObjectBase` und unabhängig davon, welche Schnittstellen die abtrennbare Objekt unterstützt werden sollen. `CComTearOffObjectBase`ist für den Besitzerklasse und das Threadmodell vorlagenbasiert. Die Besitzerklasse ist die Klasse des Objekts, für die eine abtrennbare implementiert wird. Wenn Sie ein Threadmodell nicht angeben, wird das Standardmodell des Threads verwendet.  
  
 Erstellen Sie eine COM-Zuordnung für die abtrennbare-Klasse. Wenn ATL die abtrennbare instanziiert, erstellt jedoch **CComTearOffObject\<CYourTearOffClass >** oder **CComCachedTearOffObject\<CYourTearOffClass >**.  
  
 Im Beispiel BEEPER z. B. die `CBeeper2` abtrennbare-Klasse und die `CBeeper` -Klasse ist der Besitzer:  
  
 [!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Base`  
  
 `CComTearOffObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="addref"></a>CComTearOffObject::AddRef  
 Inkrementiert den Verweiszähler des dem `CComTearOffObject` von einem Objekt.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise nützlich für die Diagnose und testen.  
  
##  <a name="ccomtearoffobject"></a>CComTearOffObject::CComTearOffObject  
 Der Konstruktor.  
  
```
CComTearOffObject(void* pv);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 [in] Zeiger, der in einen Zeiger auf konvertiert wird eine **CComObject\<Besitzer >** Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Besitzer Verweiszähler inkrementiert um eins.  
  
##  <a name="dtor"></a>CComTearOffObject:: ~ CComTearOffObject  
 Der Destruktor.  
  
```
~CComTearOffObject();
```  
  
### <a name="remarks"></a>Hinweise  
 Alle zugeordnete Ressourcen freigegeben werden, werden Aufrufe von FinalRelease und verringert das Modul Anzahl zu sperren.  
  
##  <a name="ccomtearoffobjectbase"></a>CComTearOffObject::CComTearOffObjectBase  
 Der Konstruktor.  
  
```
CComTearOffObjectBase();
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert die [M_pOwner](#m_powner) Element **NULL**.  
  
##  <a name="m_powner"></a>CComTearOffObject::m_pOwner  
 Ein Zeiger auf eine [CComObject](../../atl/reference/ccomobject-class.md) abgeleitetes Objekt aus *Besitzer*.  
  
```
CComObject<Owner>* m_pOwner;
```  
  
### <a name="parameters"></a>Parameter  
 *Besitzer*  
 [in] Die Klasse, für die eine abtrennbare implementiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Der Zeiger wird mit initialisiert **NULL** während der Erstellung.  
  
##  <a name="queryinterface"></a>CComTearOffObject::QueryInterface  
 Ruft einen Zeiger auf die angeforderte Schnittstelle ab.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die IID der Schnittstelle angefordert wird.  
  
 `ppvObject`  
 [out] Ein Zeiger auf den Schnittstellenzeiger, der durch `iid`, oder **NULL** , wenn die Schnittstelle nicht gefunden wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Fragt zuerst nach für Ihre Klasse abtrennbare Schnittstellen ab. Wenn die Schnittstelle nicht vorhanden ist, Abfragen für die Schnittstelle für das Besitzerobjekt ist. Wenn die angeforderte Schnittstelle wird **IUnknown**, gibt die **IUnknown** des Besitzers.  
  
##  <a name="release"></a>CComTearOffObject::Release  
 Dekrementiert den Verweiszähler um eins und, wenn der Verweiszähler auf 0 (null) ist, löscht die `CComTearOffObject`.  
  
```
STDMETHOD_ULONG Release();
```  
  
### <a name="return-value"></a>Rückgabewert  
 In nicht-Debugbuilds gibt immer 0 (null) zurück. Debug-Builds gibt einen Wert an, der möglicherweise bei der Diagnose hilfreich oder testen.  
  
## <a name="see-also"></a>Siehe auch  
 [CComCachedTearOffObject-Klasse](../../atl/reference/ccomcachedtearoffobject-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
