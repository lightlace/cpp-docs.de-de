---
title: Db_column | Microsoft Docs
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
ms.openlocfilehash: 35ab2472ac9e46b620ca735d06b23806126871e0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879632"
---
# <a name="dbcolumn"></a>db_column
Bindet eine angegebene Spalte auf eine Variable im Rowset.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
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
 `ordinal`  
 Die Spaltenordnungszahl (**DBCOLUMNINFO** Ordnungszahl) oder Spaltennamen (ANSI oder Unicode-Zeichenfolge), ein Feld in das Rowset, das zum Binden von Daten entspricht. Wenn Sie Zahlen verwenden, können Sie aufeinander folgende Ordinalzahlen überspringen (z. B.: 1, 2, 3, 5). Der Name darf Leerzeichen enthalten, sofern die Verwendung von OLE DB-Anbieter unterstützt. Beispielsweise können Sie eine der folgenden Formate:  
  
```  
[db_column("2")] TCHAR szCity[30];  
[db_column(L"city_name")] TCHAR szCity[30];  
```  
  
 *DbType* (optional)  
 OLE DB- ["Typindikator" als](https://msdn.microsoft.com/en-us/library/ms711251.aspx) für den Eintrag in der Spalte.  
  
 *Genauigkeit* (optional)  
 Die Genauigkeit für den Eintrag in der Spalte verwendet werden soll. Einzelheiten finden Sie in der Beschreibung der `bPrecision` Element von der [DBBINDING-Struktur](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *Skalierung* (optional)  
 Die Dezimalstellen für den Eintrag in der Spalte verwendet werden soll. Weitere Informationen finden Sie unter der Beschreibung der `bScale` Element von der [DBBINDING-Struktur](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *Status* (optional)  
 Eine Membervariable verwendet, um den Status dieser Spalte zu halten. Der Status gibt an, ob der Spaltenwert wie z. B. einen Datenwert oder ein anderer Wert ist **NULL**. Mögliche Werte finden Sie unter [Status](https://msdn.microsoft.com/en-us/library/ms722617.aspx) in der *OLE DB Programmer's Reference*.  
  
 *Länge* (optional)  
 Eine Membervariable dar, das die Größe der Spalte in Bytes enthält.  
  
## <a name="remarks"></a>Hinweise  
 **Db_column** bindet die angegebene Tabellenspalte an eine Variable im Rowset. Er begrenzt Memberdaten, die OLE DB-beteiligt sein können `IAccessor`-basierten Bindung. Dieses Attribut richtet die spaltenzuordnung normalerweise definiert mithilfe der OLE DB-Consumer-Makros [BEGIN_COLUMN_MAP](../data/oledb/begin-column-map.md), [END_COLUMN_MAP](../data/oledb/end-column-map.md), und [COLUMN_ENTRY](../data/oledb/column-entry.md). Diese Bearbeitung der OLE DB- [DBBINDING-Struktur](https://msdn.microsoft.com/en-us/library/ms716845.aspx) die angegebene Spalte zu binden. Jedes Element aus, markieren Sie mit, der **Db_column** Attribut nimmt einen Eintrag in der spaltenzuordnung in Form von einem Eintrag in der Spalte. Daher rufen Sie dieses Attribut, in dem Sie die spaltenzuordnung, also in der Klasse Befehlsklasse oder Tabellenklasse setzen würden.  
  
 Verwendung **Db_column** in Verbindung mit der [Db_table](../windows/db-table.md) oder [Db_command](../windows/db-command.md) Attribute.  
  
 Wenn vom Consumer-Attribut-Anbieter dieses Attribut auf eine Klasse angewendet werden, wird der Compiler die Klasse umbenennen \_ *Klassenname*-Accessor, in dem *Klassenname* der eingegebene Name ist der Klasse und der Compiler erstellt auch eine Klasse mit dem Namen *Klassenname*, die sich daraus ableitet \_ *Klassenname*Accessor.  In dieser Klassenansicht werden beide Klassen angezeigt.  
  
 Beispiele für dieses Attribut in einer Anwendung verwendet, finden Sie unter den Beispielen [AtlAgent](http://msdn.microsoft.com/en-us/52bef5da-c1a0-4223-b4e6-9e464b6db409), und [MultiRead](http://msdn.microsoft.com/en-us/5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel bindet eine Spalte in einer Tabelle zu einer **lange** -Datenmember und Felder Status und Länge angegeben.  
  
```  
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
 Dieses Beispiel bindet vier Spalten zu einer **lange**, eine Zeichenfolge, die einen Zeitstempel an, und ein **DB_NUMERIC** ganze Zahl, die in dieser Reihenfolge.  
  
```  
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
|**Betrifft**|**Klasse**, `struct`, Member, -Methode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [OLE Consumerattribute DB-](../windows/ole-db-consumer-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
