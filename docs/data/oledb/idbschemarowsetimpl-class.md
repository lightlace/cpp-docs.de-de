---
title: "IDBSchemaRowsetImpl-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "IDBSchemaRowsetImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDBSchemaRowsetImpl-Klasse"
ms.assetid: bd7bf0d7-a1c6-4afa-88e3-cfdbdf560703
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# IDBSchemaRowsetImpl-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bietet die Implementierung für Schemarowsets.  
  
## Syntax  
  
```  
template <class SessionClass>  
class ATL_NO_VTABLE IDBSchemaRowsetImpl : public IDBSchemaRowset  
```  
  
#### Parameter  
 `SessionClass`  
 Die Klasse, mit der `IDBSchemaRowsetImpl` geerbt wird. Diese Klasse ist in der Regel die Sitzungsklasse des Benutzers.  
  
## Mitglieder  
  
### Methoden  
  
|||  
|-|-|  
|[CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md)|Überprüft die Gültigkeit von Einschränkungen an einem Schemarowset.|  
|[CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md)|Implementiert eine COM\-Objekterstellerfunktion für das mit dem Vorlagenparameter angegebene Objekt.|  
|[SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)|Gibt an, welche Einschränkungen Sie für ein bestimmtes Schemarowset unterstützen.|  
  
### Schnittstellenmethoden  
  
|||  
|-|-|  
|[GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)|Gibt ein Schemarowset zurück.|  
|[GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)|Gibt eine Liste der Schemarowsets zurück, auf die [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) zugreifen kann.|  
  
## Hinweise  
 Diese Klasse implementiert die [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx)\-Schnittstelle und die vorlagenbasierte Erstellerfunktion [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md).  
  
 OLE DB verwendet die Schemarowsets, um Daten zu den Daten in einem Anbieter zurückzugeben. Solche Daten werden häufig als „Metadaten“ bezeichnet. Standardmäßig muss ein Anbieter immer `DBSCHEMA_TABLES`, **DBSCHEMA\_COLUMNS** und **DBSCHEMA\_PROVIDER\_TYPES** unterstützen, wie in [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) in der *OLE DB\-Programmiererreferenz* beschrieben. Schemarowsets werden in einer Schemazuordnung festgelegt. Informationen zu den Schemazuordnungseinträgen finden Sie unter [SCHEMA\_ENTRY](../../data/oledb/schema-entry.md).  
  
 Der OLE DB\-Anbieterassistent im ATL\-Objektassistenten generiert automatisch Code für die Schemarowsets in Ihrem Projekt. \(Standardmäßig unterstützt der Assistent die bereits erwähnten obligatorischen Schemarowsets.\) Wenn Sie einen Consumer mithilfe des ATL\-Objektassistenten erstellen, verwendet der Assistent Schemarowsets, um die richtigen Daten an einen Anbieter zu binden. Wenn Sie die Schemarowsets nicht implementieren, um die richtigen Metadaten bereitzustellen, bindet der Assistent nicht die richtigen Daten.  
  
 Informationen über die Unterstützung für Schemarowsets in Ihrem Anbieter finden Sie unter [Supporting Schema Rowsets](../../data/oledb/supporting-schema-rowsets.md) \(Unterstützen von Schemarowsets\).  
  
 Weitere Informationen zu Schemarowsets finden Sie unter [Schema Rowsets](https://msdn.microsoft.com/en-us/library/ms712921.aspx) \(Schemarowsets\) in der *OLE DB\-Programmiererreferenz*.  
  
## Anforderungen  
 **Header:** „atldb.h“  
  
## Siehe auch  
 [IDBSchemaRowsetImpl Class Members](assetId:///e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [Schemarowset\-Klassen und Typedef\-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)   
 [Unterstützen von Schemarowsets](../../data/oledb/supporting-schema-rowsets.md)