---
title: Db_param | Microsoft Docs
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
ms.openlocfilehash: ce7cf5c8e92e7fd6e6e10d7bef0519b1ced4cf62
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880693"
---
# <a name="dbparam"></a>db_param
Ordnet die angegebene Membervariable ein Eingabe- oder Ausgabespalte-Parameter und begrenzt die Variable.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
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
  
#### <a name="parameters"></a>Parameter  
 `ordinal`  
 Die Nummer der Spalte (**DBCOLUMNINFO** Ordnungszahl), ein Feld in das Rowset, das zum Binden von Daten entspricht.  
  
 *ParamType-Objekt* (optional)  
 Der Typ, für den Parameter festgelegt werden. Anbieter unterstützen nur Parameter e/a-Typen, die von der zugrunde liegenden Datenquelle unterstützt werden. Der Typ ist eine Kombination aus einem oder mehreren **DBPARAMIOENUM** Werte:  
  
-   **DBPARAMIO_INPUT** Ein Eingabeparameter.  
  
-   **DBPARAMIO_OUTPUT** Ein Ausgabeparameter.  
  
-   **DBPARAMIO_NOTPARAM** Der Accessor hat keine Parameter. Festlegen von **eParamIO** auf diesen Wert in der Zeile Accessoren daran erinnert werden dem Benutzer, dass Parameter ignoriert werden.  
  
 *DbType* (optional)  
 OLE DB- ["Typindikator" als](https://msdn.microsoft.com/en-us/library/ms711251.aspx) für den Eintrag in der Spalte.  
  
 *Genauigkeit* (optional)  
 Die Genauigkeit für den Eintrag in der Spalte verwendet werden soll. Weitere Informationen finden Sie unter der Beschreibung der **bPrecision** Element von der [DBBINDING-Struktur](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *Skalierung* (optional)  
 Die Dezimalstellen für den Eintrag in der Spalte verwendet werden soll. Weitere Informationen finden Sie unter der Beschreibung der **bScale** Element von der [DBBINDING-Struktur](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *Status* (optional)  
 Eine Membervariable verwendet, um den Status dieser Spalte zu halten. Der Status gibt an, ob der Spaltenwert wie z. B. einen Datenwert oder ein anderer Wert ist **NULL**. Mögliche Werte finden Sie unter [Status](https://msdn.microsoft.com/en-us/library/ms722617.aspx) in der *OLE DB Programmer's Reference*.  
  
 *Länge* (optional)  
 Eine Membervariable dar, das die Größe der Spalte in Bytes enthält.  
  
## <a name="remarks"></a>Hinweise  
 **Db_param** Parameter definiert, dass Sie in Befehlen verwenden; aus diesem Grund verwenden Sie es mit **Db_command**. Beispielsweise können Sie **Db_param** zum Binden von Parametern in SQL-Abfragen oder gespeicherte Prozeduren. Parameter in einer gespeicherten Prozedur werden durch Fragezeichen (?) gekennzeichnet, und die Datenelemente in der Reihenfolge der Parameter gebunden werden soll.  
  
 **Db_param** Memberdaten, die in der OLE DB teilnehmen können, begrenzt `ICommandWithParameters`-basierten Bindung. Der Parametertyp (Eingabe oder Ausgabe), OLE DB-Typ, Genauigkeit, Dezimalstellen, Status und Länge für den angegebenen Parameter festgelegt. Dieses Attribut fügt die OLE DB-Consumer-Makros BEGIN_PARAM_MAP... END_PARAM_MAP. Jedes Element aus, markieren Sie mit, der **Db_param** Attribut nimmt einen Eintrag in der Zuordnung in Form einer COLUMN_ENTRY.  
  
 **Db_param** dient in Verbindung mit der [Db_table](../windows/db-table.md) oder [Db_command](../windows/db-command.md) Attribute.  
  
 Wenn vom Consumer-Attribut-Anbieter dieses Attribut auf eine Klasse angewendet werden, wird der Compiler die Klasse umbenennen \_ *Klassenname*-Accessor, in dem *Klassenname* der eingegebene Name ist der Klasse und der Compiler erstellt auch eine Klasse mit dem Namen *Klassenname*, die sich daraus ableitet \_ *Klassenname*Accessor.  In dieser Klassenansicht werden beide Klassen angezeigt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine Command-Klasse, die basierend auf der SalesbyYear gespeicherte Prozedur in der Northwind-Datenbank. Sie ordnet den ersten Parameter in der gespeicherten Prozedur mit der `m_RETURN_VALUE` Variable, und wird als Output-Parameter definiert. Sie ordnet die letzten beiden (Eingabeparameter) mit `m_Beginning_Date` und `m_Ending_Date`.  
  
 Im folgenden Beispiel wird die `nOutput` Variable mit einem Ausgabeparameter.  
  
```  
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
|**Betrifft**|**Klasse**, `struct`, Member, Methode, lokal|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumerattribute](../windows/ole-db-consumer-attributes.md)   
