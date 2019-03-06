---
title: CUtlProps-Klasse
ms.date: 11/04/2016
f1_keywords:
- CUtlProps
- CUtlProps::GetPropValue
- CUtlProps.GetPropValue
- GetPropValue
- CUtlProps::IsValidValue
- CUtlProps.IsValidValue
- IsValidValue
- CUtlProps
- OnPropertyChanged
- CUtlProps.OnPropertyChanged
- CUtlProps::OnPropertyChanged
- SetPropValue
- ATL::CUtlProps<T>::SetPropValue
- ATL.CUtlProps<T>.SetPropValue
- ATL.CUtlProps.SetPropValue
- CUtlProps::SetPropValue
- CUtlProps<T>::SetPropValue
- CUtlProps.SetPropValue
- CUtlProps<T>.SetPropValue
- ATL::CUtlProps::SetPropValue
helpviewer_keywords:
- CUtlProps class
- GetPropValue method
- IsValidValue method
- OnInterfaceRequested method
- OnPropertyChanged method
- SetPropValue method
ms.assetid: bb525178-765c-4e23-a110-c0fd70c05437
ms.openlocfilehash: 1c45e28e0e74d7216023f06ad22896c53c9226b8
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423052"
---
# <a name="cutlprops-class"></a>CUtlProps-Klasse

Die Eigenschaften für eine Vielzahl von Schnittstellen für OLE DB-Eigenschaft implementiert (z. B. `IDBProperties`, `IDBProperties`, und `IRowsetInfo`).

## <a name="syntax"></a>Syntax

```cpp
template < class T >
class ATL_NO_VTABLE CUtlProps : public CUtlPropsBase
```

### <a name="parameters"></a>Parameter

*T*<br/>
Die Klasse enthält die `BEGIN_PROPSET_MAP`.

## <a name="requirements"></a>Anforderungen

**Header:** „atldb.h“

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[GetPropValue](#getpropvalue)|Ruft eine Eigenschaft aus einem Eigenschaftensatz ab.|
|[IsValidValue](#isvalidvalue)|Verwendet, um einen Wert zu überprüfen, bevor Sie eine Eigenschaft festlegen.|
|[OnInterfaceRequested](#oninterfacerequested)|Behandelt Anforderungen für eine optionale Schnittstelle, wenn ein Consumer eine Methode für ein Objekt erstellen-Schnittstelle aufruft.|
|[OnPropertyChanged](#onpropertychanged)|Wird aufgerufen, nach dem Festlegen einer Eigenschaft für die verkettete Eigenschaften zu behandeln.|
|[SetPropValue](#setpropvalue)|Legt eine Eigenschaft in einem Eigenschaftensatz an.|

## <a name="remarks"></a>Hinweise

Die meisten dieser Klasse ist ein Implementierungsdetail.

`CUtlProps` enthält zwei Member zum Festlegen von Eigenschaften intern an: [GetPropValue](../../data/oledb/cutlprops-getpropvalue.md) und [SetPropValue](../../data/oledb/cutlprops-setpropvalue.md).

Weitere Informationen zu den Makros, die in einer Set-Zuordnung von Eigenschaft verwendet, finden Sie unter [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) und [END_PROPSET_MAP](../../data/oledb/end-propset-map.md).

## <a name="getpropvalue"></a> CUtlProps::GetPropValue

Ruft eine Eigenschaft aus einem Eigenschaftensatz ab.

### <a name="syntax"></a>Syntax

```cpp
OUT_OF_LINE HRESULT GetPropValue(const GUID* pguidPropSet,
   DBPROPID dwPropId,
   VARIANT* pvValue);
```

#### <a name="parameters"></a>Parameter

*pguidPropSet*<br/>
[in] Die GUID für den Eigenschaftensatz.

*dwPropId*<br/>
[in] Der Property-Index.

*pvValue*<br/>
[out] Ein Zeiger auf einen Variant-Wert, der den neue Eigenschaftswert enthält.

### <a name="return-value"></a>Rückgabewert

`Failure` für Fehler und S_OK, wenn erfolgreich.

## <a name="isvalidvalue"></a> CUtlProps::IsValidValue

Verwendet, um einen Wert zu überprüfen, bevor Sie eine Eigenschaft festlegen.

### <a name="syntax"></a>Syntax

```cpp
virtual HRESULT CUtlPropsBase::IsValidValue(ULONG /* iCurSet */,
   DBPROP* pDBProp);
```

#### <a name="parameters"></a>Parameter

*iCurSet*<br/>
Der Index im Array Eigenschaftensatz; NULL, wenn nur eine Eigenschaft festgelegt ist.

*pDBProp*<br/>
Die Eigenschafts-ID und den neuen Wert in eine [DBPROP](/previous-versions/windows/desktop/ms717970(v=vs.85)) Struktur.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT. Der Standardrückgabewert ist S_OK.

### <a name="remarks"></a>Hinweise

Wenn Sie Überprüfungsroutinen, die Sie nach einem Wert ausgeführt wird, die Sie verwenden verfügen, um eine Eigenschaft festlegen möchten, sollten Sie diese Funktion überschreiben. Beispielsweise konnte DBPROP_AUTH_PASSWORD für eine Kennworttabelle, um einen gültigen Wert zu bestimmen, überprüft werden.

## <a name="oninterfacerequested"></a> CUtlProps::OnInterfaceRequested

Behandelt Anforderungen für eine optionale Schnittstelle, wenn ein Consumer eine Methode eines Objekts erstellen Schnittstellen aufruft.

### <a name="syntax"></a>Syntax

```cpp
virtual HRESULT CUtlPropsBase::OnInterfaceRequested(REFIID riid);
```

#### <a name="parameters"></a>Parameter

*riid*<br/>
[in] Die IID für die angeforderte Schnittstelle. Weitere Informationen finden Sie unter der Beschreibung des der *Riid* Parameter `ICommand::Execute` in die *OLE DB-Programmierreferenz* (in der *MDAC SDK*).

### <a name="remarks"></a>Hinweise

`OnInterfaceRequested` Consumeranforderungen für eine optionale Schnittstelle verarbeitet, wenn ein Consumer eine Methode eines Objekts erstellen Schnittstellen aufruft (z. B. `IDBCreateSession`, `IDBCreateCommand`, `IOpenRowset`, oder `ICommand`). Die entsprechende OLE DB-Eigenschaft für die angeforderte Schnittstelle festgelegt. Angenommen, fordert der Consumer `IID_IRowsetLocate`, `OnInterfaceRequested` legt die `DBPROP_IRowsetLocate` Schnittstelle. Auf diese Weise verwaltet den richtigen Status während der rowseterstellung.

Diese Methode wird aufgerufen, wenn der Consumer ruft `IOpenRowset::OpenRowset` oder `ICommand::Execute`.

Wenn ein Consumer ein Objekt öffnet, und eine optionale Schnittstelle fordert, sollte der Anbieter die Schnittstelle auf VARIANT_TRUE fest zugeordnete Eigenschaft festlegen. Eigenschaft-spezifische Verarbeitung zu `OnInterfaceRequested` wird aufgerufen, bevor des Anbieters `Execute` Methode wird aufgerufen. In der Standardeinstellung `OnInterfaceRequested` behandelt die folgenden Schnittstellen:

- `IRowsetLocate`

- `IRowsetChange`

- `IRowsetUpdate`

- `IConnectionPointContainer`

- `IRowsetScroll`

Wenn Sie andere Schnittstellen zu verarbeiten möchten, überschreiben Sie diese Funktion in Ihrer Datenklasse Quelle "," Sitzung "," Befehl "oder" Rowset, funktioniert. Die Außerkraftsetzung funktionieren über die normalen festlegen/Abrufen von Eigenschaften-Schnittstellen, um sicherzustellen, dass das Festlegen von Eigenschaften auch alle verketteten Eigenschaften legt diese fest (siehe [OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)).

## <a name="onpropertychanged"></a> CUtlProps::OnPropertyChanged

Wird aufgerufen, nach dem Festlegen einer Eigenschaft für die verkettete Eigenschaften zu behandeln.

### <a name="syntax"></a>Syntax

```cpp
virtual HRESULT OnPropertyChanged(ULONG /* iCurSet */,
   DBPROP* pDBProp);
```

#### <a name="parameters"></a>Parameter

*iCurSet*<br/>
Der Index im Array Eigenschaftensatz; NULL, wenn nur eine Eigenschaft festgelegt ist.

*pDBProp*<br/>
Die Eigenschafts-ID und den neuen Wert in eine [DBPROP](/previous-versions/windows/desktop/ms717970(v=vs.85)) Struktur.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT. Der Standardrückgabewert ist S_OK.

### <a name="remarks"></a>Hinweise

Sollten Sie behandeln verkettete Eigenschaften, z. B. Lesezeichen oder Updates, deren Werte den Wert einer anderen Eigenschaft abhängig sind, sollten Sie diese Funktion überschreiben.

### <a name="example"></a>Beispiel

In dieser Funktion erhält der Benutzer die Eigenschafts-ID aus der `DBPROP*` Parameter. Jetzt ist es möglich, die ID für eine Eigenschaft, eine Verkettung zu vergleichen. Wenn die Eigenschaft gefunden wird, `SetProperties` wird aufgerufen, mit der Eigenschaft, die jetzt in Verbindung mit einer anderen Eigenschaft festgelegt werden. In diesem Fall wird die `DBPROP_IRowsetLocate`, `DBPROP_LITERALBOOKMARKS`, oder `DBPROP_ORDEREDBOOKMARKS` Eigenschaft, die eine Festlegen der `DBPROP_BOOKMARKS` Eigenschaft.

[!code-cpp[NVC_OLEDB_Provider#2](../../data/oledb/codesnippet/cpp/cutlprops-onpropertychanged_1.h)]

## <a name="setpropvalue"></a> CUtlProps::SetPropValue

Legt eine Eigenschaft in einem Eigenschaftensatz an.

### <a name="syntax"></a>Syntax

```cpp
HRESULT SetPropValue(const GUID* pguidPropSet,
   DBPROPID dwPropId,
   VARIANT* pvValue);
```

#### <a name="parameters"></a>Parameter

*pguidPropSet*<br/>
[in] Die GUID für den Eigenschaftensatz.

*dwPropId*<br/>
[in] Der Property-Index.

*pvValue*<br/>
[in] Ein Zeiger auf einen Variant-Wert, der den neue Eigenschaftswert enthält.

### <a name="return-value"></a>Rückgabewert

`Failure` für Fehler und S_OK, wenn erfolgreich.

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)