---
title: "Makros und globale Funktionen für OLE DB-Consumervorlagen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.templates.ole
dev_langs: C++
helpviewer_keywords:
- OLE DB consumer templates, macros
- macros, OLE DB consumer template
ms.assetid: 8765eb7b-32dd-407c-bacf-8890ef959837
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4c095c643f54ee81124a736b0eaa65628cbd23ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="macros-and-global-functions-for-ole-db-consumer-templates"></a>Makros und globale Funktionen für OLE-Consumervorlagen
Der OLE DB-Consumervorlagen umfassen die folgenden Makros und globale Funktionen:  
  
### <a name="global-functions"></a>Globale Funktionen  
  
|||  
|-|-|  
|[AtlTraceErrorRecords](../../data/oledb/atltraceerrorrecords.md)|Sichert OLE DB-Fehlerdatensatz Informationen auf dem Sicherungsmedium aus, wenn ein Fehler zurückgegeben wird.|  
  
### <a name="accessor-map-macros"></a>Accessor Ereigniszuordnungs-Makros  
  
|||  
|-|-|  
|[BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)|Markiert den Beginn eines Eintrags Accessor.|  
|[BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)|Markiert den Beginn der Accessor-Zuordnungseinträge.|  
|[END_ACCESSOR](../../data/oledb/end-accessor.md)|Markiert das Ende eines Eintrags Accessor.|  
|[END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)|Markiert das Ende der Accessor-Zuordnungseinträge.|  
  
### <a name="column-map-macros"></a>Spalte Ereigniszuordnungs-Makros  
  
|||  
|-|-|  
|[BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)|Markiert den Beginn der Zuordnungseinträge Spalte in die Benutzerdatensatz-Klasse.|  
|[BLOB_ENTRY](../../data/oledb/blob-entry.md)|Wird verwendet, um ein binary large Object (BLOB) zu binden.|  
|[BLOB_ENTRY_LENGTH](../../data/oledb/blob-entry-length.md)|Gibt die Länge der BLOB-Spalte.|  
|[BLOB_ENTRY_LENGTH_STATUS](../../data/oledb/blob-entry-length-status.md)|Gibt die Länge und den Status der BLOB-Spalte.|  
|[BLOB_ENTRY_STATUS](../../data/oledb/blob-entry-status.md)|Meldet den Status der BLOB-Spalte.|  
|[BLOB_NAME](../../data/oledb/blob-name.md)|Wird verwendet, um ein binary large Object anhand des Spaltennamens zu binden.|  
|[BLOB_NAME_LENGTH](../../data/oledb/blob-name-length.md)|Gibt die Länge der BLOB-Spalte.|  
|[BLOB_NAME_LENGTH_STATUS](../../data/oledb/blob-name-length-status.md)|Gibt die Länge und den Status der BLOB-Spalte.|  
|[BLOB_NAME_STATUS](../../data/oledb/blob-name-status.md)|Meldet den Status der BLOB-Spalte.|  
|[BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md)|Stellt einen Lesezeicheneintrag für das Rowset an. Ein Lesezeicheneintrag ist eine besondere Art von Eintrag in der Spalte.|  
|[COLUMN_ENTRY](../../data/oledb/column-entry.md)|Stellt eine Bindung zu einer bestimmten Spalte in der Datenbank dar.|  
|[COLUMN_ENTRY_EX](../../data/oledb/column-entry-ex.md)|Stellt eine Bindung an die spezifische Spalte in der Datenbank dar. Unterstützt `type`, *Länge*, *Genauigkeit*, `scale`, und *Status* Parameter.|  
|[COLUMN_ENTRY_LENGTH](../../data/oledb/column-entry-length.md)|Stellt eine Bindung an die spezifische Spalte in der Datenbank dar. Unterstützt die *Länge* Variable.|  
|[COLUMN_ENTRY_LENGTH_STATUS](../../data/oledb/column-entry-length-status.md)|Stellt eine Bindung an die spezifische Spalte in der Datenbank dar. Unterstützt *Status* und *Länge* Parameter.|  
|[COLUMN_ENTRY_PS](../../data/oledb/column-entry-ps.md)|Stellt eine Bindung an die spezifische Spalte in der Datenbank dar. Unterstützt *Genauigkeit* und `scale` Parameter.|  
|[COLUMN_ENTRY_PS_LENGTH](../../data/oledb/column-entry-ps-length.md)|Stellt eine Bindung an die spezifische Spalte in der Datenbank dar. Unterstützt die *Länge* Variable *Genauigkeit* und `scale` Parameter.|  
|[COLUMN_ENTRY_PS_LENGTH_STATUS](../../data/oledb/column-entry-ps-length-status.md)|Stellt eine Bindung an die spezifische Spalte in der Datenbank dar. Unterstützt *Status* und *Länge* Variablen *Genauigkeit* und `scale` Parameter.|  
|[COLUMN_ENTRY_PS_STATUS](../../data/oledb/column-entry-ps-status.md)|Stellt eine Bindung an die spezifische Spalte in der Datenbank dar. Unterstützt die *Status* Variable *Genauigkeit* und `scale` Parameter.|  
|[COLUMN_ENTRY_STATUS](../../data/oledb/column-entry-status.md)|Stellt eine Bindung an die spezifische Spalte in der Datenbank dar. Unterstützt die *Status* Variable.|  
|[COLUMN_ENTRY_TYPE](../../data/oledb/column-entry-type.md)|Stellt eine Bindung zu einer bestimmten Spalte in der Datenbank dar. Unterstützt `type` Parameter.|  
|[COLUMN_ENTRY_TYPE_SIZE](../../data/oledb/column-entry-type-size.md)|Stellt eine Bindung an die spezifische Spalte in der Datenbank dar. Unterstützt `type` und `size` Parameter.|  
|[COLUMN_NAME](../../data/oledb/column-name.md)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Namen dar.|  
|[COLUMN_NAME_EX](../../data/oledb/column-name-ex.md)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Namen dar. Unterstützt die Spezifikation von Datentyp, Größe, Genauigkeit, Dezimalstellen, Spaltenlänge und Status in der Spalte.|  
|[COLUMN_NAME_LENGTH](../../data/oledb/column-name-length.md)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Namen dar. Unterstützt die Angabe der Spaltenlänge.|  
|[COLUMN_NAME_LENGTH_STATUS](../../data/oledb/column-name-length-status.md)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Namen dar. Unterstützt die Spezifikation der Spaltenlänge und Status.|  
|[COLUMN_NAME_PS](../../data/oledb/column-name-ps.md)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Namen dar. Unterstützt die Spezifikation von Genauigkeit und festen Dezimalstellen.|  
|[COLUMN_NAME_PS_LENGTH](../../data/oledb/column-name-ps-length.md)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Namen dar. Unterstützt die Spezifikation Länge, Genauigkeit, Dezimalstellen und Spalte.|  
|[COLUMN_NAME_PS_LENGTH_STATUS](../../data/oledb/column-name-ps-length-status.md)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Namen dar. Unterstützt die Spezifikation von Genauigkeit, Dezimalstellen, Spaltenlänge und Status in der Spalte.|  
|[COLUMN_NAME_PS_STATUS](../../data/oledb/column-name-ps-status.md)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Namen dar. Unterstützt die Spezifikation von Genauigkeit, Dezimalstellen und die Spalte Status.|  
|[COLUMN_NAME_STATUS](../../data/oledb/column-name-status.md)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Namen dar. Unterstützt die Angabe der Spalte Status.|  
|[COLUMN_NAME_TYPE](../../data/oledb/column-name-type.md)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Namen dar. Unterstützt die Angabe des Datentyps.|  
|[COLUMN_NAME_TYPE_PS](../../data/oledb/column-name-type-ps.md)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Namen dar. Unterstützt die Spezifikation von Datentyp, Genauigkeit und Dezimalstellen.|  
|[COLUMN_NAME_TYPE_SIZE](../../data/oledb/column-name-type-size.md)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Namen dar. Unterstützt die Spezifikation von Datentyp und Größe.|  
|[COLUMN_NAME_TYPE_STATUS](../../data/oledb/column-name-type-status.md)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Namen dar. Unterstützt die Angabe von Typ und die Spalte Status von Daten.|  
|[END_COLUMN_MAP](../../data/oledb/end-column-map.md)|Markiert das Ende der Spalte-Zuordnungseinträge.|  
  
### <a name="command-macros"></a>Befehlsmakros  
  
|||  
|-|-|  
|[DEFINE_COMMAND](../../data/oledb/define-command.md)|Gibt den Befehl an, der verwendet wird, um das Rowset zu erstellen, bei Verwendung der [CCommand](../../data/oledb/ccommand-class.md) Klasse. Akzeptiert nur Zeichenfolgen-Datentypen, die den angegebenen Anwendungstyp (ANSI oder Unicode) entsprechen. Es wird empfohlen, die Verwendung von [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) anstelle von `DEFINE_COMMAND`.|  
|[DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md)|Gibt den Befehl an, der verwendet wird, um das Rowset zu erstellen, bei Verwendung der [CCommand](../../data/oledb/ccommand-class.md) Klasse. Unterstützt ANSI- und Unicode-Anwendungen.|  
  
### <a name="parameter-map-macros"></a>Parameter-Zuordnungsmakros  
  
|||  
|-|-|  
|[BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md)|Markiert den Beginn der Parameter-Zuordnungseinträge in die Benutzerdatensatz-Klasse.|  
|[END_PARAM_MAP](../../data/oledb/end-param-map.md)|Markiert das Ende der Parameter-Zuordnungseinträge.|  
|[SET_PARAM_TYPE](../../data/oledb/set-param-type.md)|Gibt an, `COLUMN_ENTRY` Makros, die Folgen der `SET_PARAM_TYPE` Makro als Eingabe-, Ausgabe- oder Eingabe-/Ausgabe.|  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)