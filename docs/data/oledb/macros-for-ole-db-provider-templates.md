---
title: "Makros für OLE DB-Anbietervorlagen | Microsoft Docs"
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
- OLE DB provider templates, macros
- macros, OLE DB Provider Templates
- Provider Template macros (OLE DB)
- OLE DB Provider Template macros
ms.assetid: 909482c5-64ab-4e52-84a9-1c07091db183
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 11a5ae3d0ba5c3da517a380adf795e579d0dce51
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="macros-for-ole-db-provider-templates"></a>Makros für OLE DB-Anbietervorlagen
Die Makros für OLE DB-Vorlagen Anbieter bieten Funktionen in den folgenden Kategorien:  
  
### <a name="property-set-map-macros"></a>Eigenschaftensatz Ereigniszuordnungs-Makros  
  
|||  
|-|-|  
|[BEGIN_PROPERTY_SET](../../data/oledb/begin-property-set.md)|Markiert den Beginn einer Eigenschaftensatz.|  
|[BEGIN_PROPERTY_SET_EX](../../data/oledb/begin-property-set-ex.md)|Markiert den Beginn einer Eigenschaftensatz.|  
|[BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)|Markiert, die der Anfang einer Eigenschaft, die festlegen, können ausgeblendet oder außerhalb des Bereichs des Anbieters definiert werden.|  
|[CHAIN_PROPERTY_SET](../../data/oledb/chain-property-set.md)|Ketten-Eigenschaftengruppen zusammen.|  
|[END_PROPERTY_SET](../../data/oledb/end-property-set.md)|Markiert das Ende eines Satzes Eigenschaft.|  
|[END_PROPSET_MAP](../../data/oledb/end-propset-map.md)|Markiert das Ende einer Zuordnung der Eigenschaft festlegen.|  
|[PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md)|Legt eine bestimmte Eigenschaft in einer Eigenschaft auf einen Standardwert festgelegt.|  
|[PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md)|Legt eine bestimmte Eigenschaft in einer Eigenschaft, die auf einen von Ihnen angegebenen Wert festgelegt. Außerdem können Sie Optionen und Flags festgelegt.|  
|[PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md)|Legt eine bestimmte Eigenschaft in einer Eigenschaft, die auf einen von Ihnen angegebenen Wert festgelegt.|  
  
### <a name="column-map-macros"></a>Spalte Ereigniszuordnungs-Makros  
  
|||  
|-|-|  
|[BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md)|Markiert den Beginn der Anbieter Spalte-Zuordnungseinträge.|  
|[END_PROVIDER_COLUMN_MAP](../../data/oledb/end-provider-column-map.md)|Markiert das Ende der Anbieter Spalte-Zuordnungseinträge.|  
|[PROVIDER_COLUMN_ENTRY](../../data/oledb/provider-column-entry.md)|Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden.|  
|[PROVIDER_COLUMN_ENTRY_GN](../../data/oledb/provider-column-entry-gn.md)|Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden. Sie können der Spaltenwerts Größe, Datentyp, Genauigkeit, Dezimalstellen und Schemarowset-GUID angeben.|  
|[PROVIDER_COLUMN_ENTRY_FIXED](../../data/oledb/provider-column-entry-fixed.md)|Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden. Sie können den Datentyp der Spalte angeben.|  
|[PROVIDER_COLUMN_ENTRY_LENGTH](../../data/oledb/provider-column-entry-length.md)|Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden. Sie können die Größe der Spalte angeben.|  
|[PROVIDER_COLUMN_ENTRY_STR](../../data/oledb/provider-column-entry-str.md)|Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden. Es wird davon ausgegangen, dass der Spaltentyp eine Zeichenfolge ist.|  
|[PROVIDER_COLUMN_ENTRY_TYPE_LENGTH](../../data/oledb/provider-column-entry-type-length.md)|Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden. Wie Sie PROVIDER_COLUMN_ENTRY_LENGTH, doch auch ermöglicht Ihnen das Festlegen der Datentyp der Spalte sowie der Größe.|  
|[PROVIDER_COLUMN_ENTRY_WSTR](../../data/oledb/provider-column-entry-wstr.md)|Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden. Es wird davon ausgegangen, dass der Spaltentyp eine Unicode-Zeichenfolge ist.|  
  
### <a name="schema-rowset-macros"></a>Schema-Rowset-Makros  
  
|||  
|-|-|  
|[BEGIN_SCHEMA_MAP](../../data/oledb/begin-schema-map.md)|Markiert den Beginn einer Schema-Zuordnung.|  
|[SCHEMA_ENTRY](../../data/oledb/schema-entry.md)|Ordnet eine GUID mit einer Klasse.|  
|[END_SCHEMA_MAP](../../data/oledb/end-schema-map.md)|Markiert das Ende einer Zuordnung Schema.|  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)   
 [Referenz der OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-reference.md)