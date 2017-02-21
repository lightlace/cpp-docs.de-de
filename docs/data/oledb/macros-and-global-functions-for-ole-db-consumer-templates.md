---
title: "Makros und globale Funktionen f&#252;r OLE-Consumervorlagen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.templates.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Makros, OLE DB-Consumervorlagen"
  - "OLE DB-Consumervorlagen, Makros"
ms.assetid: 8765eb7b-32dd-407c-bacf-8890ef959837
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Makros und globale Funktionen f&#252;r OLE-Consumervorlagen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die OLE DB\-Consumervorlagen umfassen die folgenden Makros und globalen Funktionen:  
  
### Globale Funktionen  
  
|||  
|-|-|  
|[AtlTraceErrorRecords](../../data/oledb/atltraceerrorrecords.md)|Sichert OLE DB Fehler\-Registerinformation zum Sicherungsgerät, wenn ein Fehler zurückgegeben wird.|  
  
### Accessor\-Zuordnungs\-Makros  
  
|||  
|-|-|  
|[BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)|Markiert den Beginn eines Accessoreintrags.|  
|[BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)|Markiert den Beginn der Accessorzuordnungseinträge.|  
|[END\_ACCESSOR](../../data/oledb/end-accessor.md)|Markiert das Ende eines Accessoreintrags.|  
|[END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)|Markiert das Ende der Accessorzuordnungseinträge.|  
  
### Spalten\-Zuordnungs\-Makros  
  
|||  
|-|-|  
|[BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)|Markiert den Beginn der Spaltenzuordnungseinträge in der Benutzerdatensatz\-Klasse.|  
|[BLOB\_ENTRY](../../data/oledb/blob-entry.md)|Wird verwendet, um ein Binary Large Object \(BLOB\) binden.|  
|[BLOB\_ENTRY\_LENGTH](../../data/oledb/blob-entry-length.md)|Meldet die Länge der BLOBdatenspalte.|  
|[BLOB\_ENTRY\_LENGTH\_STATUS](../../data/oledb/blob-entry-length-status.md)|Gibt die Länge und über den Status der BLOBdatenspalte.|  
|[BLOB\_ENTRY\_STATUS](../../data/oledb/blob-entry-status.md)|Gibt den Status der BLOBdatenspalte.|  
|[BLOB\_NAME](../../data/oledb/blob-name.md)|Wird verwendet, um ein Binary Large Object von Spaltennamen zu binden.|  
|[BLOB\_NAME\_LENGTH](../../data/oledb/blob-name-length.md)|Meldet die Länge der BLOBdatenspalte.|  
|[BLOB\_NAME\_LENGTH\_STATUS](../../data/oledb/blob-name-length-status.md)|Gibt die Länge und über den Status der BLOBdatenspalte.|  
|[BLOB\_NAME\_STATUS](../../data/oledb/blob-name-status.md)|Gibt den Status der BLOBdatenspalte.|  
|[BOOKMARK\_ENTRY](../../data/oledb/bookmark-entry.md)|Stellt einen Lesezeicheneintrag im Rowset dar.  Ein Lesezeicheneintrag ist eine besondere Art Spalteneintrag.|  
|[COLUMN\_ENTRY](../../data/oledb/column-entry.md)|Stellt eine Bindung zu einer bestimmten Spalte in der Datenbank dar.|  
|[COLUMN\_ENTRY\_EX](../../data/oledb/column-entry-ex.md)|Stellt eine Bindung zur spezifischen Spalte in der Datenbank dar.  Unterstützt `type`, *Länge*, *Genauigkeit*, `scale` und *Status* parameter.|  
|[COLUMN\_ENTRY\_LENGTH](../../data/oledb/column-entry-length.md)|Stellt eine Bindung zur spezifischen Spalte in der Datenbank dar.  Unterstützt die *Längen* variable.|  
|[COLUMN\_ENTRY\_LENGTH\_STATUS](../../data/oledb/column-entry-length-status.md)|Stellt eine Bindung zur spezifischen Spalte in der Datenbank dar.  Stütz *status\-* und \- *Längen* parameter.|  
|[COLUMN\_ENTRY\_PS](../../data/oledb/column-entry-ps.md)|Stellt eine Bindung zur spezifischen Spalte in der Datenbank dar.  Stützgenauigkeit Parameter und `scale`.|  
|[COLUMN\_ENTRY\_PS\_LENGTH](../../data/oledb/column-entry-ps-length.md)|Stellt eine Bindung zur spezifischen Spalte in der Datenbank dar.  Unterstützt die *Längenvariable*, *die Genauigkeit* und die `scale`\-Parameter.|  
|[COLUMN\_ENTRY\_PS\_LENGTH\_STATUS](../../data/oledb/column-entry-ps-length-status.md)|Stellt eine Bindung zur spezifischen Spalte in der Datenbank dar.  Stützstatus\- und *\-Längenvariablen*, *Genauigkeit* und Parameter `scale`.|  
|[COLUMN\_ENTRY\_PS\_STATUS](../../data/oledb/column-entry-ps-status.md)|Stellt eine Bindung zur spezifischen Spalte in der Datenbank dar.  Unterstützt die *Statusvariable*, *die Genauigkeit* und die `scale`\-Parameter.|  
|[COLUMN\_ENTRY\_STATUS](../../data/oledb/column-entry-status.md)|Stellt eine Bindung zur spezifischen Spalte in der Datenbank dar.  Unterstützt die *Status* variable.|  
|[COLUMN\_ENTRY\_TYPE](../../data/oledb/column-entry-type.md)|Stellt eine Bindung zu einer bestimmten Spalte in der Datenbank dar.  Unterstützt `type`\-Parameter.|  
|[COLUMN\_ENTRY\_TYPE\_SIZE](../../data/oledb/column-entry-type-size.md)|Stellt eine Bindung zur spezifischen Spalte in der Datenbank dar.  Unterstützung Parameter `type` und `size`.|  
|[COLUMN\_NAME](../../data/oledb/column-name.md)|Stellt eine Bindung zu einer bestimmten Spalte in der Datenbank über dar.|  
|[COLUMN\_NAME\_EX](../../data/oledb/column-name-ex.md)|Stellt eine Bindung zu einer bestimmten Spalte in der Datenbank über dar.  Unterstützt Spezifikation des Datentyps, der Größe, einer Genauigkeit, Umfang, der Spaltenlänge und des Spaltenstatus.|  
|[COLUMN\_NAME\_LENGTH](../../data/oledb/column-name-length.md)|Stellt eine Bindung zu einer bestimmten Spalte in der Datenbank über dar.  Unterstützt Spezifikation die Spaltenlänge.|  
|[COLUMN\_NAME\_LENGTH\_STATUS](../../data/oledb/column-name-length-status.md)|Stellt eine Bindung zu einer bestimmten Spalte in der Datenbank über dar.  Unterstützt Spezifikation der Spaltenlänge und \-Status.|  
|[COLUMN\_NAME\_PS](../../data/oledb/column-name-ps.md)|Stellt eine Bindung zu einer bestimmten Spalte in der Datenbank über dar.  Unterstützt Spezifikation von Genauigkeit und Umfang.|  
|[COLUMN\_NAME\_PS\_LENGTH](../../data/oledb/column-name-ps-length.md)|Stellt eine Bindung zu einer bestimmten Spalte in der Datenbank über dar.  Unterstützt Spezifikation von Genauigkeit, der Skalierung und die Spaltenlänge.|  
|[COLUMN\_NAME\_PS\_LENGTH\_STATUS](../../data/oledb/column-name-ps-length-status.md)|Stellt eine Bindung zu einer bestimmten Spalte in der Datenbank über dar.  Unterstützt Spezifikation von Genauigkeit, Umfang, der Spaltenlänge und des Spaltenstatus.|  
|[COLUMN\_NAME\_PS\_STATUS](../../data/oledb/column-name-ps-status.md)|Stellt eine Bindung zu einer bestimmten Spalte in der Datenbank über dar.  Unterstützt Spezifikation von Genauigkeit, der Skalierung und des Spaltenstatus.|  
|[COLUMN\_NAME\_STATUS](../../data/oledb/column-name-status.md)|Stellt eine Bindung zu einer bestimmten Spalte in der Datenbank über dar.  Unterstützt Spezifikation des Spaltenstatus.|  
|[COLUMN\_NAME\_TYPE](../../data/oledb/column-name-type.md)|Stellt eine Bindung zu einer bestimmten Spalte in der Datenbank über dar.  Unterstützt Spezifikation des Datentyps.|  
|[COLUMN\_NAME\_TYPE\_PS](../../data/oledb/column-name-type-ps.md)|Stellt eine Bindung zu einer bestimmten Spalte in der Datenbank über dar.  Unterstützt Spezifikation des Datentyps, von Genauigkeit und Umfang.|  
|[COLUMN\_NAME\_TYPE\_SIZE](../../data/oledb/column-name-type-size.md)|Stellt eine Bindung zu einer bestimmten Spalte in der Datenbank über dar.  Unterstützt Spezifikation des Datentyps und Größe.|  
|[COLUMN\_NAME\_TYPE\_STATUS](../../data/oledb/column-name-type-status.md)|Stellt eine Bindung zu einer bestimmten Spalte in der Datenbank über dar.  Unterstützt Spezifikation des Datentyp\- und Spaltenstatus.|  
|[END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)|Markiert das Ende der Spaltenzuordnungseinträge.|  
  
### Befehls\-Makros  
  
|||  
|-|-|  
|[DEFINE\_COMMAND](../../data/oledb/define-command.md)|Gibt den Befehl an, der verwendet wird, um das Rowset zu erstellen, wenn die [CCommand](../../data/oledb/ccommand-class.md)\-Klasse verwendet.  Akzeptiert die nur Zeichenfolgentypen, die den angegebenen Anwendungstyp übereinstimmen \(ANSI oder Unicode\).  Es wird empfohlen, dass Sie [DEFINE\_COMMAND\_EX](../../data/oledb/define-command-ex.md) anstelle von `DEFINE_COMMAND` verwenden.|  
|[DEFINE\_COMMAND\_EX](../../data/oledb/define-command-ex.md)|Gibt den Befehl an, der verwendet wird, um das Rowset zu erstellen, wenn die [CCommand](../../data/oledb/ccommand-class.md)\-Klasse verwendet.  Anwendungen der Unterstützungs\- ANSI und Unicode\-.|  
  
### Parameter\-Zuordnungs\-Makros  
  
|||  
|-|-|  
|[BEGIN\_PARAM\_MAP](../../data/oledb/begin-param-map.md)|Markiert den Beginn der Parameterzuordnungseinträge in der Benutzerdatensatz\-Klasse.|  
|[END\_PARAM\_MAP](../../data/oledb/end-param-map.md)|Markiert das Ende der Parameterzuordnungseinträge.|  
|[SET\_PARAM\_TYPE](../../data/oledb/set-param-type.md)|Gibt `COLUMN_ENTRY`\-Makros, die das `SET_PARAM_TYPE`\-Makro ausführen, als Eingabe, Ausgabe oder Eingabe\/Ausgabe an.|  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)