---
title: CAccessorBase-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CAccessorBase
- CAccessorBase.Close
- CAccessorBase::Close
- GetHAccessor
- CAccessorBase::GetHAccessor
- CAccessorBase.GetHAccessor
- CAccessorBase::GetNumAccessors
- GetNumAccessors
- CAccessorBase.GetNumAccessors
- IsAutoAccessor
- CAccessorBase.IsAutoAccessor
- CAccessorBase::IsAutoAccessor
- CAccessorBase::ReleaseAccessors
- CAccessorBase.ReleaseAccessors
- ReleaseAccessors
dev_langs:
- C++
helpviewer_keywords:
- CAccessorBase class
- Close method
- GetHAccessor method
- GetNumAccessors method
- IsAutoAccessor method
- ReleaseAccessors method
ms.assetid: 389b65be-11ca-4ae0-9290-60c621c4982b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2e62c4242513c5147dcfd84ee5d69ec51a4816d1
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50053330"
---
# <a name="caccessorbase-class"></a>CAccessorBase-Klasse

Alle Accessoren in OLE DB-Vorlagen, die von dieser Klasse abgeleitet werden. `CAccessorBase` können ein Rowset, um mehrere Accessoren zu verwalten. Darüber hinaus Bindung für Parameter und Ausgabespalten.

## <a name="syntax"></a>Syntax

```cpp
// Replace with syntax
```

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[Schließen](#close)|Schließt die Accessoren.|
|[GetHAccessor](#geth)|Ruft das Accessorhandle ab.|
|[GetNumAccessors](#getnum)|Ruft die Anzahl der Accessoren, die von der Klasse erstellt.|
|[IsAutoAccessor](#isauto)|Testet, ob der angegebene Accessor einen Autoaccessor ist.|
|[ReleaseAccessors](#release)|Gibt die Accessoren frei.|

## <a name="requirements"></a>Anforderungen

**Header:** atldbcli.h

## <a name="close"></a> CAccessorBase:: Close

Schließt die Accessoren.

### <a name="syntax"></a>Syntax

```cpp
void Close();
```

### <a name="remarks"></a>Hinweise

Rufen Sie [ReleaseAccessors](../../data/oledb/caccessorbase-releaseaccessors.md) erste.

## <a name="geth"></a> CAccessorBase:: Gethaccessor

Ruft den Accessorhandle für einen angegebenen Accessor ab.

### <a name="syntax"></a>Syntax

```cpp
HACCESSOR GetHAccessor(ULONG nAccessor) const;
```

#### <a name="parameters"></a>Parameter

*nAccessor*<br/>
[in] Die Anzahl der NULL-Offset für die Zugriffsmethode.

### <a name="return-value"></a>Rückgabewert

Das Accessorhandle.

## <a name="getnum"></a> CAccessorBase:: Getnumaccessors

Ruft die Anzahl der Accessoren, die von der Klasse erstellt.

### <a name="syntax"></a>Syntax

```cpp
ULONG GetNumAccessors() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Accessoren, die von der Klasse erstellt.

## <a name="isauto"></a> CAccessorBase:: Isautoaccessor

Gibt "true" zurück, wenn die Daten automatisch für den Accessor während eines Verschiebevorgangs abgerufen werden.

### <a name="syntax"></a>Syntax

```cpp
bool IsAutoAccessor(ULONG nAccessor) const;
```

#### <a name="parameters"></a>Parameter

*nAccessor*<br/>
[in] Die Anzahl der NULL-Offset für die Zugriffsmethode.

### <a name="return-value"></a>Rückgabewert

Gibt **"true"** Wenn der Accessor einen Autoaccessor ist. Andernfalls wird **false**zurückgegeben.

## <a name="release"></a> CAccessorBase:: Releaseaccessors

Gibt die Accessoren, die von der Klasse erstellt.

### <a name="syntax"></a>Syntax

```cpp
HRESULT ReleaseAccessors(IUnknown* pUnk);
```

#### <a name="parameters"></a>Parameter

*pUnk*<br/>
[in] Ein Zeiger auf ein `IUnknown` Schnittstelle für das COM-Objekt, das für die die Accessoren erstellt wurden.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

### <a name="remarks"></a>Hinweise

Aufgerufen von [CAccessorRowset:: Close](../../data/oledb/caccessorrowset-close.md).

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessorBase-Klasse](../../data/oledb/caccessorbase-class.md)