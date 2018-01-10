---
title: IDBSchemaRowsetImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDBSchemaRowsetImpl
dev_langs: C++
helpviewer_keywords: IDBSchemaRowsetImpl class
ms.assetid: bd7bf0d7-a1c6-4afa-88e3-cfdbdf560703
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6b4f451fa408f2f6470281206e5de3670d069b6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="idbschemarowsetimpl-class"></a>IDBSchemaRowsetImpl-Klasse
Bietet die Implementierung für Schemarowsets.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class SessionClass>  
class ATL_NO_VTABLE IDBSchemaRowsetImpl : public IDBSchemaRowset  
```  
  
#### <a name="parameters"></a>Parameter  
 `SessionClass`  
 Die Klasse, mit der `IDBSchemaRowsetImpl` geerbt wird. Diese Klasse ist in der Regel die Sitzungsklasse des Benutzers.  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md)|Überprüft die Gültigkeit von Einschränkungen an einem Schemarowset.|  
|[CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md)|Implementiert eine COM-Objekterstellerfunktion für das mit dem Vorlagenparameter angegebene Objekt.|  
|[SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)|Gibt an, welche Einschränkungen Sie für ein bestimmtes Schemarowset unterstützen.|  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)|Gibt ein Schemarowset zurück.|  
|[GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)|Gibt eine Liste der Schemarowsets zurück, auf die [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)zugreifen kann.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse implementiert die [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) -Schnittstelle und die vorlagenbasierte Erstellerfunktion [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md).  
  
 OLE DB verwendet die Schemarowsets, um Daten zu den Daten in einem Anbieter zurückzugeben. Solche Daten werden häufig als „Metadaten“ bezeichnet. Standardmäßig muss ein Anbieter immer `DBSCHEMA_TABLES`, **DBSCHEMA_COLUMNS**und **DBSCHEMA_PROVIDER_TYPES**unterstützen, wie in [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) in der *OLE DB-Programmiererreferenz*beschrieben. Schemarowsets werden in einer Schemazuordnung festgelegt. Informationen zu den Schemazuordnungseinträgen finden Sie unter [SCHEMA_ENTRY](../../data/oledb/schema-entry.md).  
  
 Der OLE DB-Anbieterassistent im ATL-Objektassistenten generiert automatisch Code für die Schemarowsets in Ihrem Projekt. (Standardmäßig unterstützt der Assistent die bereits erwähnten obligatorischen Schemarowsets.) Wenn Sie einen Consumer mithilfe des ATL-Objektassistenten erstellen, verwendet der Assistent Schemarowsets, um die richtigen Daten an einen Anbieter zu binden. Wenn Sie die Schemarowsets nicht implementieren, um die richtigen Metadaten bereitzustellen, bindet der Assistent nicht die richtigen Daten.  
  
 Informationen über die Unterstützung für Schemarowsets in Ihrem Anbieter finden Sie unter [Supporting Schema Rowsets](../../data/oledb/supporting-schema-rowsets.md)(Unterstützen von Schemarowsets).  
  
 Weitere Informationen zu Schemarowsets finden Sie unter [Schema Rowsets](https://msdn.microsoft.com/en-us/library/ms712921.aspx) (Schemarowsets) in der *OLE DB-Programmiererreferenz*.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IDBSchemaRowsetImpl-Klasse, Elemente](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [Schemarowset-Klassen und TypeDef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)   
 [Supporting Schema Rowsets](../../data/oledb/supporting-schema-rowsets.md)