---
title: CDBPropSet-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDBPropSet
- ATL.CDBPropSet
- ATL::CDBPropSet
- CDBPropSet::AddProperty
- CDBPropSet.AddProperty
- AddProperty
- ATL::CDBPropSet::AddProperty
- ATL.CDBPropSet.AddProperty
- CDBPropSet.CDBPropSet
- CDBPropSet::CDBPropSet
- ATL::CDBPropSet::CDBPropSet
- ATL.CDBPropSet.CDBPropSet
- CDBPropSet.operator=
- ATL::CDBPropSet::operator=
- ATL.CDBPropSet.operator=
- CDBPropSet::operator=
- ATL.CDBPropSet.SetGUID
- CDBPropSet.SetGUID
- ATL::CDBPropSet::SetGUID
- SetGUID
- CDBPropSet::SetGUID
helpviewer_keywords:
- CDBPropSet class
- AddProperty method
- CDBPropSet class, constructor
- operator =, property sets
- = operator, with OLE DB templates
- operator=, property sets
- SetGUID method
- AddProperty method
ms.assetid: 54190149-c277-4679-b81a-ef484d4d1c00
ms.openlocfilehash: b58c0262d361ede37bc3db68784177ec4c29f3a4
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59034237"
---
# <a name="cdbpropset-class"></a>CDBPropSet-Klasse

Erbt von der `DBPROPSET` -Struktur und fügt einen Konstruktor, der wichtige Felder initialisiert sowie die `AddProperty` -Zugriffsmethode.

## <a name="syntax"></a>Syntax

```cpp
class CDBPropSet : public tagDBPROPSET
```

## <a name="requirements"></a>Anforderungen

**Header:** atldbcli.h

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[AddProperty](#addproperty)|Fügt eine Eigenschaft, der die Eigenschaft festgelegt.|
|[CDBPropSet](#cdbpropset)|Konstruktor.|
|[SetGUID](#setguid)|Legt die `guidPropertySet` Feld der `DBPROPSET` Struktur.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator =](#op_equal)|Weist den Inhalt einer Eigenschaft in ein anderes festlegen.|

## <a name="remarks"></a>Hinweise

OLE DB-Anbieter und Consumer verwenden `DBPROPSET` Strukturen zum Übergeben von Arrays von `DBPROP` Strukturen. Jede `DBPROP` Struktur stellt eine einzelne Eigenschaft, die festgelegt werden kann.

## <a name="addproperty"></a> CDBPropSet::AddProperty

Fügt eine Eigenschaft, der die Eigenschaft festgelegt.

### <a name="syntax"></a>Syntax

```cpp
bool AddProperty(DWORD dwPropertyID,
   constVARIANT& var,
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   LPCSTR szValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   LPCWSTR szValue,DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   bool bValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   BYTE bValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   short nValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   long nValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   float fltValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   double dblValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   CY cyValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();
```

#### <a name="parameters"></a>Parameter

*dwPropertyID*<br/>
[in] Die ID der Eigenschaft hinzugefügt werden. Zum Initialisieren der `dwPropertyID` von der `DBPROP` Struktur hinzugefügt, der die Eigenschaft festgelegt.

*var*<br/>
[in] Eine Variante, die zum Initialisieren des Eigenschaftswerts für die `DBPROP` Struktur hinzugefügt, der die Eigenschaft festgelegt.

*szValue*<br/>
[in] Eine Zeichenfolge, die zum Initialisieren des Eigenschaftswerts für die `DBPROP` Struktur hinzugefügt, der die Eigenschaft festgelegt.

*bValue*<br/>
[in] Ein `BYTE` oder ein boolescher Wert, der zum Initialisieren des Eigenschaftswerts für die `DBPROP` Struktur hinzugefügt, der die Eigenschaft festgelegt.

*nValue*<br/>
[in] Ein Ganzzahlwert, der zum Initialisieren des Eigenschaftswerts für die `DBPROP` Struktur hinzugefügt, der die Eigenschaft festgelegt.

*fltValue*<br/>
[in] Ein Gleitkommawert, der zum Initialisieren des Eigenschaftswerts für die `DBPROP` Struktur hinzugefügt, der die Eigenschaft festgelegt.

*dblValue*<br/>
[in] Ein Gleitkommawert mit doppelter Genauigkeit, verwendet, um den Eigenschaftswert für Initialisieren der `DBPROP` Struktur hinzugefügt, der die Eigenschaft festgelegt.

*cyValue*<br/>
[in] CY Währungswert verwendet, um den Eigenschaftswert für Initialisieren der `DBPROP` Struktur hinzugefügt, der die Eigenschaft festgelegt.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn die Eigenschaft erfolgreich hinzugefügt wurde. Andernfalls **"false"**.

## <a name="cdbpropset"></a> CDBPropSet:: CDBPropSet

Der Konstruktor. Initialisiert die `rgProperties`, `cProperties`, und `guidPropertySet` Felder der [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) Struktur.

### <a name="syntax"></a>Syntax

```cpp
CDBPropSet(const GUID& guid);

CDBPropSet(const CDBPropSet& propset);

CDBPropSet();
```

#### <a name="parameters"></a>Parameter

*guid*<br/>
[in] Eine GUID, die zum Initialisieren der `guidPropertySet` Feld.

*propset*<br/>
[in] Eine andere `CDBPropSet` Objekt für die Copy-Konstruktion.

## <a name="setguid"></a> CDBPropSet::SetGUID

Legt die `guidPropertySet` -Feld in der `DBPROPSET` Struktur.

### <a name="syntax"></a>Syntax

```cpp
void SetGUID(const GUID& guid) throw();
```

#### <a name="parameters"></a>Parameter

*guid*<br/>
[in] Eine GUID zum Festlegen der `guidPropertySet` Feld der [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) Struktur.

### <a name="remarks"></a>Hinweise

Dieses Feld kann festgelegt werden, indem die [Konstruktor](../../data/oledb/cdbpropset-cdbpropset.md) ebenfalls.

## <a name="op_equal"></a> CDBPropSet:: Operator =

Weist den Inhalt einer Eigenschaft, die auf einem anderen Eigenschaftensatz festgelegt.

### <a name="syntax"></a>Syntax

```cpp
CDBPropSet& operator =(CDBPropSet& propset) throw();
```

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CDBPropIDSet-Klasse](../../data/oledb/cdbpropidset-class.md)<br/>
[DBPROPSET-Struktur](/previous-versions/windows/desktop/ms714367(v=vs.85))
[DBPROP-Struktur](/previous-versions/windows/desktop/ms717970(v=vs.85))