---
title: "db_accessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_accessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_accessor attribute"
ms.assetid: ec407a9f-24d7-4822-96d4-7cc6a0301815
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# db_accessor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gruppen **db\_column**\-Attribute, die an er\-basiert Bindung `IAccessor`teilnehmen.  
  
## Syntax  
  
```  
  
      [ db_accessor(   
   num,   
   auto   
) ]  
```  
  
#### Parameter  
 *num*  
 Gibt die Zahl an \(Accessor einen nullbasierten ganzzahligen Index\).  Sie müssen in Zahlen Accessor mithilfe der Reihenfolge zunehmender ganze Zahlen oder der definierten Werte angeben.  
  
 *Auto*  
 Ein boolescher Wert, der angibt, ob der Accessor automatisch abgerufenes \(TRUE\) ist oder nicht abgerufen \(**FALSE**\).  
  
## Hinweise  
 **db\_accessor** definiert den zugrunde liegenden OLE DB\-Accessor für folgende **db\_column** und **db\_param**\-Attribute in der gleichen Klasse oder Funktion.  **db\_accessor** ist ein Member der Ebene verwendet werden und wird verwendet, um **db\_column**\-Attribute zu gruppieren, die an er\-basiert Bindung in OLE DB `IAccessor`teilnehmen.  Es wird entweder in Verbindung mit den **db\_table** oder **db\_command**\-Attributen verwendet.  Dieses Attribut aufrufen und [BEGIN\_ACCESSOR](../data/oledb/begin-accessor.md) entspricht dem Aufrufen der [END\_ACCESSOR](../data/oledb/end-accessor.md) Makros vergleichbar.  
  
 **db\_accessor** generiert ein Rowset und bindet es an den entsprechenden Accessor ist.  Wenn Sie nicht **db\_accessor**aufrufen, wird Accessor 0 automatisch generiert und Spaltenbindungen werden alle zu diesem Accessor Datenbindungsausdrücken zugeordnet.  
  
 **db\_accessor** Gruppen datenbank\-Spalten Befehlsbindungen in eine oder mehrere Accessoren.  Ausführliche Informationen über die Szenarien, in denen mehrere Accessoren verwenden müssen, finden Sie unter [Verwenden mehrerer Accessoren in einem Rowset](../data/oledb/using-multiple-accessors-on-a-rowset.md).  Siehe auch „Benutzer\-Datensatz\-Unterstützung für mehrere Accessoren“ in [Benutzerdatensätze](../data/oledb/user-records.md).  
  
 Wenn der Consumer Attribut für Textanbieter dieses Attribut auf eine Klasse angewendet wird, benennt der Compiler die Klasse zum \_TheClassNameAccessor, in dem *TheClassName* der Name ist, den Sie für die Klasse haben, und der Compiler außerdem eine Klasse erstellt, die *TheClassName* aufgerufen wird *,* die vom \_TheClassNameAccessor berechnet.  In der Klassenansicht finden Sie unter beide Klassen.  
  
## Beispiel  
 Im folgenden Beispiel wird **db\_accessor** , um Spalten aus der Tabelle Orders der Datenbank Northwind in zwei Accessoren zu gruppieren.  Accessor 0 ist ein automatischer Accessor, und Accessor 1 ist nicht möglich.  
  
```  
// cpp_attr_ref_db_accessor.cpp  
// compile with: /LD /link /OPT:NOREF  
#define _ATL_ATTRIBUTES  
#include <atlbase.h>  
#include <atldbcli.h>  
  
[ db_command(L"SELECT LastName, FirstName FROM Orders") ]  
class CEmployees {  
public:  
   [ db_accessor(0, TRUE) ];  
   [ db_column("1") ] LONG m_OrderID;  
   [ db_column("2") ] TCHAR m_CustomerID[6];  
   [ db_column("4") ] DBTIMESTAMP m_OrderDate;   
  
   [ db_accessor(1, FALSE) ];  
   [ db_column("8") ] CURRENCY m_Freight;  
};  
```  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|Attributblöcke|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)