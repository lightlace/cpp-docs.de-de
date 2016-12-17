---
title: "db_table"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_table"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_table attribute"
ms.assetid: ff9eb957-4e6d-4175-afcc-fd8ea916cec0
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# db_table
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Öffnet eine OLE DB\-Tabelle.  
  
## Syntax  
  
```  
  
      [ db_table(   
   db_table,   
   name,   
   source_name,   
   hresult   
) ]  
```  
  
#### Parameter  
 *db\_table*  
 Eine Zeichenfolge, die den Namen einer Datenbanktabelle angibt \(z. B. „Products“\).  
  
 *Name* \(optional\)  
 Der Name des Handles, das Sie verwenden, um mit der Tabelle zu bearbeiten.  Sie müssen diesen Parameter angeben, wenn Sie mehr als eine Zeile der Ergebnisse zurückgeben möchten.  **db\_table** generiert eine Variable mit dem angegebenen *Namen,* der verwendet werden kann, um das Rowset zu durchlaufen oder Abfragen mehrerer Aktion auszuführen.  
  
 *source\_name* \(optional\)  
 Die `CSession`\-Variable oder eine Instanz einer Klasse, die das `db_source` darauf angewendeten Attribut enthält, auf dem der Befehl ausgeführt wird, oder legt diesen fest.  Weitere Informationen finden Sie unter [db\_source](../windows/db-source.md).  
  
 `hresult` \(optional\)  
 Identifiziert die Variable, die `HRESULT` dieses Befehls Datenbank erhält.  Wenn die Variable nicht vorhanden ist, wird sie automatisch vom Attribut eingefügt.  
  
## Hinweise  
 **db\_table** erstellt ein [CTable](../data/oledb/ctable-class.md)\-Objekt, das durch einen OLE DB\-Consumer verwendet wird, um eine Tabelle zu öffnen.  Dieses Attribut kann nur auf Klassenebene verwenden. Sie können sie nicht inline verwenden.  Verwenden Sie **db\_column** , um Tabellenspalten zu den Variablen gebunden werden soll. \(Verwenden Sie **db\_param** festgelegt usw.\) entnehmen dem Parametertyp getrennt.  
  
 Wenn der Consumer Attribut für Textanbieter dieses Attribut auf eine Klasse angewendet wird, benennt der Compiler die Klasse zum \_TheClassNameAccessor, in dem *TheClassName* der Name ist, den Sie für die Klasse haben, und der Compiler außerdem eine Klasse erstellt, die *TheClassName* aufgerufen wird *,* die vom \_TheClassNameAccessor berechnet.  In der Klassenansicht finden Sie unter beide Klassen.  
  
## Beispiel  
 Im folgenden Beispiel wird die Tabelle Products für `CProducts`.  
  
```  
// db_table.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_table(L"dbo.Products") ]  
class CProducts {  
   [ db_column("1") ] LONG m_ProductID;  
};  
```  
  
 Ein Beispiel für dieses Attribut, das in einer Anwendung verwendet wird, finden Sie in den Beispielen [AtlAgent](assetId:///52bef5da-c1a0-4223-b4e6-9e464b6db409) und [MultiRead](assetId:///5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)