---
title: CDBPropIDSet-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDBPropIDSet
- ATL.CDBPropIDSet
- ATL::CDBPropIDSet
- CDBPropIDSet.AddPropertyID
- CDBPropIDSet::AddPropertyID
- AddPropertyID
- ATL.CDBPropIDSet.AddPropertyID
- ATL::CDBPropIDSet::AddPropertyID
- ATL::CDBPropIDSet::CDBPropIDSet
- CDBPropIDSet
- CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet::CDBPropIDSet
- ATL.CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet.operator=
- ATL.CDBPropIDSet.operator=
- ATL::CDBPropIDSet::operator=
- CDBPropIDSet::operator=
- CDBPropIDSet.SetGUID
- ATL::CDBPropIDSet::SetGUID
- SetGUID
- ATL.CDBPropIDSet.SetGUID
- CDBPropIDSet::SetGUID
helpviewer_keywords:
- CDBPropIDSet class
- AddPropertyID method
- CDBPropIDSet class, constructor
- operator =, property sets
- = operator, with OLE DB templates
- operator=, property sets
- SetGUID method
ms.assetid: 52bb806c-9581-494d-9af7-50d8a4834805
ms.openlocfilehash: 9e878af3acf4c4d3a6ca785454c4bb072f17cf09
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59022410"
---
# <a name="cdbpropidset-class"></a>CDBPropIDSet-Klasse

Erbt von der `DBPROPIDSET` -Struktur und fügt einen Konstruktor, der wichtige Felder initialisiert sowie die [AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md) -Zugriffsmethode.

## <a name="syntax"></a>Syntax

```cpp
class CDBPropIDSet : public tagDBPROPIDSET
```

## <a name="requirements"></a>Anforderungen

**Header:** atldbcli.h

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[AddPropertyID](#addpropertyid)|Fügt eine Eigenschaft auf den ID-Eigenschaftensatz an.|
|[CDBPropIDSet](#cdbpropidset)|Konstruktor.|
|[SetGUID](#setguid)|Legt fest, die GUID der Eigenschafts-ID wird.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator =](#op_equal)|Weist legen Sie den Inhalt von einer Eigenschafts-ID in eine andere.|

## <a name="remarks"></a>Hinweise

Verwenden der OLE DB-Consumer `DBPROPIDSET` Strukturen, um ein Array von Eigenschaften-IDs übergeben, für die der Consumer die Eigenschaftsinformationen abrufen möchte. In einem einzelnen angegebenen Eigenschaften [DBPROPIDSET](/previous-versions/windows/desktop/ms717981(v=vs.85)) Struktur zu einem Eigenschaftensatz gehören.

## <a name="addpropertyid"></a> CDBPropIDSet::AddPropertyID

Eine Eigenschafts-ID und der ID-Eigenschaftensatz hinzugefügt.

### <a name="syntax"></a>Syntax

```cpp
bool AddPropertyID(DBPROPID propid) throw();
```

#### <a name="parameters"></a>Parameter

*propid*<br/>
[in] Legen Sie die Eigenschafts-ID der Eigenschafts-ID hinzugefügt werden.

## <a name="cdbpropidset"></a> CDBPropIDSet::CDBPropIDSet

Der Konstruktor. Initialisiert die `rgProperties`, `cProperties`, und (optional) `guidPropertySet` Felder der [DBPROPIDSET](/previous-versions/windows/desktop/ms717981(v=vs.85)) Struktur.

### <a name="syntax"></a>Syntax

```cpp
CDBPropIDSet(const GUID& guid);

CDBPropIDSet(const CDBPropIDSet& propidset);

CDBPropIDSet();
```

#### <a name="parameters"></a>Parameter

*guid*<br/>
[in] Eine GUID, die zum Initialisieren der `guidPropertySet` Feld.

*propidset*<br/>
[in] Eine andere `CDBPropIDSet` Objekt für die Copy-Konstruktion.

## <a name="setguid"></a> CDBPropIDSet::SetGUID

Legt das Feld "GUID" der `DBPROPIDSET` Struktur.

### <a name="syntax"></a>Syntax

```cpp
void SetGUID(const GUID& guid) throw();
```

#### <a name="parameters"></a>Parameter

*guid*<br/>
[in] Eine GUID zum Festlegen der `guidPropertySet` Feld der [DBPROPIDSET](/previous-versions/windows/desktop/ms717981(v=vs.85)) Struktur.

### <a name="remarks"></a>Hinweise

Dieses Feld kann festgelegt werden, indem die [Konstruktor](../../data/oledb/cdbpropidset-cdbpropidset.md) ebenfalls. Rufen Sie diese Funktion, wenn Sie den Standardkonstruktor für diese Klasse verwenden.

## <a name="op_equal"></a> Cdbpropidset:: Operator =

Weist den Inhalt von einer Eigenschafts-ID, die auf einen anderen Satz von ID-Eigenschaft festgelegt.

### <a name="syntax"></a>Syntax

```cpp
CDBPropIDSet& operator =(CDBPropIDSet& propset) throw();
```

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)