---
title: Accessoren und Rowsets
ms.date: 11/19/2018
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
ms.openlocfilehash: d29c409f2ed410d9f697419e9a98b675eee7a69d
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175712"
---
# <a name="accessors-and-rowsets"></a>Accessoren und Rowsets

OLE DB-Vorlagen zum Festlegen und Abrufen von Daten, verwenden Sie einen Accessor und ein Rowset über die [CAccessorRowset](../../data/oledb/caccessorrowset-class.md) Klasse. Diese Klasse kann mehrere Accessoren verschiedener Typen verarbeiten.

## <a name="accessor-types"></a>Zugriffsmethodentypen

Alle Accessoren werden von [CAccessorBase](../../data/oledb/caccessorbase-class.md). `CAccessorBase` Stellt Parameter und spaltenbindung.

Die folgende Abbildung zeigt die Accessortypen.

![Zugriffsmethodentypen](../../data/oledb/media/vcaccessortypes.gif "zugriffsmethodentypen")<br/>
Accessorklassen

- [CAccessor](../../data/oledb/caccessor-class.md) verwenden Sie diesen Accessor, wenn Sie die Struktur der Datenbankquelle zur Entwurfszeit bekannt. `CAccessor` statisch bindet ein Datenbankeintrag, die den Puffer enthält, mit der Datenquelle ein.

- [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) verwenden Sie diesen Accessor, wenn Sie nicht die Struktur der Datenbank zur Entwurfszeit kennen. `CDynamicAccessor` Aufrufe `IColumnsInfo::GetColumnInfo` auf die Datenbank-Spalteninformationen abgerufen. Es erstellt und verwaltet einen Accessor und den Puffer.

- [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) verwenden Sie diesen Accessor, um unbekannte Befehlstypen zu behandeln. Wenn Sie die Befehle, Vorbereiten `CDynamicParameterAccessor` erhalten Sie Informationen zu den Parametern aus der `ICommandWithParameters` Schnittstelle, wenn der Anbieter unterstützt `ICommandWithParameters`.

- [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md), [CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md), und [CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md) diese Klassen verwenden, wenn Sie keine Kenntnis des Schemas der Datenbank verfügen. `CDynamicStringAccessorA` Ruft Daten ab, als ANSI-Zeichenfolgen; `CDynamicStringAccessorW` Ruft Daten als Unicode-Zeichenfolgen ab.

- [CManualAccessor](../../data/oledb/cmanualaccessor-class.md) mit dieser Klasse können Sie, dass die Datentypen, die Sie möchten, dass der Anbieter den Typ konvertieren kann. Er behandelt sowohl die Ergebnisspalten als auch die Parameter des Befehls.

Die folgende Tabelle enthält die Unterstützung in den OLE DB-Vorlagen-Accessor-Typen.

|Accessortyp|Dynamic|Params behandelt|Puffer|Mehrere Zugriffsmethoden|
|-------------------|-------------|--------------------|------------|------------------------|
|`CAccessor`|Nein|Ja|Benutzer|Ja|
|`CDynamicAccessor`|Ja|Nein|OLE DB-Vorlagen|Nein|
|`CDynamicParameterAccessor`|Ja|Ja|OLE DB-Vorlagen|Nein|
|`CDynamicStringAccessor[A,W]`|Ja|Nein|OLE DB-Vorlagen|Nein|
|`CManualAccessor`|Ja|Ja|Benutzer|Ja|

## <a name="rowset-types"></a>Rowsettypen

OLE DB-Vorlagen unterstützen drei Arten von Rowsets (siehe Abbildung oben): einzelne Rowsets (implementiert [CRowset](../../data/oledb/crowset-class.md)), Massenkopieren von Rowsets (implementiert [CBulkRowset](../../data/oledb/cbulkrowset-class.md)), und die array-Rowsets (implementiert durch [CArrayRowset](../../data/oledb/carrayrowset-class.md)). Einzelne Rowsets abrufen, die eine einzelne Zeile behandelt, wenn `MoveNext` aufgerufen wird. Sammel-Rowsets können mehrere Zeilenhandles abzurufen. Array-Rowsets sind Rowsets, die über die Array-Syntax zugegriffen werden kann.

Die folgende Abbildung zeigt die Rowsettypen.

![Grafik zu RowsetType](../../data/oledb/media/vcrowsettypes.gif "Grafik zu RowsetType")<br/>
Schemarowset-Klassen

[Schemarowsets](../../data/oledb/obtaining-metadata-with-schema-rowsets.md) nicht den Zugriff auf Daten in den Daten zu speichern, sondern auf Informationen über den Datenspeicher, die als Metadaten bezeichnet. Schemarowsets werden in der Regel in Situationen verwendet, in denen die Struktur der Datenbank ist nicht zur Kompilierzeit bekannt und muss zur Laufzeit abgerufen werden.

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)