---
title: TypeDef, Enum, Union- und Struct-Attribute (C++-COM)
ms.date: 10/02/2018
helpviewer_keywords:
- union attributes
- attributes [C++/CLI], reference topics
ms.assetid: f8a4fe94-dc02-4aed-bc31-3e500d42f4c7
ms.openlocfilehash: 2b56ada13a0c597866d538991ed1e83078924ac9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407223"
---
# <a name="typedef-enum-union-and-struct-attributes"></a>typedef-, enum-, union- und struct-Attribute

Die folgenden Attribute gelten für die [Typedef](../../cpp/aliases-and-typedefs-cpp.md), [Struktur](../../cpp/struct-cpp.md), und [Enum](../../cpp/enumerations-cpp.md) C++-Schlüsselwörter.

### <a name="typedef"></a>Typedef

|Attribut|Beschreibung|
|---------------|-----------------|
|[case](case-cpp.md)|Verwendung der [Switch_type](switch-type.md) -Attribut in einer **Union**.|
|[custom](custom-cpp.md)|Sie können Ihr eigenes Attribut definieren.|
|[export](export.md)|Bewirkt, dass eine Datenstruktur, in der IDL-Datei platziert wird.|
|[first_is](first-is.md)|Gibt den Index des ersten Arrayelements übertragen werden.|
|[helpcontext](helpcontext.md)|Gibt eine Kontext-ID, mit dem die Benutzerinformationen zu diesem Element in der Hilfedatei.|
|[helpfile](helpfile.md)|Legt den Namen der Hilfedatei für die Typbibliothek.|
|[helpstring](helpstring.md)|Gibt eine Zeichenfolge an, die zum Beschreiben des Elements verwendet wird, auf das sie angewendet wird.|
|[library_block](library-block.md)|Fügt ein Konstrukt in bibliotheksblock der IDL-Datei an.|
|[ptr](ptr.md)|Kennzeichnet einen Zeiger als vollständige Zeiger.|
|[public](public-cpp-attributes.md)|Wird sichergestellt, dass eine Typdefinition in der Typbibliothek wird, auch wenn es nicht in der IDL-Datei verweist.|
|[ref](ref-cpp.md)|Identifiziert einen Verweiszeiger an.|
|[switch_is](switch-is.md)|Gibt den Ausdruck oder einen Bezeichner fungiert als die union kombiniert werden sollen, die die union-Member auswählt.|
|[switch_type](switch-type.md)|Gibt den Typ der Variablen als die union Discriminant verwendet.|
|[unique](unique-cpp.md)|Gibt einen eindeutigen Zeiger.|
|[wire_marshal](wire-marshal.md)|Gibt einen Datentyp, der für die Übertragung anstelle eines Typs anwendungsspezifische Daten verwendet wird.|

### <a name="enum"></a>enum

|Attribut|Beschreibung|
|---------------|-----------------|
|[custom](custom-cpp.md)|Sie können Ihr eigenes Attribut definieren.|
|[export](export.md)|Bewirkt, dass eine Datenstruktur, in der IDL-Datei platziert wird.|
|[uuid](uuid-cpp-attributes.md)|Gibt die eindeutige ID für eine Klasse oder Schnittstelle an.|
|[v1_enum](v1-enum.md)|Wird angewiesen, der angegebene enumerierten Typ als eine 32-Bit-Entität und nicht als der Standardwert 16-Bit-übertragen werden.|

### <a name="union"></a>union

|Attribut|Beschreibung|
|---------------|-----------------|
|[custom](custom-cpp.md)|Sie können Ihr eigenes Attribut definieren.|
|[export](export.md)|Bewirkt, dass eine Datenstruktur, in der IDL-Datei platziert wird.|
|[first_is](first-is.md)|Gibt den Index des ersten Arrayelements übertragen werden.|
|[last_is](last-is.md)|Gibt den Index des letzten Elements Array übertragen werden.|
|[length_is](length-is.md)|Gibt die Anzahl von Elementen übertragen werden.|
|[max_is](max-is.md)|Legt fest, den maximalen Wert für ein gültiges Array-Index.|
|[size_is](size-is.md)|Gibt an, die Größe des Arbeitsspeichers für Größe Zeiger zugewiesen, die Größe der Zeiger auf Zeiger, die Größe und Einzel- oder mehrdimensionale Arrays.|
|[unique](unique-cpp.md)|Gibt einen eindeutigen Zeiger.|
|[uuid](uuid-cpp-attributes.md)|Gibt die eindeutige ID für eine Klasse oder Schnittstelle an.|

### <a name="nonencapsulated-union"></a>Nonencapsulated union

|Attribut|Beschreibung|
|---------------|-----------------|
|[ms_union](ms-union.md)|Steuert die Netzwerk-datenausrichtung Darstellung nonencapsulated Unions.|
|[no_injected_text](no-injected-text.md)|Verhindert, dass den Compiler Einfügen von Code durch Verwendung des Attributs.|

### <a name="struct"></a>struct

|Attribut|Beschreibung|
|---------------|-----------------|
|[Aggregierbar](aggregatable.md)|Gibt an, dass die Klasse Aggregation unterstützt.|
|[Aggregate](aggregates.md)|Gibt an, dass ein Steuerelement die Zielklasse aggregiert.|
|[appobject](appobject.md)|Identifiziert die Co-Klasse als ein Anwendungsobjekt, das eine vollständige .exe-Anwendung zugeordnet ist, und gibt an, dass die Funktionen und Eigenschaften der Co-Klasse in diese Typbibliothek global verfügbar sind.|
|[coclass](coclass.md)|Erstellt ein ActiveX-Steuerelement.|
|[com_interface_entry](com-interface-entry-cpp.md)|Fügt einen Eintrag für die Schnittstelle eine COM-Zuordnung.|
|[Steuerelement](control.md)|Gibt an, dass der benutzerdefinierte Typ eines Steuerelements.|
|[custom](custom-cpp.md)|Sie können Ihr eigenes Attribut definieren.|
|[db_column](db-column.md)|Bindet eine angegebene Spalte auf das Rowset an.|
|[db_command](db-command.md)|Erstellt einen OLE DB-Befehl.|
|[db_param](db-param.md)|Ordnet die angegebenen Member-Variable mit einem Eingabe- oder ausgabeadapter-Parameter und Variablen begrenzt.|
|[db_source](db-source.md)|Erstellt eine Verbindung mit einer Datenquelle.|
|[db_table](db-table.md)|Öffnet eine OLE DB-Tabelle.|
|[default](default-cpp.md)|Gibt an, dass die benutzerdefinierte Schnittstelle oder Disp-Schnittstelle innerhalb einer Co-Klasse die Standard-Programmierschnittstelle darstellt.|
|[defaultvtable](defaultvtable.md)|Definiert eine Schnittstelle als die Vtable-Standardschnittstelle für ein Steuerelement an.|
|[event_receiver](event-receiver.md)|Erstellt einen Ereignisempfänger an.|
|[event_source](event-source.md)|Erstellt eine Ereignisquelle.|
|[export](export.md)|Bewirkt, dass eine Datenstruktur, in der IDL-Datei platziert wird.|
|[first_is](first-is.md)|Gibt den Index des ersten Arrayelements übertragen werden.|
|[hidden](hidden.md)|Gibt an, dass das Element vorhanden ist, aber nicht in einem benutzerorientierten Browser angezeigt werden soll.|
|[implements_category](implements-category.md)|Gibt an, für die Klasse implementierten Komponentenkategorien.|
|[last_is](last-is.md)|Gibt den Index des letzten Elements Array übertragen werden.|
|[length_is](length-is.md)|Gibt die Anzahl von Elementen übertragen werden.|
|[max_is](max-is.md)|Legt fest, den maximalen Wert für ein gültiges Array-Index.|
|[requires_category](requires-category.md)|Gibt die erforderliche Komponentenkategorien der Zielklasse.|
|[size_is](size-is.md)|Gibt an, die Größe des Arbeitsspeichers für Größe Zeiger zugewiesen, die Größe der Zeiger auf Zeiger, die Größe und Einzel- oder mehrdimensionale Arrays.|
|[source](source-cpp.md)|Gibt an für eine Klasse das COM-Objekt-Schnittstellen für Verbindungspunkte aus. Auf eine Eigenschaft oder Methode gibt Sie an, dass das Element zurückgibt, ein Objekt oder eine Variante, die eine Ereignisquelle ist.|
|[threading](threading-cpp.md)|Gibt das Threadingmodell für eine COM-Objekt.|
|[unique](unique-cpp.md)|Gibt einen eindeutigen Zeiger.|
|[uuid](uuid-cpp-attributes.md)|Gibt die eindeutige ID für eine Klasse oder Schnittstelle an.|
|[version](version-cpp.md)|Identifiziert eine bestimmte Version mehrere Versionen einer Klasse.|
|[vi_progid](vi-progid.md)|Gibt eine Art versionsunabhängige Programm-ID an.|

## <a name="see-also"></a>Siehe auch

[Attribute nach Verwendung](attributes-by-usage.md)