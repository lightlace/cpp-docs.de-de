---
title: "Accessoren und Rowsets"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Accessoren [C++]"
  - "Accessoren [C++], Rowsets"
  - "Array-Rowsets"
  - "Sammel-Rowsets"
  - "CAccessorBase-Klasse"
  - "CAccessorRowset-Klasse, Accessortypen"
  - "CArrayRowset-Klasse, Accessoren"
  - "CBulkRowset-Klasse, Accessoren"
  - "CRowset-Klasse, Accessoren und Rowsets"
  - "OLE DB-Consumervorlagen, Accessoren"
  - "OLE DB-Consumervorlagen, Rowset-Unterstützung"
  - "Rowsets [C++], Aufrufen"
  - "Rowsets [C++], Unterstützte Typen"
  - "Einzelne Rowsets"
ms.assetid: edc9c8b3-1a2d-4c2d-869f-7e058c631042
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Accessoren und Rowsets
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zum Festlegen und Abrufen von Daten verwenden die OLE DB\-Vorlagen einen Accessor und ein Rowset über die [CAccessorRowset](../../data/oledb/caccessorrowset-class.md)\-Klasse.  Diese Klasse kann mehrere verschiedene Accessoren behandeln.  
  
## Accessortypen  
 Alle Accessoren werden von [CAccessorBase](../../data/oledb/caccessorbase-class.md) abgeleitet.  `CAccessorBase` stellt sowohl Parameter\- als auch Spaltenbindung bereit.  
  
 Die folgende Abbildung zeigt die verschiedenen Accessortypen.  
  
 ![Accessortypen](../../data/oledb/media/vcaccessortypes.png "vcAccessorTypes")  
Accessorklassen  
  
-   [CAccessor](../../data/oledb/caccessor-class.md) Verwenden Sie diesen Accessor, wenn Ihnen die Struktur der Datenbankquelle zur Entwurfszeit bekannt ist.  `CAccessor` bindet den Datenbankdatensatz, der den Puffer enthält, statisch an die Datenquelle.  
  
-   [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) Verwenden Sie diesen Accessor, wenn Ihnen die Struktur der Datenbankquelle zur Entwurfszeit nicht bekannt ist.  `CDynamicAccessor` ruft `IColumnsInfo::GetColumnInfo` auf, um die Spalteninformationen für die Datenbank abzurufen.  Er erstellt und verwaltet einen Accessor und den Puffer.  
  
-   [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) Verwenden Sie diesen Accessor, um unbekannte Befehlstypen zu verarbeiten.  Während Sie die Befehle vorbereiten, kann `CDynamicParameterAccessor` Parameterinformationen von der `ICommandWithParameters`\-Schnittstelle beziehen, sofern der Anbieter `ICommandWithParameters` unterstützt.  
  
-   [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md), [CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md) und [CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md) Verwenden Sie diese Klassen, wenn Ihnen das Datenbankschema nicht bekannt ist.  `CDynamicStringAccessorA` empfängt Daten als ANSI\-Zeichenfolgen, und `CDynamicStringAccessorW` empfängt Daten als Unicode\-Zeichenfolgen.  
  
-   [CManualAccessor](../../data/oledb/cmanualaccessor-class.md) Mit dieser Klasse können Sie alle Datentypen verwenden, die der Anbieter konvertieren kann.  Sie verarbeitet sowohl Ergebnisspalten als auch Befehlsparameter.  
  
 In der folgenden Tabelle wird die Unterstützung in den OLE DB\-Vorlagenaccessortypen zusammengefasst.  
  
|Accessortyp|Dynamic|Parameterbehandlung|Puffer|Mehrere Accessoren|  
|-----------------|-------------|-------------------------|------------|------------------------|  
|`CAccessor`|nein|ja|Benutzer|ja|  
|`CDynamicAccessor`|ja|nein|OLE DB\-Vorlagen|nein|  
|`CDynamicParameterAccessor`|ja|ja|OLE DB\-Vorlagen|nein|  
|`CDynamicStringAccessor[A,W]`|ja|nein|OLE DB\-Vorlagen|nein|  
|`CManualAccessor`|ja|ja|Benutzer|ja|  
  
## Rowsettypen  
 Die OLE DB\-Vorlagen unterstützen drei Arten von Rowsets \(siehe Abbildung oben\): einzelne Rowsets \(implementiert durch [CRowset](../../data/oledb/crowset-class.md)\), Sammelrowsets \(implementiert durch [CBulkRowset](../../data/oledb/cbulkrowset-class.md)\) und Arrayrowsets \(implementiert durch [CArrayRowset](../../data/oledb/carrayrowset-class.md)\).  Einzelne Rowsets rufen ein einzelnes Zeilenhandle ab, wenn `MoveNext` aufgerufen wird.  Sammelrowsets können mehrere Zeilenhandles abrufen.  Bei Arrayrowsets handelt es sich um Rowsets, auf die mithilfe von Arraysyntax zugegriffen werden kann.  
  
 Die folgende Abbildung zeigt die verschiedenen Rowsettypen.  
  
 ![RowsetType&#45;Grafik](../../data/oledb/media/vcrowsettypes.png "vcRowsetTypes")  
Rowset\-Klassen  
  
 [Schemarowsets](../../data/oledb/obtaining-metadata-with-schema-rowsets.md) greifen nicht auf Daten im Datenspeicher, sondern auf Informationen über den Datenspeicher, so genannte *Metadaten*, zu.  Schemarowsets werden gewöhnlich in Situationen verwendet, in denen die Datenbankstruktur zum Zeitpunkt der Kompilierung nicht bekannt ist und zur Laufzeit ermittelt werden muss.  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)