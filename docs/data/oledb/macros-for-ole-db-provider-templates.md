---
title: "Makros f&#252;r OLE DB-Anbietervorlagen"
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
  - "vc.templates.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Makros, OLE DB-Anbietervorlagen"
  - "OLE DB-Anbietervorlagenmakros"
  - "OLE DB-Anbietervorlagen, Makros"
  - "Anbietervorlagenmakros (OLE DB)"
ms.assetid: 909482c5-64ab-4e52-84a9-1c07091db183
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Makros f&#252;r OLE DB-Anbietervorlagen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die OLE DB\-Vorlagen\-Anbietermakros bieten Funktionen in den folgenden Kategorien an:  
  
### Eigenschaftensetzuordnungs\-Makros  
  
|||  
|-|-|  
|[BEGIN\_PROPERTY\_SET](../../data/oledb/begin-property-set.md)|Markiert den Beginn eines Eigenschaftensatzes.|  
|[BEGIN\_PROPERTY\_SET\_EX](../../data/oledb/begin-property-set-ex.md)|Markiert den Beginn eines Eigenschaftensatzes.|  
|[BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md)|Markiert den Beginn eines Eigenschaftensatzes, der außerhalb des Projektumfangs des Anbieters ausgeblendet oder definiert werden kann.|  
|[CHAIN\_PROPERTY\_SET](../../data/oledb/chain-property-set.md)|Verkettet Eigenschaftengruppen zusammen.|  
|[END\_PROPERTY\_SET](../../data/oledb/end-property-set.md)|Markiert das Ende eines Eigenschaftensatzes.|  
|[END\_PROPSET\_MAP](../../data/oledb/end-propset-map.md)|Markiert das Ende einer Eigenschaftensetzuordnung.|  
|[PROPERTY\_INFORMATION\_ENTRY](../../data/oledb/property-info-entry.md)|Legt eine bestimmte Eigenschaft in einem Eigenschaft auf einen Standardwert fest.|  
|[PROPERTY\_INFORMATION\_ENTRY\_EX](../../data/oledb/property-info-entry-ex.md)|Legt eine bestimmte Eigenschaft in einem Eigenschaft auf einen Wert fest, der von Ihnen angegeben wird.  Ermöglicht es Ihnen auch, um Flags und Optionen festzulegen.|  
|[PROPERTY\_INFORMATION\_ENTRY\_VALUE](../../data/oledb/property-info-entry-value.md)|Legt eine bestimmte Eigenschaft in einem Eigenschaft auf einen Wert fest, der von Ihnen angegeben wird.|  
  
### Spalten\-Zuordnungs\-Makros  
  
|||  
|-|-|  
|[BEGIN\_PROVIDER\_COLUMN\_MAP](../../data/oledb/begin-provider-column-map.md)|Markiert den Beginn der Anbieterspalten\-Zuordnungseinträge.|  
|[END\_PROVIDER\_COLUMN\_MAP](../../data/oledb/end-provider-column-map.md)|Markiert das Ende der Anbieterspalten\-Zuordnungseinträge.|  
|[PROVIDER\_COLUMN\_ENTRY](../../data/oledb/provider-column-entry.md)|Stellt eine bestimmte Spalte dar, die vom Anbieter unterstützt wird.|  
|[PROVIDER\_COLUMN\_ENTRY\_GN](../../data/oledb/provider-column-entry-gn.md)|Stellt eine bestimmte Spalte dar, die vom Anbieter unterstützt wird.  Sie können die Größe der Spalte, den Datentyp, Genauigkeit, der Umfang und der Schemarowset GUID angeben.|  
|[PROVIDER\_COLUMN\_ENTRY\_FIXED](../../data/oledb/provider-column-entry-fixed.md)|Stellt eine bestimmte Spalte dar, die vom Anbieter unterstützt wird.  Sie können dem Spaltendatentyp angeben.|  
|[PROVIDER\_COLUMN\_ENTRY\_LENGTH](../../data/oledb/provider-column-entry-length.md)|Stellt eine bestimmte Spalte dar, die vom Anbieter unterstützt wird.  Sie können die Spalte angeben.|  
|[PROVIDER\_COLUMN\_ENTRY\_STR](../../data/oledb/provider-column-entry-str.md)|Stellt eine bestimmte Spalte dar, die vom Anbieter unterstützt wird.  Dabei wird vorausgesetzt, dass der Spaltentyp eine Zeichenfolge ist.|  
|[PROVIDER\_COLUMN\_ENTRY\_TYPE\_LENGTH](../../data/oledb/provider-column-entry-type-length.md)|Stellt eine bestimmte Spalte dar, die vom Anbieter unterstützt wird.  Wie PROVIDER\_COLUMN\_ENTRY\_LENGTH aber ermöglicht Ihnen auch, um die dem Datentyp sowie der Größe Spalte anzugeben.|  
|[PROVIDER\_COLUMN\_ENTRY\_WSTR](../../data/oledb/provider-column-entry-wstr.md)|Stellt eine bestimmte Spalte dar, die vom Anbieter unterstützt wird.  Dabei wird vorausgesetzt, dass der Spaltentyp eine Unicode\-Zeichenfolge ist.|  
  
### Schemarowset\-Makros  
  
|||  
|-|-|  
|[BEGIN\_SCHEMA\_MAP](../../data/oledb/begin-schema-map.md)|Markiert den Beginn einer Schemazuordnung.|  
|[SCHEMA\_ENTRY](../../data/oledb/schema-entry.md)|Ordnet eine GUID mit einer Klasse zu.|  
|[END\_SCHEMA\_MAP](../../data/oledb/end-schema-map.md)|Markiert das Ende einer Schemazuordnung.|  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Erstellen eines OLE DB\-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)   
 [Referenz der OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-reference.md)