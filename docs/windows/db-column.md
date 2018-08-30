---
title: Db_column | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_column
dev_langs:
- C++
helpviewer_keywords:
- db_column attribute
ms.assetid: 58da4afc-f69c-4ae6-af9a-3f9515f56081
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 10acf2b69eaa6b49145e671d437f18dfaff8e499
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43195789"
---
# <a name="dbcolumn"></a>db_column

Bindet eine angegebene Spalte auf eine Variable im Rowset.

## <a name="syntax"></a>Syntax

```cpp
[ db_column(
   ordinal,
   dbtype,
   precision,
   scale,
   status,
   length
) ]
```

#### <a name="parameters"></a>Parameter

*Ordinal*  
Die Spaltenordnungszahl (`DBCOLUMNINFO` Ordnungszahl) oder einen Spaltennamen (ANSI oder Unicode-Zeichenfolge) für ein Feld in das Rowset, um Daten zu binden. Wenn Sie Zahlen verwenden, können Sie mit der überspringen aufeinander folgende Ordnungszahlen (z. B.: 1, 2, 3, 5). Der Name darf Leerzeichen enthalten, wenn der OLE DB-Anbieter, die, den Sie verwenden, dies unterstützt. Beispielsweise können Sie eine der folgenden Formate:

```cpp
[db_column("2")] TCHAR szCity[30];
[db_column(L"city_name")] TCHAR szCity[30];
```

*DbType* (optional)  
OLE DB [Typindikator](/previous-versions/windows/desktop/ms711251\(v=vs.85\)) für den Eintrag in der Spalte.

*Genauigkeit* (optional)  
Die Genauigkeit für den Eintrag in der Spalte verwendet werden soll. Weitere Informationen finden Sie unter der Beschreibung des der `bPrecision` Element der [DBBINDING-Struktur](/previous-versions/windows/desktop/ms716845\(v=vs.85\))

*Skalierung* (optional)  
Die Dezimalstellen für den Eintrag in der Spalte verwendet werden soll. Weitere Informationen finden Sie unter der Beschreibung der `bScale` Element der [DBBINDING-Struktur](/previous-versions/windows/desktop/ms716845\(v=vs.85\))

*Status* (optional)  
Eine Membervariable verwendet, um den Status dieser Spalte zu speichern. Der Status gibt an, ob der Wert der Spalte einen Datenwert oder einen anderen Wert, z. B. die NULL ist. Mögliche Werte finden Sie unter [Status](/previous-versions/windows/desktop/ms722617\(v=vs.85\)) in die *OLE DB-Programmierreferenz*.

*Länge* (optional)  
Eine Membervariable verwendet, um die Größe der Spalte in Bytes zu speichern.

## <a name="remarks"></a>Hinweise

**Db_column** bindet die angegebene Tabellenspalte an eine Variable im Rowset. Er begrenzt die Daten, die in der OLE DB teilnehmen kann `IAccessor`-basierten Bindung. Dieses Attribut richtet die spaltenzuordnung, die normalerweise definiert mithilfe der OLE DB-Consumer-Makros [BEGIN_COLUMN_MAP](../data/oledb/begin-column-map.md), [END_COLUMN_MAP](../data/oledb/end-column-map.md), und [COLUMN_ENTRY](../data/oledb/column-entry.md). Diese Bearbeitung der OLE DB [DBBINDING-Struktur](/previous-versions/windows/desktop/ms716845\(v=vs.85\)) die angegebene Spalte zu binden. Jedes Element, markieren Sie Sie mit, der **Db_column** Attribut nimmt einen Eintrag in der spaltenzuordnung in Form von einem Eintrag in der Spalte. Daher rufen Sie dieses Attribut, in denen würden Sie die spaltenzuordnung, d. h. in der Klasse-Befehl oder eine Tabelle platzieren.

Verwendung **Db_column** in Verbindung mit der [Db_table](../windows/db-table.md) oder [Db_command](../windows/db-command.md) Attribute.

Wenn der Consumer Attributanbieter dieses Attribut auf eine Klasse angewendet wird, wird der Compiler die Klasse umbenennen \_ *Klassenname*Accessor, in denen *Klassenname* ist der Name, der Sie zugewiesen haben die Klasse und der Compiler erstellt auch eine Klasse namens *Klassenname*, die sich daraus ableitet \_ *Klassenname*Accessor.  In dieser Klassenansicht werden beide Klassen angezeigt.

Beispiele für dieses Attribut in einer Anwendung verwendet, finden Sie unter den Beispielen [AtlAgent](https://github.com/Microsoft/VCSamples), und [MultiRead](https://github.com/Microsoft/VCSamples).

## <a name="example"></a>Beispiel

In diesem Beispiel wird eine Spalte gebunden, in einer Tabelle eine **lange** -Datenmember und Felder Status und Länge angegeben.

```cpp
// db_column_1.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[ db_command(L"Select * from Products") ]
class CProducts {
   DBSTATUS m_dwProductIDStatus;
   DBLENGTH m_dwProductIDLength;

   [ db_column("1", status="m_dwProductIDStatus", length="m_dwProductIDLength") ] LONG m_ProductID;
};
```

## <a name="example"></a>Beispiel

In diesem Beispiel bindet die vier Spalten zu einer **lange**, eine Zeichenfolge, die einen Zeitstempel, und ein `DB_NUMERIC` ganze Zahl, die in dieser Reihenfolge.

```cpp
// db_column_2.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[ db_command(L"Select * from Products") ]
class CProducts {
   [db_column("1")] LONG m_OrderID;
   [db_column("2")] TCHAR m_CustomerID[6];
   [db_column("4")] DB_NUMERIC m_OrderDate;
   [db_column("7", dbtype="DBTYPE_NUMERIC")] DB_NUMERIC m_ShipVia;
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**, Member, Methode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumerattribute](../windows/ole-db-consumer-attributes.md)  
[Klassenattribute](../windows/class-attributes.md)  
