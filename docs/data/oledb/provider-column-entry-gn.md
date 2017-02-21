---
title: "PROVIDER_COLUMN_ENTRY_GN | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PROVIDER_COLUMN_ENTRY_GN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROVIDER_COLUMN_ENTRY_GN-Makro"
ms.assetid: be77ba85-634c-4e28-832f-d2fa40413254
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# PROVIDER_COLUMN_ENTRY_GN
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine bestimmte Spalte dar, die vom Anbieter unterstützt wird.  
  
## Syntax  
  
```  
  
PROVIDER_COLUMN_ENTRY_GN (  
name  
, ordinal, flags, colSize, dbtype, precision, scale, guid )  
```  
  
#### Parameter  
 *Name*  
 \[in\] der Spaltenname.  
  
 `ordinal`  
 \[in\] Spaltennummer.  Sofern, dass die Spalte eine Lesezeichenspalte ist, darf die Spaltennummer nicht 0 sein.  
  
 `flags`  
 \[in\] gibt an, wie Daten zurückgegeben werden.  Siehe `dwFlags` die Beschreibung in [DBBINDING\-Strukturen](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 *colSize*  
 \[in\] Die Spaltengröße.  
  
 `dbtype`  
 \[in\] gibt den Datentyp des Werts an.  Siehe **wType** die Beschreibung in [DBBINDING\-Strukturen](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 *precision*  
 \[in\] gibt von Genauigkeit an, die verwendet werden, wenn Daten, Abrufen, wenn *dbType*`DBTYPE_NUMERIC` oder **DBTYPE\_DECIMAL** aufweist.  Siehe **bPrecision** die Beschreibung in [DBBINDING\-Strukturen](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 `scale`  
 \[in\] gibt der Skalierung an, die verwendet werden, wenn Daten, Abrufen, wenn dbType `DBTYPE_NUMERIC` oder **DBTYPE\_DECIMAL** aufweist.  Siehe **bScale** die Beschreibung in [DBBINDING\-Strukturen](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 `guid`  
 Eine Schemarowset GUID.  Siehe [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) in *der OLE DB\-Programmierreferenz* für eine Liste der Schemarowsets und zugehörigen GUIDs.  
  
## Hinweise  
 Ermöglicht Ihnen, die Größe der Spalte, den Datentyp, Genauigkeit, der Umfang und der Schemarowset GUID anzugeben.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [Makros für OLE DB\-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Erstellen eines OLE DB\-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)