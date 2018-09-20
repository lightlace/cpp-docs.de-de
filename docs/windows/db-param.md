---
title: Db_param | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_param
dev_langs:
- C++
helpviewer_keywords:
- db_param attribute
ms.assetid: a28315f5-4722-459e-92ef-32e83c0b205a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6bfd96962cebd4b94e9b1b50ca588ada9af69779
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418384"
---
# <a name="dbparam"></a>db_param

Ordnet die angegebenen Member-Variable mit einem Eingabe- oder ausgabeadapter-Parameter und Variablen begrenzt.

## <a name="syntax"></a>Syntax

```cpp
[ db_param(
   ordinal,
   paramtype="DBPARAMIO_INPUT",
   dbtype,
   precision,
   scale,
   status,
   length
) ]
```

### <a name="parameters"></a>Parameter

*Ordinal*<br/>
Die Nummer der Spalte (DBCOLUMNINFO-Ordnungszahl) für ein Feld in das Rowset, um Daten zu binden.

*ParamType-Objekt*<br/>
(Optional) Der Typ, für den Parameter festlegen. Anbieter unterstützen nur e/a-Parametertypen, die von der zugrunde liegenden Datenquelle unterstützt werden. Der Typ ist eine Kombination aus einem oder mehreren DBPARAMIOENUM-Werten:

- DBPARAMIO_INPUT Eingabeparameter.

- DBPARAMIO_OUTPUT ein Output-Parameter.

- DBPARAMIO_NOTPARAM der Accessor hat keine Parameter. Festlegen von `eParamIO` auf diesen Wert in Zeile Accessoren daran erinnert werden dem Benutzer, dass Parameter ignoriert werden.

*DbType*<br/>
(Optional) OLE DB [Typindikator](/previous-versions/windows/desktop/ms711251\(v=vs.85\)) für den Eintrag in der Spalte.

*precision*<br/>
(Optional) Die Genauigkeit für den Eintrag in der Spalte verwendet werden soll. Weitere Informationen finden Sie unter der Beschreibung der `bPrecision` Element der [DBBINDING-Struktur](/previous-versions/windows/desktop/ms716845\(v=vs.85\))

*Skalieren*<br/>
(Optional) Die Dezimalstellen für den Eintrag in der Spalte verwendet werden soll. Weitere Informationen finden Sie unter der Beschreibung der `bScale` Element der [DBBINDING-Struktur](/previous-versions/windows/desktop/ms716845\(v=vs.85\))

*status*<br/>
(Optional) Eine Membervariable verwendet, um den Status dieser Spalte zu speichern. Der Status gibt an, ob der Wert der Spalte einen Datenwert oder einen anderen Wert, z. B. die NULL ist. Mögliche Werte finden Sie unter [Status](/previous-versions/windows/desktop/ms722617\(v=vs.85\)) in die *OLE DB-Programmierreferenz*.

*length*<br/>
(Optional) Eine Membervariable verwendet, um die Größe der Spalte in Bytes zu speichern.

## <a name="remarks"></a>Hinweise

**Db_param** Parameter definiert, dass Sie in den Befehlen verwenden; aus diesem Grund verwenden Sie ihn mit `db_command`. Beispielsweise können Sie **Db_param** zum Binden von Parametern in SQL-Abfragen oder gespeicherte Prozeduren. Parameter in einer gespeicherten Prozedur sind gekennzeichnet durch die Fragezeichen (?), und die Datenmember in der Reihenfolge der Parameter gebunden werden soll.

**Db_param** begrenzt Memberdaten, die in der OLE DB teilnehmen kann `ICommandWithParameters`-basierten Bindung. Der Parametertyp (Eingabe oder Ausgabe), OLE DB-Typ, Genauigkeit, Dezimalstellen, Status und Länge für den angegebenen Parameter festgelegt. Dieses Attribut fügt die Makros für OLE DB-Consumer BEGIN_PARAM_MAP... END_PARAM_MAP. Jedes Element, markieren Sie Sie mit, der **Db_param** Attribut nimmt einen Eintrag in der Zuordnung in Form einer COLUMN_ENTRY.

**Db_param** dient in Verbindung mit der [Db_table](../windows/db-table.md) oder [Db_command](../windows/db-command.md) Attribute.

Wenn der Consumer Attributanbieter dieses Attribut auf eine Klasse angewendet wird, wird der Compiler die Klasse umbenennen \_ *Klassenname*Accessor, in denen *Klassenname* ist der Name, der Sie zugewiesen haben die Klasse und der Compiler erstellt auch eine Klasse namens *Klassenname*, die sich daraus ableitet \_ *Klassenname*Accessor.  In dieser Klassenansicht werden beide Klassen angezeigt.

## <a name="example"></a>Beispiel

Das folgende Beispiel erstellt eine Command-Klasse, die basierend auf der SalesbyYear gespeicherte Prozedur in der Datenbank Northwind. Wird den ersten Parameter in der gespeicherten Prozedur mit der `m_RETURN_VALUE` Variable, und definiert es als ein Ausgabeparameter. Es ordnet die beiden letzten Parameter (Eingabe) mit `m_Beginning_Date` und `m_Ending_Date`.

Im folgenden Beispiel wird die `nOutput` Variable mit einem Ausgabeparameter.

```cpp
// db_param.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[ db_source(L"my_connection_string"),
  db_command(L"{ ? = CALL dbo.\"Sales by Year\"(?,?) }")  
]
struct CSalesbyYear {
   DBSTATUS m_dwShippedDateStatus;
   DBSTATUS m_dwOrderIDStatus;
   DBSTATUS m_dwSubtotalStatus;
   DBSTATUS m_dwYearStatus;

   DBLENGTH m_dwShippedDateLength;
   DBLENGTH m_dwOrderIDLength;
   DBLENGTH m_dwSubtotalLength;
   DBLENGTH m_dwYearLength;

   // Bind columns
   [ db_column("1", status="m_dwShippedDateStatus", length="m_dwShippedDateLength") ] DBTIMESTAMP m_ShippedDate;
   [ db_column("2", status="m_dwOrderIDStatus", length="m_dwOrderIDLength") ] LONG m_OrderID;
   [ db_column("3", status="m_dwSubtotalStatus", length="m_dwSubtotalLength") ] CURRENCY m_Subtotal;
   [ db_column("4", status="m_dwYearStatus", length="m_dwYearLength") ] TCHAR m_Year[31];

   // Bind parameters
   [ db_param("1", paramtype="DBPARAMIO_OUTPUT") ] LONG m_RETURN_VALUE;
   [ db_param("2", paramtype="DBPARAMIO_INPUT") ] DBTIMESTAMP m_Beginning_Date;
   [ db_param("3", paramtype="DBPARAMIO_INPUT") ] DBTIMESTAMP m_Ending_Date;
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**, Member, Methode, lokal|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumerattribute](../windows/ole-db-consumer-attributes.md)  
