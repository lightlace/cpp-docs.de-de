---
title: Accessoren und Rowsets | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- accessors [C++]
- OLE DB consumer templates, rowset support
- OLE DB consumer templates, accessors
- rowsets [C++], accessing
- bulk rowsets
- CAccessorRowset class, accessor types
- single rowsets
- CArrayRowset class, accessors
- CBulkRowset class, accessors
- array rowsets
- CAccessorBase class
- CRowset class, accessors and rowsets
- accessors [C++], rowsets
- rowsets [C++], supported types
ms.assetid: edc9c8b3-1a2d-4c2d-869f-7e058c631042
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cf47597ac38ae2944fc41bd686552e5d15c96b39
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="accessors-and-rowsets"></a>Accessoren und Rowsets
Zum Festlegen und Abrufen von Daten, OLE DB-Vorlagen verwenden, einen Accessor und ein Rowset über die [CAccessorRowset](../../data/oledb/caccessorrowset-class.md) Klasse. Diese Klasse kann mehrere verschiedene Accessoren behandeln.  
  
## <a name="accessor-types"></a>Accessortypen  
 Alle Accessoren abgeleitet [CAccessorBase](../../data/oledb/caccessorbase-class.md). `CAccessorBase`Stellt Parameter und spaltenbindung bereit.  
  
 Die folgende Abbildung zeigt die zugriffsmethodentypen.  
  
 ![Accessortypen](../../data/oledb/media/vcaccessortypes.gif "Vcaccessortypes")  
Accessorklassen  
  
-   [CAccessor](../../data/oledb/caccessor-class.md) verwenden Sie diesen Accessor, wenn Sie die Struktur der Datenbankquelle zur Entwurfszeit bekannt. `CAccessor`statisch bindet ein Datenbankeintrag, der den Puffer enthält, an die Datenquelle.  
  
-   [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) verwenden Sie diesen Accessor, wenn Sie nicht über die Struktur der Datenbank zur Entwurfszeit kennen. `CDynamicAccessor`Aufrufe `IColumnsInfo::GetColumnInfo` auf die Datenbank-Spalteninformationen abgerufen werden. Es erstellt und verwaltet einen Accessor und den Puffer.  
  
-   [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) verwenden Sie diesen Accessor, um unbekannte Befehlstypen zu behandeln. Wenn Sie die Befehle vorbereiten `CDynamicParameterAccessor` erhalten Parameterinformationen aus der `ICommandWithParameters` -Schnittstelle ein, wenn der Anbieter unterstützt `ICommandWithParameters`.  
  
-   [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md), [CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md), und [CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md) verwenden Sie diese Klassen, wenn Sie keine Kenntnisse des Datenbankschemas verfügen. `CDynamicStringAccessorA`Ruft die Daten als ANSI-Zeichenfolgen ab. `CDynamicStringAccessorW` Ruft Daten als Unicode-Zeichenfolgen ab.  
  
-   [CManualAccessor](../../data/oledb/cmanualaccessor-class.md) mit dieser Klasse können Sie beliebige Datentypen soll, wenn der Anbieter den Typ konvertieren kann. Er verarbeitet die Ergebnisspalten und Befehlsparameter.  
  
 In der folgenden Tabelle werden die Unterstützung in den OLE DB-Vorlagen Accessortypen zusammengefasst.  
  
|Accessortypen|Dynamic|Handles params|Puffer|Mehrere Accessoren|  
|-------------------|-------------|--------------------|------------|------------------------|  
|`CAccessor`|Nein|Ja|Benutzer|Ja|  
|`CDynamicAccessor`|Ja|Nein|OLE DB-Vorlagen|Nein|  
|`CDynamicParameterAccessor`|Ja|Ja|OLE DB-Vorlagen|Nein|  
|`CDynamicStringAccessor[A,W]`|Ja|Nein|OLE DB-Vorlagen|Nein|  
|`CManualAccessor`|Ja|Ja|Benutzer|Ja|  
  
## <a name="rowset-types"></a>Rowsettypen  
 Der OLE DB-Vorlagen unterstützen drei Arten von Rowsets (finden Sie in der obigen Abbildung): einzelne Rowsets (implementiert [CRowset](../../data/oledb/crowset-class.md)), Massenkopieren von Rowsets (implementiert [CBulkRowset](../../data/oledb/cbulkrowset-class.md)), und array-Rowsets (implementiert durch [CArrayRowset](../../data/oledb/carrayrowset-class.md)). Einzelne Rowsets Fetch, die eine einzelne Zeile verarbeiten, wenn `MoveNext` aufgerufen wird. Sammel-Rowsets können mehrere Zeilenhandles abgerufen werden. Arrayrowsets sind Rowsets, die über die Array-Syntax zugegriffen werden kann.  
  
 Die folgende Abbildung zeigt die Rowsettypen.  
  
 ![Grafik zu RowsetType](../../data/oledb/media/vcrowsettypes.gif "Vcrowsettypes")  
Schemarowset-Klassen  
  
 [Schemarowsets](../../data/oledb/obtaining-metadata-with-schema-rowsets.md) müssen nicht über die Access-Daten in den Daten speichern, sondern auf Informationen über den Datenspeicher, die als Metadaten bezeichnet wird. Schemarowsets werden in der Regel in Situationen verwendet, in denen Struktur der Datenbank zum Zeitpunkt der Kompilierung nicht bekannt ist und zur Laufzeit abgerufen werden muss.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)