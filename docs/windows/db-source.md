---
title: "db_source | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_source attribute"
ms.assetid: 0ec8bbf7-ade2-4899-bf4c-8608b92779bc
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# db_source
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt eine Verbindung zu einer Datenquelle.  
  
## Syntax  
  
```  
  
      [ db_source(   
   db_source,   
   name,   
   hresult   
) ]  
```  
  
#### Parameter  
 *db\_source*  
 Die Verbindungszeichenfolge, die verwendet wird, um eine Verbindung mit der Datenquelle herzustellen.  Für das Format der Verbindungszeichenfolge finden Sie unter [Verbindungszeichenfolgen und Datenverknüpfungen](https://msdn.microsoft.com/en-us/library/ms718376.aspx) im Microsoft Data Access Components \(MDAC\) SDK.  
  
 *Name* \(optional\)  
 Wenn Sie `db_source` für eine Klasse verwenden, ist *Name* eine Instanz eines Datenquellenobjekts, das das `db_source`\-Attribut verfügt, das auf sie angewendet wird \(siehe Beispiel 1\).  Wenn Sie `db_source` inline in einer Methodenimplementierung verwenden, ist eine Variable *Name* der Methode \(lokal\), die verwendet werden kann, um auf die Datenquelle zuzugreifen \(siehe Beispiel 2\).  Sie führen diesen *Namen* in das `source_name`\-Parameter aus **db\_command** , um die Datenquelle mit einem Befehl zugeordnet werden soll.  
  
 `hresult` \(optional\)  
 Identifiziert die Variable, die `HRESULT` dieses Befehls Datenbank erhält.  Wenn die Variable nicht vorhanden ist, wird sie automatisch vom Attribut eingefügt.  
  
## Hinweise  
 `db_source` erstellt [CDataSource](../data/oledb/cdatasource-class.md) und ein [CSession](../data/oledb/csession-class.md)\-Objekt, die zusammen eine Verbindung mit einer OLE DB\-Consumer\-Datenquelle darstellen.  
  
 Wenn Sie `db_source` für eine Klasse verwenden, wird das `CSession`\-Objekt einen Member der Klasse.  
  
 Wenn Sie `db_source` in einer Methode verwenden, wird der eingefügte Code innerhalb des Bereichs Methoden `CSession` ausgeführt, und das Objekt wird als lokale Variable erstellt.  
  
 `db_source` fügt Datenquelleneigenschaften einer Klasse oder in einer Methode hinzu.  Es wird in Verbindung mit **db\_command** \(das den `db_source` *Namensparameter* als `source_name`\-Parameter erwartet.\)  
  
 Wenn der Consumer Attribut für Textanbieter dieses Attribut auf eine Klasse angewendet wird, benennt der Compiler die Klasse zum \_TheClassNameAccessor, in dem *TheClassName* der Name ist, den Sie für die Klasse haben, und der Compiler außerdem eine Klasse erstellt, die *TheClassName* aufgerufen wird *,* die vom \_TheClassNameAccessor berechnet.  In der Klassenansicht finden Sie unter beide Klassen.  
  
 Ein Beispiel für dieses Attribut, das in einer Anwendung verwendet wird, finden Sie in den Beispielen [AtlAgent](assetId:///52bef5da-c1a0-4223-b4e6-9e464b6db409) und [MultiRead](assetId:///5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## Beispiel  
 In diesem Beispiel wird `db_source` für eine Klasse an, um eine Verbindung mit der Datenquelle `ds` mit der Datenbank Northwind zu erstellen.  `ds` ist ein Handle für die Datenquelle, die auf die `CMyCommand`\-Klasse intern verwendet werden kann.  
  
```  
// db_source_1.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[  
  db_source(L"my_connection_string", name="ds"),  
  db_command(L"select * from Products")  
]  
class CMyCommand {};  
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