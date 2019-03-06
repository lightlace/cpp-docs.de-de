---
title: IDBInitializeImpl-Klasse
ms.date: 11/04/2016
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
helpviewer_keywords:
- IDBInitializeImpl class
- IDBInitializeImpl constructor
- Initialize method
- Uninitialize method
- m_dwStatus
- m_pCUtlPropInfo
ms.assetid: e4182f81-0443-44f5-a0d3-e7e075d6f883
ms.openlocfilehash: 18145f3dc9545f79b08d9d92cacdafad0520c992
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57418741"
---
# <a name="idbinitializeimpl-class"></a>IDBInitializeImpl-Klasse

Stellt eine Implementierung für die [IDBInitialize](/previous-versions/windows/desktop/ms713706(v=vs.85)) Schnittstelle.

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

## <a name="idbinitializeimpl"></a> IDBInitializeImpl::IDBInitializeImpl

Der Konstruktor.

### <a name="syntax"></a>Syntax

```cpp
IDBInitializeImpl();
```

### <a name="remarks"></a>Hinweise

Initialisiert alle Datenmember.

## <a name="initialize"></a> IDBInitializeImpl::Initialize

Initialisiert das Objekt durch die Unterstützung für die Eigenschaft wird vorbereitet.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(Initialize)(void);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IDBInitialize:: Initialize](/previous-versions/windows/desktop/ms718026(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="uninitialize"></a> IDBInitializeImpl::Uninitialize

Stellen Sie die Daten Datenquellenobjekts im nicht initialisierten Zustand freigegeben werden und interne Ressourcen wie z. B. die Unterstützung für die Eigenschaft ein.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(Uninitialize)(void);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IDBInitialize:: UnInitialize](/previous-versions/windows/desktop/ms719648(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="dwstatus"></a> IDBInitializeImpl::m_dwStatus

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

## <a name="pcutlpropinfo"></a> IDBInitializeImpl::m_pCUtlPropInfo

Ein Zeiger auf Objekt implementace Datenbankeigenschaften Informationen.

### <a name="syntax"></a>Syntax

```cpp
CUtlPropInfo< T >* m_pCUtlPropInfo;
```

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)