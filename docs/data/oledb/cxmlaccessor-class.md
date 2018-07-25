---
title: CXMLAccessor-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CXMLAccessor class
- GetXMLColumnData method
- GetXMLRowData method
ms.assetid: c88c082c-ec2f-4351-8947-a330b15e448a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f25d02b5b8b86a70f63dc2b0ca8d2ba9cb60066b
ms.sourcegitcommit: b217daee32d3413cf33753d9b4dc35a0022b1bfa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "39233412"
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
 *strOutput*  
 [out] Ein Verweis auf einen Zeichenfolgenpuffer, enthält die Typ-Spalteninformationen abgerufen werden sollen. Mit XML-Tag-Namen, die mit dem Datenspeicher Spaltennamen übereinstimmen, wird die Zeichenfolge formatiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="remarks"></a>Hinweise  
 Das folgende Beispiel zeigt, wie die Spalteninformationen für den Typ in XML formatiert ist. `type` Gibt den Datentyp der Spalte Daten an. Beachten Sie, dass die Datentypen in OLE DB-Datentypen, die nicht auf die von der Datenbank, die auf die zugegriffen wird basieren.  
  
 `<columninfo>`  
  
 `<column type = I2/> ColumnName`  
  
 `</columninfo>` 

## <a name="getxmlrowdata"></a> CXMLAccessor:: GetXMLRowData
Ruft den gesamten Inhalt einer Tabelle als XML-formatierte Zeichenfolge mit Daten von Zeile ab.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetXMLRowData(CSimpleStringW& strOutput,   
   bool bAppend = false) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 *strOutput*  
 [out] Ein Verweis auf einen Puffer, enthält die Tabellendaten abgerufen werden sollen. Die Daten werden als Zeichenfolgendaten mit XML-Tagnamen formatiert, die mit dem Datenspeicher Spaltennamen übereinstimmen.  
  
 *bAppend*  
 [in] Ein boolescher Wert, der angibt, ob eine Zeichenfolge an das Ende der Ausgabe von Daten angefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="remarks"></a>Hinweise  
 Das folgende Beispiel zeigt, wie Daten aus der Zeile in XML formatiert ist. `DATA` unten stellt Sie Daten aus der Zeile dar. Verwenden Sie move, Methoden, in der gewünschten Zeile zu verschieben.  
  
 `<row>`  
  
 `<column name>DATA</column name>`  
  
 `</row>`   
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor-Klasse](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicParameterAccessor-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CDynamicStringAccessor-Klasse](../../data/oledb/cdynamicstringaccessor-class.md)   
 [CDynamicStringAccessorA-Klasse](../../data/oledb/cdynamicstringaccessora-class.md)   
 [CDynamicStringAccessorW-Klasse](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [CManualAccessor-Klasse](../../data/oledb/cmanualaccessor-class.md)