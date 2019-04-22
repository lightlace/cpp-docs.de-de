---
title: ICommandImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- ICommandImpl
- ICommandImpl::Cancel
- Cancel
- ICommandImpl.Cancel
- ICommandImpl::CancelExecution
- ATL::ICommandImpl::CancelExecution
- ATL.ICommandImpl.CancelExecution
- CancelExecution
- ICommandImpl.CancelExecution
- ICommandImpl::CreateRowset
- ICommandImpl.CreateRowset
- CreateRowset
- ICommandImpl::Execute
- ICommandImpl.Execute
- ICommandImpl::GetDBSession
- GetDBSession
- ICommandImpl.GetDBSession
- ATL.ICommandImpl.ICommandImpl
- ATL::ICommandImpl::ICommandImpl
- ICommandImpl
- ICommandImpl::ICommandImpl
- ICommandImpl.ICommandImpl
- ICommandImpl::m_bCancel
- ICommandImpl.m_bCancel
- m_bCancel
- ATL::ICommandImpl::m_bCancel
- ATL.ICommandImpl.m_bCancel
- ICommandImpl::m_bCancelWhenExecuting
- ICommandImpl.m_bCancelWhenExecuting
- ATL::ICommandImpl::m_bCancelWhenExecuting
- m_bCancelWhenExecuting
- ATL.ICommandImpl.m_bCancelWhenExecuting
- ICommandImpl.m_bIsExecuting
- ATL::ICommandImpl::m_bIsExecuting
- m_bIsExecuting
- ATL.ICommandImpl.m_bIsExecuting
- ICommandImpl::m_bIsExecuting
helpviewer_keywords:
- ICommandImpl class
- Cancel method
- CancelExecution method
- CreateRowset method
- Execute method
- GetDBSession method
- ICommandImpl constructor
- ICommandImpl class, constructor
- m_bCancel
- m_bCancelWhenExecuting
- m_bIsExecuting
ms.assetid: ef285fef-0d66-45e6-a762-b03357098e3b
ms.openlocfilehash: d890b62e4e4aabb9f8ca7ebb9d3051c53febd91f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026791"
---
# <a name="icommandimpl-class"></a>ICommandImpl-Klasse

Stellt die Implementierung für die [ICommand](/previous-versions/windows/desktop/ms709737(v=vs.85)) Schnittstelle.

## <a name="syntax"></a>Syntax

```cpp
template <class T, class CommandBase = ICommand>
class ATL_NO_VTABLE ICommandImpl : public CommandBase
```

### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `ICommandImpl`.

*CommandBase*<br/>
Eine Befehlsschnittstelle. Die Standardeinstellung ist `ICommand`.

## <a name="requirements"></a>Anforderungen

**Header:** „atldb.h“

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[Kündigung](#cancel)|Bricht die Ausführung des aktuellen Befehls ab.|
|[CancelExecution](#cancelexecution)|Bricht die Ausführung des aktuellen Befehls ab.|
|[CreateRowset](#createrowset)|Erstellt ein Rowsetobjekt.|
|[Execute](#execute)|Führt den Befehl.|
|[GetDBSession](#getdbsession)|Gibt einen Schnittstellenzeiger zurück, mit der Sitzung, die den Befehl erstellt haben.|
|[ICommandImpl](#icommandimpl)|Der Konstruktor.|

### <a name="data-members"></a>Datenmember

|||
|-|-|
|[m_bCancel](#bcancel)|Gibt an, ob der Befehl abgebrochen werden.|
|[m_bCancelWhenExecuting](#bcancelwhenexecuting)|Gibt an, ob der Befehl ist für die Ausführung abgebrochen werden soll.|
|[m_bIsExecuting](#bisexecuting)|Gibt an, ob der Befehl derzeit ausgeführt wird.|

## <a name="remarks"></a>Hinweise

Eine erforderliche Schnittstelle für das Command-Objekt.

## <a name="cancel"></a> ICommandImpl::Cancel

Bricht die Ausführung des aktuellen Befehls ab.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(Cancel)();
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [ICommand::Cancel](/previous-versions/windows/desktop/ms714402(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="cancelexecution"></a> ICommandImpl::CancelExecution

Bricht die Ausführung des aktuellen Befehls ab.

### <a name="syntax"></a>Syntax

```cpp
HRESULT CancelExecution();
```

## <a name="createrowset"></a> ICommandImpl::CreateRowset

Wird aufgerufen, indem [Execute](../../data/oledb/icommandimpl-execute.md) um ein einzelnes Rowset zu erstellen.

### <a name="syntax"></a>Syntax

```cpp
template template <class RowsetClass>
HRESULT CreateRowset(IUnknown* pUnkOuter,
   REFIID riid,
   DBPARAMS* pParams,
   DBROWCOUNT* pcRowsAffected,
   IUnknown** ppRowset,
   RowsetClass*& pRowsetObj);
```

#### <a name="parameters"></a>Parameter

*RowsetClass*<br/>
Ein Member von Vorlage-Klasse, die Rowset-Klasse für den Benutzer darstellt. In der Regel vom Assistenten generiert.

*pUnkOuter*<br/>
[in] Ein Zeiger auf das steuernde `IUnknown` Schnittstelle, wenn das Rowset als Teil eines Aggregats erstellt wird; andernfalls ist der Wert null.

*riid*<br/>
[in] Entspricht *Riid* in `ICommand::Execute`.

*pParams*<br/>
[in/Out] Entspricht *pParams* in `ICommand::Execute`.

*pcRowsAffected*<br/>
Entspricht *PcRowsAffected* in `ICommand::Execute`.

*ppRowset*<br/>
[in/Out] Entspricht *PpRowset* in `ICommand::Execute`.

*pRowsetObj*<br/>
[out] Ein Zeiger auf eine Rowset-Objekt. Dieser Parameter wird in der Regel nicht verwendet, aber es kann verwendet werden, wenn Sie mehr Arbeit für das Rowset ausführen müssen, vor der Übergabe an ein COM-Objekt. Die Lebensdauer des *pRowsetObj* gebunden ist, indem *PpRowset*.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert. Finden Sie unter `ICommand::Execute` eine Liste mit typischen Werten.

### <a name="remarks"></a>Hinweise

Um mehr als ein Rowset zu erstellen, oder geben Sie Ihren eigenen Bedingungen für das Erstellen von anderen Rowsets, platzieren Sie die verschiedenen Aufrufe zum `CreateRowset` aus `Execute`.

Finden Sie unter [ICommand:: Execute](/previous-versions/windows/desktop/ms718095(v=vs.85)) in die *OLE DB-Programmierreferenz.*

## <a name="execute"></a> ICommandImpl::Execute

Führt den Befehl.

### <a name="syntax"></a>Syntax

```cpp
HRESULT Execute(IUnknown* pUnkOuter,
   REFIID riid,
   DBPARAMS* pParams,
   DBROWCOUNT* pcRowsAffected,
   IUnknown** ppRowset);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [ICommand:: Execute](/previous-versions/windows/desktop/ms718095(v=vs.85)) in die *OLE DB-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Die Ausgangsschnittstelle angefordert werden, dass eine Schnittstelle, die abgerufen werden, aus dem Rowsetobjekt, das diese Funktion erstellt.

`Execute` Aufrufe [CreateRowset](../../data/oledb/icommandimpl-createrowset.md). Überschreiben Sie die standardmäßige Implementierung mehr als ein Rowset zu erstellen, oder geben Sie Ihren eigenen Bedingungen für das Erstellen von anderen Rowsets.

## <a name="getdbsession"></a> ICommandImpl::GetDBSession

Gibt einen Schnittstellenzeiger zurück, mit der Sitzung, die den Befehl erstellt haben.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD (GetDBSession) (REFIID riid,
   IUnknown** ppSession);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [ICommand::GetDBSession](/previous-versions/windows/desktop/ms719622(v=vs.85)) in die *OLE DB-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Nützlich zum Abrufen von Eigenschaften aus der Sitzung.

## <a name="icommandimpl"></a> ICommandImpl::ICommandImpl

Der Konstruktor.

### <a name="syntax"></a>Syntax

```cpp
ICommandImpl();
```

## <a name="bcancel"></a> ICommandImpl::m_bCancel

Gibt an, ob der Befehl abgebrochen wird.

### <a name="syntax"></a>Syntax

```cpp
unsigned m_bCancel:1;
```

### <a name="remarks"></a>Hinweise

Sie können diese Variable im Abrufen der `Execute` Methode Ihrer Klasse des Befehls und "Abbrechen", nach Bedarf.

## <a name="bcancelwhenexecuting"></a> ICommandImpl::m_bCancelWhenExecuting

Gibt an, ob der Befehl für die Ausführung abgebrochen werden kann.

### <a name="syntax"></a>Syntax

```cpp
unsigned m_bCancelWhenExecuting:1;
```

### <a name="remarks"></a>Hinweise

Standardmäßig **"true"** (kann abgebrochen werden kann).

## <a name="bisexecuting"></a> ICommandImpl::m_bIsExecuting

Gibt an, ob der Befehl derzeit ausgeführt wird.

### <a name="syntax"></a>Syntax

```cpp
unsigned m_bIsExecuting:1;
```

### <a name="remarks"></a>Hinweise

Die `Execute` -Methode der Ihre Befehlsklasse kann diese Variable festlegen, um **"true"**.

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)