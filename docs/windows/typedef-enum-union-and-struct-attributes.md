---
title: TypeDef, Enum, Union- und Struct-Attribute | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- union attributes
- attributes [C++], reference topics
- struct attributes
- typedef attributes
- enum attributes
ms.assetid: f8a4fe94-dc02-4aed-bc31-3e500d42f4c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2e4e8ad94e96c6bfc45102f1c970476c484d756f
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649122"
---
# <a name="typedef-enum-union-and-struct-attributes"></a>typedef-, enum-, union- und struct-Attribute
Die folgenden Attribute gelten für die [Typedef](http://msdn.microsoft.com/cc96cf26-ba93-4179-951e-695d1f5fdcf1), [Struktur](../cpp/struct-cpp.md), und [Enum](../cpp/enumerations-cpp.md) C++-Schlüsselwörter.  
  
### <a name="typedef"></a>Typedef  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|[case](../windows/case-cpp.md)|Verwendung der [Switch_type](../windows/switch-type.md) -Attribut in einer **Union**.|  
|[Benutzerdefinierte](../windows/custom-cpp.md)|Sie können Ihr eigenes Attribut definieren.|  
|[export](../windows/export.md)|Bewirkt, dass eine Datenstruktur, in der IDL-Datei platziert wird.|  
|[first_is](../windows/first-is.md)|Gibt den Index des ersten Arrayelements übertragen werden.|  
|[helpcontext](../windows/helpcontext.md)|Gibt eine Kontext-ID, mit dem die Benutzerinformationen zu diesem Element in der Hilfedatei.|  
|[helpfile](../windows/helpfile.md)|Legt den Namen der Hilfedatei für die Typbibliothek.|  
|[helpstring](../windows/helpstring.md)|Gibt eine Zeichenfolge an, die zum Beschreiben des Elements verwendet wird, auf das sie angewendet wird.|  
|[library_block](../windows/library-block.md)|Fügt ein Konstrukt in bibliotheksblock der IDL-Datei an.|  
|[ptr](../windows/ptr.md)|Kennzeichnet einen Zeiger als vollständige Zeiger.|  
|[public](../windows/public-cpp-attributes.md)|Wird sichergestellt, dass eine Typdefinition in der Typbibliothek wird, auch wenn es nicht in der IDL-Datei verweist.|  
|[ref](../windows/ref-cpp.md)|Identifiziert einen Verweiszeiger an.|  
|[switch_is](../windows/switch-is.md)|Gibt den Ausdruck oder einen Bezeichner fungiert als die union kombiniert werden sollen, die die union-Member auswählt.|  
|[switch_type](../windows/switch-type.md)|Gibt den Typ der Variablen als die union Discriminant verwendet.|  
|[unique](../windows/unique-cpp.md)|Gibt einen eindeutigen Zeiger.|  
|[wire_marshal](../windows/wire-marshal.md)|Gibt einen Datentyp, der für die Übertragung anstelle eines Typs anwendungsspezifische Daten verwendet wird.|  
  
### <a name="enum"></a>enum  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|[Benutzerdefinierte](../windows/custom-cpp.md)|Sie können Ihr eigenes Attribut definieren.|  
|[export](../windows/export.md)|Bewirkt, dass eine Datenstruktur, in der IDL-Datei platziert wird.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Gibt die eindeutige ID für eine Klasse oder Schnittstelle an.|  
|[v1_enum](../windows/v1-enum.md)|Wird angewiesen, der angegebene enumerierten Typ als eine 32-Bit-Entität und nicht als der Standardwert 16-Bit-übertragen werden.|  
  
### <a name="union"></a>union  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|[Benutzerdefinierte](../windows/custom-cpp.md)|Sie können Ihr eigenes Attribut definieren.|  
|[export](../windows/export.md)|Bewirkt, dass eine Datenstruktur, in der IDL-Datei platziert wird.|  
|[first_is](../windows/first-is.md)|Gibt den Index des ersten Arrayelements übertragen werden.|  
|[last_is](../windows/last-is.md)|Gibt den Index des letzten Elements Array übertragen werden.|  
|[length_is](../windows/length-is.md)|Gibt die Anzahl von Elementen übertragen werden.|  
|[max_is](../windows/max-is.md)|Legt fest, den maximalen Wert für ein gültiges Array-Index.|  
|[size_is](../windows/size-is.md)|Gibt an, die Größe des Arbeitsspeichers für Größe Zeiger zugewiesen, die Größe der Zeiger auf Zeiger, die Größe und Einzel- oder mehrdimensionale Arrays.|  
|[unique](../windows/unique-cpp.md)|Gibt einen eindeutigen Zeiger.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Gibt die eindeutige ID für eine Klasse oder Schnittstelle an.|  
  
### <a name="nonencapsulated-union"></a>Nonencapsulated union  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|[ms_union](../windows/ms-union.md)|Steuert die Netzwerk-datenausrichtung Darstellung nonencapsulated Unions.|  
|[no_injected_text](../windows/no-injected-text.md)|Verhindert, dass den Compiler Einfügen von Code durch Verwendung des Attributs.|  
  
### <a name="struct"></a>struct  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|[Aggregierbar](../windows/aggregatable.md)|Gibt an, dass die Klasse Aggregation unterstützt.|  
|[Aggregate](../windows/aggregates.md)|Gibt an, dass ein Steuerelement die Zielklasse aggregiert.|  
|[appobject](../windows/appobject.md)|Identifiziert die Co-Klasse als ein Anwendungsobjekt, das eine vollständige .exe-Anwendung zugeordnet ist, und gibt an, dass die Funktionen und Eigenschaften der Co-Klasse in diese Typbibliothek global verfügbar sind.|  
|[coclass](../windows/coclass.md)|Erstellt ein ActiveX-Steuerelement.|  
|[COM_INTERFACE_ENTRY](../windows/com-interface-entry-cpp.md)|Fügt einen Eintrag für die Schnittstelle eine COM-Zuordnung.|  
|[Steuerelement](../windows/control.md)|Gibt an, dass der benutzerdefinierte Typ eines Steuerelements.|  
|[Benutzerdefinierte](../windows/custom-cpp.md)|Sie können Ihr eigenes Attribut definieren.|  
|[db_column](../windows/db-column.md)|Bindet eine angegebene Spalte auf das Rowset an.|  
|[db_command](../windows/db-command.md)|Erstellt einen OLE DB-Befehl.|  
|[db_param](../windows/db-param.md)|Ordnet die angegebenen Member-Variable mit einem Eingabe- oder ausgabeadapter-Parameter und Variablen begrenzt.|  
|[db_source](../windows/db-source.md)|Erstellt eine Verbindung mit einer Datenquelle.|  
|[db_table](../windows/db-table.md)|Öffnet eine OLE DB-Tabelle.|  
|[default](../windows/default-cpp.md)|Gibt an, dass die benutzerdefinierte Schnittstelle oder Disp-Schnittstelle innerhalb einer Co-Klasse die Standard-Programmierschnittstelle darstellt.|  
|[defaultvtable](../windows/defaultvtable.md)|Definiert eine Schnittstelle als die Vtable-Standardschnittstelle für ein Steuerelement an.|  
|[event_receiver](../windows/event-receiver.md)|Erstellt einen Ereignisempfänger an.|  
|[event_source](../windows/event-source.md)|Erstellt eine Ereignisquelle.|  
|[export](../windows/export.md)|Bewirkt, dass eine Datenstruktur, in der IDL-Datei platziert wird.|  
|[first_is](../windows/first-is.md)|Gibt den Index des ersten Arrayelements übertragen werden.|  
|[hidden](../windows/hidden.md)|Gibt an, dass das Element vorhanden ist, aber nicht in einem benutzerorientierten Browser angezeigt werden soll.|  
|[implements_category](../windows/implements-category.md)|Gibt an, für die Klasse implementierten Komponentenkategorien.|  
|[last_is](../windows/last-is.md)|Gibt den Index des letzten Elements Array übertragen werden.|  
|[length_is](../windows/length-is.md)|Gibt die Anzahl von Elementen übertragen werden.|  
|[max_is](../windows/max-is.md)|Legt fest, den maximalen Wert für ein gültiges Array-Index.|  
|[requires_category](../windows/requires-category.md)|Gibt die erforderliche Komponentenkategorien der Zielklasse.|  
|[size_is](../windows/size-is.md)|Gibt an, die Größe des Arbeitsspeichers für Größe Zeiger zugewiesen, die Größe der Zeiger auf Zeiger, die Größe und Einzel- oder mehrdimensionale Arrays.|  
|[source](../windows/source-cpp.md)|Gibt an für eine Klasse das COM-Objekt-Schnittstellen für Verbindungspunkte aus. Auf eine Eigenschaft oder Methode gibt Sie an, dass das Element zurückgibt, ein Objekt oder eine Variante, die eine Ereignisquelle ist.|  
|[Threading](../windows/threading-cpp.md)|Gibt das Threadingmodell für eine COM-Objekt.|  
|[unique](../windows/unique-cpp.md)|Gibt einen eindeutigen Zeiger.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Gibt die eindeutige ID für eine Klasse oder Schnittstelle an.|  
|[version](../windows/version-cpp.md)|Identifiziert eine bestimmte Version mehrere Versionen einer Klasse.|  
|[vi_progid](../windows/vi-progid.md)|Gibt eine Art versionsunabhängige Programm-ID an.|  
  
## <a name="see-also"></a>Siehe auch  
 [Attribute nach Verwendung](../windows/attributes-by-usage.md)