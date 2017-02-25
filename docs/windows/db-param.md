---
title: "db_param | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_param"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_param attribute"
ms.assetid: a28315f5-4722-459e-92ef-32e83c0b205a
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# db_param
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ordnet die angegebene Membervariable mit einer Eingabe oder einem Ausgabeparameter und schränkt die Variable ab.  
  
## Syntax  
  
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
  
#### Parameter  
 `ordinal`  
 Die Spaltennummer \(**DBCOLUMNINFO** Ordnungszahl\) entspricht einem Feld im Rowset, um Daten zu binden.  
  
 *paramtype* \(optional\)  
 Der festzulegende Typ für den Parameter.  Anbieter unterstützen nur Parameter E\/A\-Typen, die von der zugrunde liegenden Datenquelle unterstützt werden.  Der Typ ist eine Kombination aus einem oder mehreren **DBPARAMIOENUM**\-Werte:  
  
-   **DBPARAMIO\_INPUT** ein Eingabeparameter.  
  
-   **DBPARAMIO\_OUTPUT** ein Ausgabeparameter.  
  
-   **DBPARAMIO\_NOTPARAM** der Accessor verfügt über keine Parameter.  Einstellung **eParamIO** auf diesen Wert in Zeilen accessoren speichert den Benutzer, dass Parameter ignoriert werden.  
  
 *dbtype* \(optional\)  
 OLE DB [Typ\-Indikator](https://msdn.microsoft.com/en-us/library/ms711251.aspx) für den Eintrag Spalten.  
  
 *Genauigkeit* \(optional\)  
 Die für den Eintrag Spalten zu verwendenden Genauigkeit.  Ausführliche Informationen finden Sie in der Beschreibung von **bPrecision**\-Element [DBBINDING\-Struktur](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *Dezimalstellen* \(optional\)  
 Die für den Eintrag Spalten, Skalierung verwendet werden soll.  Ausführliche Informationen finden Sie in der Beschreibung von **bScale**\-Element [DBBINDING\-Struktur](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *Status* \(optional\)  
 Eine Membervariable verwendet, um den Status dieser Spalte enthält.  Der Status gibt, ob der Spaltenwert ein Datenwert oder ein anderer Wert ist, z **NULL**an.  Mögliche Werte finden Sie in der [Status](https://msdn.microsoft.com/en-us/library/ms722617.aspx)*OLE DB\-Programmierreferenz*.  
  
 *Length* \(optional\)  
 Eine Membervariable verwendet, um die Größe der Spalte in Bytes enthält.  
  
## Hinweise  
 **db\_param** definiert Parameter, die Sie in Befehlen verwendet werden. Daher können Sie es mit **db\_command**.  Beispielsweise können Sie den **db\_param** Binding parametern in SQL\-Abfragen oder gespeicherte Prozeduren verwenden.  Parameter in einer gespeicherten Prozedur werden durch Fragezeichen \(?\) bezeichnet, und Sie sollten die Datenmember in der Reihenfolge binden, in der die Parameter angegeben werden.  
  
 **db\_param** schränkt Memberdaten ab, die an er\-basiert Bindung in OLE DB `ICommandWithParameters`teilnehmen können.  Er legt den Parametertyp \(Eingabe oder Ausgabe\), OLE DB\-Typ, Genauigkeit, Dezimalstellen, Status und Länge für den angegebenen Parameter fest.  Dieses Attribut wird der OLE DB\-Consumer\-Makros ein BEGIN\_PARAM\_MAP…  END\_PARAM\_MAP.  Jeder Member, den Sie mit dem **db\_param**\-Attribut kennzeichnen, nimmt einen Eintrag in der Zuordnung in Form eines COLUMN\_ENTRY.  
  
 **db\_param** wird entweder in Verbindung mit den [db\_table](../windows/db-table.md) oder [db\_command](../windows/db-command.md)\-Attributen verwendet.  
  
 Wenn der Consumer Attribut für Textanbieter dieses Attribut auf eine Klasse angewendet wird, benennt der Compiler die Klasse zum \_TheClassNameAccessor, in dem *TheClassName* der Name ist, den Sie für die Klasse haben, und der Compiler außerdem eine Klasse erstellt, die *TheClassName* aufgerufen wird *,* die vom \_TheClassNameAccessor berechnet.  In der Klassenansicht finden Sie unter beide Klassen.  
  
## Beispiel  
 Im folgenden Beispiel wird eine Befehlsklasse auf Grundlage der SalesbyYear\-gespeicherte Prozedur in der Datenbank Northwind.  Er weist den ersten Parameter in der gespeicherten Prozedur mit der `m_RETURN_VALUE`\-Variable definiert und diesen als Ausgabeparameter.  Sie ordnet die letzten beiden Parameter mit `m_Beginning_Date` \(Eingabe\) und `m_Ending_Date`.  
  
 Im folgenden Beispiel ordnet die `nOutput`\-Variable mit einem Ausgabeparameter.  
  
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
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`, Member, Möglichkeit, lokale Variablen|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)