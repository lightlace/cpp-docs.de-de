---
title: "db_column | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_column"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_column attribute"
ms.assetid: 58da4afc-f69c-4ae6-af9a-3f9515f56081
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# db_column
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bindet eine angegebene Spalte auf eine Variable im Rowset.  
  
## Syntax  
  
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
  
#### Parameter  
 `ordinal`  
 Der ordinale Spaltennummer \(**DBCOLUMNINFO** Ordnungszahl\) oder Spaltenname \(ANSI oder Unicode\-Zeichenfolge\) entspricht einem Feld im Rowset, um Daten zu binden.  Wenn Sie Zahlen verwenden, können Sie nachfolgende Ordnungszahlen überspringen \(z. B.: 1, 2, 3, 5\).  Der Name enthält möglicherweise leer, wenn der OLE DB\-Anbieter, den Sie verwenden sie unterstützen.  Sie können z. B. eines der folgenden Formate aufweisen:  
  
```  
[db_column("2")] TCHAR szCity[30];  
[db_column(L"city_name")] TCHAR szCity[30];  
```  
  
 *dbtype* \(optional\)  
 OLE DB [Typ\-Indikator](https://msdn.microsoft.com/en-us/library/ms711251.aspx) für den Eintrag Spalten.  
  
 *Genauigkeit* \(optional\)  
 Die für den Eintrag Spalten zu verwendenden Genauigkeit.  Weitere Informationen finden Sie in der Beschreibung des `bPrecision`\-Elements [DBBINDING\-Struktur](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *Dezimalstellen* \(optional\)  
 Die für den Eintrag Spalten, Skalierung verwendet werden soll.  Ausführliche Informationen finden Sie in der Beschreibung von `bScale`\-Element [DBBINDING\-Struktur](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *Status* \(optional\)  
 Eine Membervariable verwendet, um den Status dieser Spalte enthält.  Der Status gibt, ob der Spaltenwert ein Datenwert oder ein anderer Wert ist, z **NULL**an.  Mögliche Werte finden Sie in der [Status](https://msdn.microsoft.com/en-us/library/ms722617.aspx)*OLE DB\-Programmierreferenz*.  
  
 *Length* \(optional\)  
 Eine Membervariable verwendet, um die Größe der Spalte in Bytes enthält.  
  
## Hinweise  
 **db\_column** bindet die angegebene Tabellenspalte auf eine Variable im Rowset.  Sie schränkt Memberdaten ab, die an er\-basiert Bindung in OLE DB `IAccessor`teilnehmen können.  Dieses Attribut richtet die Spaltenzuordnung, die normalerweise mithilfe der OLE DB\-Consumer\-Makros [BEGIN\_COLUMN\_MAP](../data/oledb/begin-column-map.md), [END\_COLUMN\_MAP](../data/oledb/end-column-map.md)und [COLUMN\_ENTRY](../data/oledb/column-entry.md)definiert wurde.  Diese bearbeiten OLE DB [DBBINDING\-Struktur](https://msdn.microsoft.com/en-us/library/ms716845.aspx) , um die angegebene Spalte gebunden wird.  Jeder Member, den Sie mit dem **db\_column**\-Attribut kennzeichnen, nimmt einen Eintrag in der Spaltenzuordnung in Form eines Spalten Zieleintrags.  Daher rufen Sie dieses Attribut an, in dem Sie die Spaltenzuordnung, d. h. in den Befehl oder die Tabellenklasse einfügen würden.  
  
 Verwenden Sie **db\_column** entweder in Verbindung mit den [db\_table](../windows/db-table.md) oder [db\_command](../windows/db-command.md)\-Attributen.  
  
 Wenn der Consumer Attribut für Textanbieter dieses Attribut auf eine Klasse angewendet wird, benennt der Compiler die Klasse zum \_TheClassNameAccessor, in dem *TheClassName* der Name ist, den Sie für die Klasse haben, und der Compiler außerdem eine Klasse erstellt, die *TheClassName* aufgerufen wird *,* die vom \_TheClassNameAccessor berechnet.  In der Klassenansicht finden Sie unter beide Klassen.  
  
 Beispiele dieses Attributs, das in einer Anwendung verwendet wird, finden Sie in den Beispielen [AtlAgent](assetId:///52bef5da-c1a0-4223-b4e6-9e464b6db409)und [MultiRead](assetId:///5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## Beispiel  
 In diesem Beispiel umschließt eine Spalte in einer Tabelle zu einem **long** Datenmember und gibt Datenmember für Status und Länge Feldern an.  
  
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
  
## Beispiel  
 In diesem Beispiel umschließt vier Spalten **long**, einer Zeichenfolge, einen Zeitstempel und eine **DB\_NUMERIC** Ganzzahl, in dieser Reihenfolge.  
  
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
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`, Member, Methode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)