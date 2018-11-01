---
title: CEnumeratorAccessor-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CEnumeratorAccessor
- CEnumeratorAccessor
- ATL.CEnumeratorAccessor
- CEnumeratorAccessor.m_bIsParent
- ATL::CEnumeratorAccessor::m_bIsParent
- m_bIsParent
- ATL.CEnumeratorAccessor.m_bIsParent
- CEnumeratorAccessor::m_bIsParent
- ATL::CEnumeratorAccessor::m_nType
- CEnumeratorAccessor.m_nType
- CEnumeratorAccessor::m_nType
- ATL.CEnumeratorAccessor.m_nType
- m_nType
- ATL::CEnumeratorAccessor::m_szDescription
- CEnumeratorAccessor.m_szDescription
- CEnumeratorAccessor::m_szDescription
- ATL.CEnumeratorAccessor.m_szDescription
- CEnumeratorAccessor::m_szName
- ATL.CEnumeratorAccessor.m_szName
- m_szName
- ATL::CEnumeratorAccessor::m_szName
- CEnumeratorAccessor.m_szName
- CEnumeratorAccessor::m_szParseName
- ATL::CEnumeratorAccessor::m_szParseName
- m_szParseName
- CEnumeratorAccessor.m_szParseName
- ATL.CEnumeratorAccessor.m_szParseName
dev_langs:
- C++
helpviewer_keywords:
- CEnumeratorAccessor class
- m_bIsParent
- m_nType
- m_szDescription
- m_szName
- m_szParseName
ms.assetid: 21e8e7ea-3511-4afe-b33f-d520f4ff82bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 616d2cc9919c992212024d25ab11902ffe2eda5e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50072147"
---
# <a name="cenumeratoraccessor-class"></a>CEnumeratorAccessor-Klasse

Ein, die [CEnumerator](../../data/oledb/cenumerator-class.md) Zugriff auf die Daten aus dem Enumerator-Rowset.

## <a name="syntax"></a>Syntax

```cpp
class CEnumeratorAccessor
```

## <a name="requirements"></a>Anforderungen

**Header:** atldbcli.h

## <a name="members"></a>Member

### <a name="data-members"></a>Datenmember

|||
|-|-|
|[m_bIsParent](#bisparent)|Eine Variable, der angibt, ob der Enumerator einen übergeordneten-Enumerator ist die Zeile ist ein Enumerator.|
|[m_nType](#ntype)|Eine Variable, der angibt, ob die Zeile eine Datenquelle oder einen Enumerator beschreibt.|
|[m_szDescription](#szdescription)|Die Beschreibung der Datenquelle oder Enumerator.|
|[m_szName](#szname)|Der Name der Datenquelle oder Enumerator.|
|[m_szParseName](#szparsename)|Zeichenfolge zu übergeben [IParseDisplayName](/windows/desktop/api/oleidl/nn-oleidl-iparsedisplayname) einen Moniker für die Datenquelle oder einen Enumerator abrufen.|

## <a name="remarks"></a>Hinweise

Dieses Rowset besteht aus den Datenquellen und Enumeratoren, die der aktuelle Enumerator sichtbar.

## <a name="bisparent"></a> Cenumeratoraccessor:: M_bisparent

Eine Variable, der angibt, ob der Enumerator einen übergeordneten-Enumerator ist die Zeile ist ein Enumerator.

### <a name="syntax"></a>Syntax

```cpp
VARIANT_BOOL m_bIsParent;
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200) in die *OLE DB-Programmierreferenz* für Weitere Informationen.

## <a name="ntype"></a> Cenumeratoraccessor:: M_ntype

Eine Variable, der angibt, ob die Zeile eine Datenquelle oder einen Enumerator beschreibt.

### <a name="syntax"></a>Syntax

```cpp
USHORT m_nType;
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200) in die *OLE DB-Programmierreferenz* für Weitere Informationen.

## <a name="szdescription"></a> Cenumeratoraccessor:: M_szdescription

Die Beschreibung der Datenquelle oder Enumerator.

### <a name="syntax"></a>Syntax

```cpp
WCHAR m_szDescription[129];
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200) in die *OLE DB-Programmierreferenz* für Weitere Informationen.

## <a name="szname"></a> Cenumeratoraccessor:: M_szname

Der Name der Datenquelle oder Enumerator.

### <a name="syntax"></a>Syntax

```cpp
WCHAR m_szName[129];
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200) in die *OLE DB-Programmierreferenz* für Weitere Informationen.

## <a name="szparsename"></a> Cenumeratoraccessor:: M_szparsename

Zeichenfolge zu übergeben [IParseDisplayName](/windows/desktop/api/oleidl/nn-oleidl-iparsedisplayname) einen Moniker für die Datenquelle oder einen Enumerator abrufen.

### <a name="syntax"></a>Syntax

```cpp
WCHAR m_szParseName[129];
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200) in die *OLE DB-Programmierreferenz* für Weitere Informationen.

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)