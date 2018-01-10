---
title: TypeDef, Enum, Union- und Struct-Attribute | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- union attributes
- attributes [C++], reference topics
- struct attributes
- typedef attributes
- enum attributes
ms.assetid: f8a4fe94-dc02-4aed-bc31-3e500d42f4c7
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2087d4ff4e4905324f9bbdfaa954287f033feafe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="typedef-enum-union-and-struct-attributes"></a>typedef-, enum-, union- und struct-Attribute
Die folgenden Attribute gelten für die [Typedef](http://msdn.microsoft.com/en-us/cc96cf26-ba93-4179-951e-695d1f5fdcf1), [Struktur](../cpp/struct-cpp.md), und [Enum](../cpp/enumerations-cpp.md) C++-Schlüsselwörter.  
  
### <a name="typedef"></a>Typedef  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|[case](../windows/case-cpp.md)|Verwendet die [Switch_type](../windows/switch-type.md) Attribut in einer **Union**.|  
|[benutzerdefinierte](../windows/custom-cpp.md)|Sie können Ihr eigenes Attribut definieren.|  
|[export](../windows/export.md)|Bewirkt, dass eine Datenstruktur, in der IDL-Datei abgelegt werden soll.|  
|[first_is](../windows/first-is.md)|Gibt den Index des ersten Arrayelements übermittelt werden sollen.|  
|[helpcontext](../windows/helpcontext.md)|Gibt eine Kontext-ID, mit dem die Benutzerinformationen zu diesem Element in der Hilfedatei.|  
|[helpfile](../windows/helpfile.md)|Legt den Namen der Hilfedatei für eine Typbibliothek.|  
|[helpstring](../windows/helpstring.md)|Gibt eine Zeichenfolge, die verwendet wird, um das Element zu beschreiben, auf dem es angewendet.|  
|[library_block](../windows/library-block.md)|Fügt ein Konstrukt in der IDL-Datei bibliotheksblock vor.|  
|[ptr](../windows/ptr.md)|Kennzeichnet einen Zeiger als vollständige Zeiger.|  
|[public](../windows/public-cpp-attributes.md)|Stellt sicher, dass eine Typdefinition in der Typbibliothek aufgenommen werden, auch wenn es nicht von innerhalb der IDL-Datei verwiesen wird.|  
|[ref](../windows/ref-cpp.md)|Identifiziert einen Verweiszeiger an.|  
|[switch_is](../windows/switch-is.md)|Gibt den Ausdruck oder einen Bezeichner fungiert als die union kombiniert werden sollen, die den union-Member auswählt.|  
|[switch_type](../windows/switch-type.md)|Identifiziert den Typ der Variablen als die union Discriminant verwendet.|  
|[unique](../windows/unique-cpp.md)|Gibt einen eindeutigen Zeiger.|  
|[wire_marshal](../windows/wire-marshal.md)|Gibt einen Datentyp, der für die Übertragung anstelle eines Typs programmspezifische Daten verwendet wird.|  
  
### <a name="enum"></a>enum  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|[benutzerdefinierte](../windows/custom-cpp.md)|Sie können Ihr eigenes Attribut definieren.|  
|[export](../windows/export.md)|Bewirkt, dass eine Datenstruktur, in der IDL-Datei abgelegt werden soll.|  
|[UUID](../windows/uuid-cpp-attributes.md)|Gibt die eindeutige ID für eine Klasse oder Schnittstelle an.|  
|[v1_enum](../windows/v1-enum.md)|Weist der angegebene enumerierten Typ als eine 32-Bit-Entität, anstatt die 16-Bit-Standardeinstellung übertragen werden.|  
  
### <a name="union"></a>union  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|[benutzerdefinierte](../windows/custom-cpp.md)|Sie können Ihr eigenes Attribut definieren.|  
|[export](../windows/export.md)|Bewirkt, dass eine Datenstruktur, in der IDL-Datei abgelegt werden soll.|  
|[first_is](../windows/first-is.md)|Gibt den Index des ersten Arrayelements übermittelt werden sollen.|  
|[last_is](../windows/last-is.md)|Gibt den Index des letzten Arrayelements übermittelt werden sollen.|  
|[length_is](../windows/length-is.md)|Gibt die Anzahl von Arrayelementen übermittelt werden sollen.|  
|[max_is](../windows/max-is.md)|Legt fest, den maximalen Wert für eine gültige Arrayindex.|  
|[size_is](../windows/size-is.md)|Gibt die Größe des Arbeitsspeichers für Größe Zeiger belegt, Größe von Zeigern auf großen Zeiger und Einzel- oder mehrdimensionale Arrays.|  
|[unique](../windows/unique-cpp.md)|Gibt einen eindeutigen Zeiger.|  
|[UUID](../windows/uuid-cpp-attributes.md)|Gibt die eindeutige ID für eine Klasse oder Schnittstelle an.|  
  
### <a name="nonencapsulated-union"></a>Nonencapsulated union  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|[ms_union](../windows/ms-union.md)|Steuert die Netzwerk-datenausrichtung Darstellung nonencapsulated Unions.|  
|[no_injected_text](../windows/no-injected-text.md)|Verhindert, dass den Compiler Code aufgrund der Verwendung des Attributs injiziert.|  
  
### <a name="struct"></a>struct  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|[Aggregierbar](../windows/aggregatable.md)|Gibt an, dass die Klasse Aggregation unterstützt.|  
|[Aggregate](../windows/aggregates.md)|Gibt an, dass ein Steuerelement die Zielklasse aggregiert.|  
|[appobject](../windows/appobject.md)|Identifiziert die Co-Klasse als ein Anwendungsobjekt, die mit einer vollständigen .exe-Anwendung verknüpft ist, und gibt an, dass die Funktionen und Eigenschaften der Co-Klasse in diese Typbibliothek global verfügbar sind.|  
|[coclass](../windows/coclass.md)|Erstellt ein ActiveX-Steuerelement.|  
|[COM_INTERFACE_ENTRY](../windows/com-interface-entry-cpp.md)|Fügt einen Eintrag für die Schnittstelle zu einer COM-Zuordnung.|  
|[Steuerelement](../windows/control.md)|Gibt an, dass der benutzerdefinierte Datentyp eines Steuerelements.|  
|[benutzerdefinierte](../windows/custom-cpp.md)|Sie können Ihr eigenes Attribut definieren.|  
|[db_column](../windows/db-column.md)|Bindet eine angegebene Spalte auf das Rowset an.|  
|[db_command](../windows/db-command.md)|Erstellt einen OLE DB-Befehl.|  
|[db_param](../windows/db-param.md)|Ordnet die angegebene Membervariable ein Eingabe- oder Ausgabespalte-Parameter und begrenzt die Variable.|  
|[db_source](../windows/db-source.md)|Erstellt eine Verbindung mit einer Datenquelle.|  
|[db_table](../windows/db-table.md)|Öffnet eine OLE DB-Tabelle.|  
|[default](../windows/default-cpp.md)|Gibt an, dass die benutzerdefinierte Schnittstelle oder Disp-Schnittstelle innerhalb einer Co-Klasse die Standard-Programmierschnittstelle darstellt.|  
|[defaultvtable](../windows/defaultvtable.md)|Definiert eine Schnittstelle als die Vtable Standardschnittstelle für ein Steuerelement an.|  
|[event_receiver](../windows/event-receiver.md)|Erstellt einen Ereignisempfänger.|  
|[event_source](../windows/event-source.md)|Erstellt eine Ereignisquelle.|  
|[export](../windows/export.md)|Bewirkt, dass eine Datenstruktur, in der IDL-Datei abgelegt werden soll.|  
|[first_is](../windows/first-is.md)|Gibt den Index des ersten Arrayelements übermittelt werden sollen.|  
|[hidden](../windows/hidden.md)|Gibt an, dass das Element vorhanden ist, aber nicht in einem Browser benutzerorientierte angezeigt werden soll.|  
|[implements_category](../windows/implements-category.md)|Gibt an, für die Klasse implementierten Komponentenkategorien.|  
|[last_is](../windows/last-is.md)|Gibt den Index des letzten Arrayelements übermittelt werden sollen.|  
|[length_is](../windows/length-is.md)|Gibt die Anzahl von Arrayelementen übermittelt werden sollen.|  
|[max_is](../windows/max-is.md)|Legt fest, den maximalen Wert für eine gültige Arrayindex.|  
|[requires_category](../windows/requires-category.md)|Gibt die erforderliche Komponentenkategorien der Zielklasse an.|  
|[size_is](../windows/size-is.md)|Gibt die Größe des Arbeitsspeichers für Größe Zeiger belegt, Größe von Zeigern auf großen Zeiger und Einzel- oder mehrdimensionale Arrays.|  
|[Datenquelle](../windows/source-cpp.md)|Für eine Klasse gibt Schnittstellen für Verbindungspunkte der COM-Objekt. Auf eine Eigenschaft oder Methode gibt Sie an, dass das Element zurückgibt, ein Objekt oder eine Variante, die Quelle von Ereignissen ist.|  
|[Threading](../windows/threading-cpp.md)|Gibt das Threadingmodell für ein COM-Objekt.|  
|[unique](../windows/unique-cpp.md)|Gibt einen eindeutigen Zeiger.|  
|[UUID](../windows/uuid-cpp-attributes.md)|Gibt die eindeutige ID für eine Klasse oder Schnittstelle an.|  
|[version](../windows/version-cpp.md)|Identifiziert eine bestimmte Version mehrere Versionen einer Klasse.|  
|[vi_progid](../windows/vi-progid.md)|Gibt eine versionsunabhängige Form der ProgID an.|  
  
## <a name="see-also"></a>Siehe auch  
 [Attribute nach Verwendung](../windows/attributes-by-usage.md)