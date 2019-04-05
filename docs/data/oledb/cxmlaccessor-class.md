---
title: CXMLAccessor-Klasse
ms.date: 11/04/2016
f1_keywords:
- ATL::CXMLAccessor
- CXMLAccessor
- ATL.CXMLAccessor
- ATL.CXMLAccessor.GetXMLColumnData
- CXMLAccessor::GetXMLColumnData
- CXMLAccessor.GetXMLColumnData
- ATL::CXMLAccessor::GetXMLColumnData
- GetXMLColumnData
- ATL::CXMLAccessor::GetXMLRowData
- ATL.CXMLAccessor.GetXMLRowData
- CXMLAccessor::GetXMLRowData
- CXMLAccessor.GetXMLRowData
- GetXMLRowData
helpviewer_keywords:
- CXMLAccessor class
- GetXMLColumnData method
- GetXMLRowData method
ms.assetid: c88c082c-ec2f-4351-8947-a330b15e448a
ms.openlocfilehash: 85fddb9b77cfc089b2236f2ff82944fec6ef9632
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59036100"
---
# <a name="cxmlaccessor-class"></a>CXMLAccessor-Klasse

Ermöglicht Ihnen Zugriff auf Datenquellen wie Zeichenfolgendaten, wenn Sie keine Kenntnis von den Data Store Schema (zugrunde liegende Struktur) verfügen.

## <a name="syntax"></a>Syntax

```cpp
class CXMLAccessor : public CDynamicStringAccessorW
```

## <a name="requirements"></a>Anforderungen

**Header**: atldbcli.h

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[GetXMLColumnData](#getxmlcolumndata)|Ruft die Spalteninformationen ab.|
|[GetXMLRowData](#getxmlrowdata)|Ruft den gesamten Inhalt einer Tabelle von Zeilen ab.|

## <a name="remarks"></a>Hinweise

Allerdings `CXMLAccessor` unterscheidet sich von `CDynamicStringAccessorW` , sie alle Daten, die aus dem Datenspeicher als XML-Format (tagged) Daten zugegriffen konvertiert. Dies ist besonders nützlich für die Ausgabe auf XML-fähige Webseiten. Die XML-Tag-Namen des Datenspeichers Spaltennamen ist so weit wie möglich entspricht.

Verwendung `CDynamicAccessor` Methoden zum Abrufen der Spalteninformationen. Sie können diese Spalteninformationen verwenden, um einen Accessor dynamisch zur Laufzeit zu erstellen.

Die Spalteninformationen befindet sich in einem Puffer, die von dieser Klasse erstellt und verwaltet. Erhalten Sie die Spalte mit [GetXMLColumnData](#getxmlcolumndata) oder Zeilen mit Daten der Spalte erzielen [GetXMLRowData](#getxmlrowdata).

## <a name="example"></a>Beispiel

[!code-cpp[NVC_OLEDB_Consumer#14](../../data/oledb/codesnippet/cpp/cxmlaccessor-class_1.cpp)]

## <a name="getxmlcolumndata"></a> CXMLAccessor:: GetXMLColumnData

Ruft die Typinformationen Spalte einer Tabelle als XML-formatierte Zeichenfolge mit Daten von der Spalte ab.

### <a name="syntax"></a>Syntax

```cpp
HRESULT GetXMLColumnData(CSimpleStringW& strOutput) throw();
```

#### <a name="parameters"></a>Parameter

*strOutput*<br/>
[out] Ein Verweis auf einen Zeichenfolgenpuffer, enthält die Typ-Spalteninformationen abgerufen werden sollen. Mit XML-Tag-Namen, die mit dem Datenspeicher Spaltennamen übereinstimmen, wird die Zeichenfolge formatiert.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Das folgende Beispiel zeigt, wie die Spalteninformationen für den Typ in XML formatiert ist. `type` Gibt den Datentyp der Spalte Daten an. Beachten Sie, dass die Datentypen in OLE DB-Datentypen, die nicht auf die von der Datenbank, die auf die zugegriffen wird basieren.

`<columninfo>`

`<column type = I2/> ColumnName`

`</columninfo>`

## <a name="getxmlrowdata"></a> CXMLAccessor::GetXMLRowData

Ruft den gesamten Inhalt einer Tabelle als XML-formatierte Zeichenfolge mit Daten von Zeile ab.

### <a name="syntax"></a>Syntax

```cpp
HRESULT GetXMLRowData(CSimpleStringW& strOutput,
   bool bAppend = false) throw();
```

#### <a name="parameters"></a>Parameter

*strOutput*<br/>
[out] Ein Verweis auf einen Puffer, enthält die Tabellendaten abgerufen werden sollen. Die Daten werden als Zeichenfolgendaten mit XML-Tagnamen formatiert, die mit dem Datenspeicher Spaltennamen übereinstimmen.

*bAppend*<br/>
[in] Ein boolescher Wert, der angibt, ob eine Zeichenfolge an das Ende der Ausgabe von Daten angefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Das folgende Beispiel zeigt, wie Daten aus der Zeile in XML formatiert ist. `DATA` unten stellt Sie Daten aus der Zeile dar. Verwenden Sie move, Methoden, in der gewünschten Zeile zu verschieben.

`<row>`

`<column name>DATA</column name>`

`</row>`

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor-Klasse](../../data/oledb/caccessor-class.md)<br/>
[CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicParameterAccessor-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[CDynamicStringAccessor-Klasse](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
[CDynamicStringAccessorA-Klasse](../../data/oledb/cdynamicstringaccessora-class.md)<br/>
[CDynamicStringAccessorW-Klasse](../../data/oledb/cdynamicstringaccessorw-class.md)<br/>
[CManualAccessor-Klasse](../../data/oledb/cmanualaccessor-class.md)