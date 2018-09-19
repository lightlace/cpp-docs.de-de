---
title: IDBInitializeImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IDBInitializeImpl<T>
- ATL::IDBInitializeImpl<T>
- IDBInitializeImpl
- ATL::IDBInitializeImpl
- ATL.IDBInitializeImpl
- IDBInitializeImpl.IDBInitializeImpl
- IDBInitializeImpl
- IDBInitializeImpl::IDBInitializeImpl
- Initialize
- IDBInitializeImpl::Initialize
- IDBInitializeImpl.Initialize
- IDBInitializeImpl.Uninitialize
- Uninitialize
- IDBInitializeImpl::Uninitialize
- ATL::IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl.m_dwStatus
- ATL.IDBInitializeImpl.m_dwStatus
- IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl<T>::m_dwStatus
- ATL.IDBInitializeImpl<T>.m_dwStatus
- ATL::IDBInitializeImpl<T>::m_dwStatus
- m_dwStatus
- ATL::IDBInitializeImpl<T>::m_pCUtlPropInfo
- m_pCUtlPropInfo
- IDBInitializeImpl::m_pCUtlPropInfo
- ATL.IDBInitializeImpl.m_pCUtlPropInfo
- IDBInitializeImpl<T>::m_pCUtlPropInfo
- IDBInitializeImpl.m_pCUtlPropInfo
- ATL::IDBInitializeImpl::m_pCUtlPropInfo
dev_langs:
- C++
helpviewer_keywords:
- IDBInitializeImpl class
- IDBInitializeImpl constructor
- Initialize method
- Uninitialize method
- m_dwStatus
- m_pCUtlPropInfo
ms.assetid: e4182f81-0443-44f5-a0d3-e7e075d6f883
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4f44d43d48f862ca2ca5465d5ea9ee44d0e9040e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072419"
---
# <a name="idbinitializeimpl-class"></a>IDBInitializeImpl-Klasse

Stellt eine Implementierung für die [IDBInitialize](/previous-versions/windows/desktop/ms713706\(v=vs.85\)) Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T>  
class ATL_NO_VTABLE IDBInitializeImpl : public IDBInitialize  
```  
  
### <a name="parameters"></a>Parameter  

*T*<br/>
Abgeleitet von die Klasse `IDBInitializeImpl`.  

## <a name="requirements"></a>Anforderungen  

**Header:** „atldb.h“  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[IDBInitializeImpl](#idbinitializeimpl)|Der Konstruktor.|  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[Initialize](#initialize)|Startet den Anbieter.|  
|[Die Initialisierung aufheben](#uninitialize)|Beendet den Anbieter an.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_dwStatus](#dwstatus)|Datenquellen-Flags.|  
|[m_pCUtlPropInfo](#pcutlpropinfo)|Ein Zeiger auf die Implementierung der DB-Eigenschaften-Informationen.|  
  
## <a name="remarks"></a>Hinweise  

Eine erforderliche Schnittstelle für Datenquellenobjekte und optionale Schnittstelle für Enumeratoren.  

## <a name="idbinitializeimpl"></a> Idbinitializeimpl:: Idbinitializeimpl

Der Konstruktor.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
IDBInitializeImpl();  
```  
  
### <a name="remarks"></a>Hinweise  

Initialisiert alle Datenmember. 
  
## <a name="initialize"></a> Idbinitializeimpl:: Initialize

Initialisiert das Objekt durch die Unterstützung für die Eigenschaft wird vorbereitet.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
STDMETHOD(Initialize)(void);  
```  
  
### <a name="remarks"></a>Hinweise  

Finden Sie unter [IDBInitialize:: Initialize](/previous-versions/windows/desktop/ms718026\(v=vs.85\)) in die *OLE DB-Programmierreferenz*. 

## <a name="uninitialize"></a> Idbinitializeimpl:: UnInitialize

Stellen Sie die Daten Datenquellenobjekts im nicht initialisierten Zustand freigegeben werden und interne Ressourcen wie z. B. die Unterstützung für die Eigenschaft ein.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
STDMETHOD(Uninitialize)(void);  
```  
  
### <a name="remarks"></a>Hinweise  

Finden Sie unter [IDBInitialize:: UnInitialize](/previous-versions/windows/desktop/ms719648\(v=vs.85\)) in die *OLE DB-Programmierreferenz*.

## <a name="dwstatus"></a> Idbinitializeimpl:: M_dwstatus

Datenquellen-Flags.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
DWORD m_dwStatus;  
```  
  
### <a name="remarks"></a>Hinweise  

Diese Flags geben, oder geben Sie den Status der verschiedenen Attribute für das Datenquellenobjekt. Enthält eine oder mehrere der folgenden **Enum** Werte:  
  
```cpp  
enum DATASOURCE_FLAGS {  
    DSF_MASK_INIT     = 0xFFFFF00F,  
    DSF_PERSIST_DIRTY = 0x00000001,  
    DSF_INITIALIZED   = 0x00000010,  
};  
```  
  
|||  
|-|-|  
|`DSF_MASK_INIT`|Eine Maske, die Wiederherstellung von nicht initialisierten Zustand zu aktivieren.|  
|`DSF_PERSIST_DIRTY`|Festlegen Sie, wenn das Datenquellenobjekt Persistenz ist erforderlich (d.h., wenn Änderungen vorgenommen wurden).|  
|`DSF_INITIALIZED`|Festlegen Sie, wenn die Datenquelle initialisiert wurde.|  

## <a name="pcutlpropinfo"></a> Idbinitializeimpl:: M_pcutlpropinfo

Ein Zeiger auf Objekt implementace Datenbankeigenschaften Informationen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
CUtlPropInfo< T >* m_pCUtlPropInfo;  
```  
  
## <a name="see-also"></a>Siehe auch  

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)