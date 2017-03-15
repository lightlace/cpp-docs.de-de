---
title: "Typedef, Enum, Union, and Struct Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "union attributes"
  - "attributes [C++], reference topics"
  - "struct attributes"
  - "typedef attributes"
  - "enum attributes"
ms.assetid: f8a4fe94-dc02-4aed-bc31-3e500d42f4c7
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Typedef, Enum, Union, and Struct Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Attribute werden auf die [Typedef](assetId:///cc96cf26-ba93-4179-951e-695d1f5fdcf1), [Struktur](../cpp/struct-cpp.md)und [Enumeration](../cpp/enumerations-cpp.md) C\+\+ Schlüsselwörter an.  
  
### typedef  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|[case](../windows/case-cpp.md)|Wird mit dem [switch\_type](../windows/switch-type.md)\-Attribut in **Union**.|  
|[custom](../windows/custom-cpp.md)|Ermöglicht Ihnen definierten Attribut besitzen.|  
|["export"](../windows/export.md)|Bewirkt, dass eine Datenstruktur, in die IDL\-Datei abgelegt werden.|  
|[first\_is](../windows/first-is.md)|Gibt den Index des ersten zu sendenden Arrayelements an.|  
|[helpcontext](../windows/helpcontext.md)|Gibt eine Kontext\-ID an, die der Benutzer Informationen über dieses Element in der Hilfedatei können.|  
|[helpfile](../windows/helpfile.md)|Legt den Namen der Hilfedatei für eine Typbibliothek fest.|  
|[helpstring](../windows/helpstring.md)|Gibt eine Zeichenfolge an, durch die das zugehörige Element beschrieben wird.|  
|[library\_block](../windows/library-block.md)|Platziert ein Konstrukt innerhalb des Library\-Blocks der .idl\-Datei.|  
|[PTR](../windows/ptr.md)|Legt einen Zeiger als vollständiger Zeiger fest.|  
|[public](../windows/public-cpp-attributes.md)|Stellt sicher, dass eine Typdefinition in die Typbibliothek wechselt, selbst wenn sie nicht innerhalb der IDL\-Datei verwiesen wird.|  
|[ref](../windows/ref-cpp.md)|Identifiziert einen Verweiszeiger.|  
|[switch\_is](../windows/switch-is.md)|Gibt den Ausdruck oder den Bezeichner an, die als diskriminierende Union fungiert, die das Gewerkschaftsmitglied auswählt.|  
|[switch\_type](../windows/switch-type.md)|Gibt den Typ der Variablen, die als diskriminierende Union verwendet wird.|  
|[eindeutig](../windows/unique-cpp.md)|Gibt einen eindeutigen Zeiger an.|  
|[wire\_marshal](../windows/wire-marshal.md)|Gibt einen Datentyp an, der für die Übertragung anstelle eines anwendungsspezifischen Datentyps verwendet wird.|  
  
### enum  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|[custom](../windows/custom-cpp.md)|Ermöglicht Ihnen definierten Attribut besitzen.|  
|["export"](../windows/export.md)|Bewirkt, dass eine Datenstruktur, in die IDL\-Datei abgelegt werden.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Gibt die eindeutige ID für eine Klasse oder eine Schnittstelle an.|  
|[v1\_enum](../windows/v1-enum.md)|Verweist auf, denen der angegebene 32\-Bit\-Entität als Aufzählungstyp gesendet wird, und nicht mit dem 16\-Bit\-Standard.|  
  
### union  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|[custom](../windows/custom-cpp.md)|Ermöglicht Ihnen definierten Attribut besitzen.|  
|["export"](../windows/export.md)|Bewirkt, dass eine Datenstruktur, in die IDL\-Datei abgelegt werden.|  
|[first\_is](../windows/first-is.md)|Gibt den Index des ersten zu sendenden Arrayelements an.|  
|[last\_is](../windows/last-is.md)|Gibt den Index des letzten gesendet werden sollen, Arrayelements an.|  
|[length\_is](../windows/length-is.md)|Gibt die Anzahl der zu sendenden auf Arrayelemente.|  
|[max\_is](../windows/max-is.md)|Legt den Höchstwert für einen gültigen Arrayindex.|  
|[size\_is](../windows/size-is.md)|Gibt die Größe des zugeordneten Speichers für sortierte Zeiger, sortierte Zeiger auf sortierten Zeigern und einzel\- oder mehrdimensionalen Felder an.|  
|[eindeutig](../windows/unique-cpp.md)|Gibt einen eindeutigen Zeiger an.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Gibt die eindeutige ID für eine Klasse oder eine Schnittstelle an.|  
  
### Nonencapsulated\-Union  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|[ms\_union](../windows/ms-union.md)|Steuert die Ausrichtung der Netzwerk Informationsdarstellung von nonencapsulated Unions.|  
|[no\_injected\_text](../windows/no-injected-text.md)|Verhindert, dass der Compiler Code aufgrund der Attributverwendung einfügt.|  
  
### struct  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|[aggregierbar](../windows/aggregatable.md)|Gibt an, dass die Klasse Aggregation unterstützt.|  
|[Aggregate](../windows/aggregates.md)|Gibt an, dass ein Steuerelement die Zielklasse aggregiert.|  
|[appobject](../windows/appobject.md)|Identifiziert die Co\-Klasse als Anwendungsobjekt, das einer vollständigen EXE\-Anwendung zugeordnet ist, und gibt an, dass Features und Eigenschaften der Co\-Klasse in dieser Typbibliothek global verfügbar sind.|  
|[Co\-Klasse](../windows/coclass.md)|Erstellt ein ActiveX\-Steuerelement.|  
|[com\_interface\_entry](../windows/com-interface-entry-cpp.md)|Fügt einen Eintrag für eine COM\-Zuordnung Schnittstellen hinzu.|  
|[\-Steuerelement](../windows/control.md)|Gibt an, dass der benutzerdefinierte Typ ein Steuerelement befindet.|  
|[custom](../windows/custom-cpp.md)|Ermöglicht Ihnen definierten Attribut besitzen.|  
|[db\_column](../windows/db-column.md)|Bindet eine angegebene Spalte auf das Rowset.|  
|[db\_command](../windows/db-command.md)|Erstellt einen OLE DB\-Befehl.|  
|[db\_param](../windows/db-param.md)|Ordnet die angegebene Membervariable mit einer Eingabe oder einem Ausgabeparameter und schränkt die Variable ab.|  
|[db\_source](../windows/db-source.md)|Erstellt eine Verbindung zu einer Datenquelle.|  
|[db\_table](../windows/db-table.md)|Öffnet eine OLE DB\-Tabelle.|  
|[default](../windows/default-cpp.md)|Gibt an, dass die benutzerdefinierte oder die Dispatchschnittstelle, die innerhalb einer Co\-Klasse definierten Programmierung der Schnittstelle darstellt.|  
|[defaultvtable](../windows/defaultvtable.md)|Definiert eine Schnittstelle als die standardmäßige vtable Schnittstelle für ein Steuerelement.|  
|[event\_receiver](../windows/event-receiver.md)|Stellt einen Ereignisempfänger erstellt.|  
|[event\_source](../windows/event-source.md)|Erstellt eine Ereignisquelle.|  
|["export"](../windows/export.md)|Bewirkt, dass eine Datenstruktur, in die IDL\-Datei abgelegt werden.|  
|[first\_is](../windows/first-is.md)|Gibt den Index des ersten zu sendenden Arrayelements an.|  
|[hidden](../windows/hidden.md)|Gibt an, dass das Element vorhanden ist, in einem benutzerorientierten Browser jedoch nicht angezeigt werden sollte.|  
|[implements\_category](../windows/implements-category.md)|Gibt implementierte Teil Kategorien für die Klasse.|  
|[last\_is](../windows/last-is.md)|Gibt den Index des letzten gesendet werden sollen, Arrayelements an.|  
|[length\_is](../windows/length-is.md)|Gibt die Anzahl der zu sendenden auf Arrayelemente.|  
|[max\_is](../windows/max-is.md)|Legt den Höchstwert für einen gültigen Arrayindex.|  
|[requires\_category](../windows/requires-category.md)|Gibt die Kategorien erforderlicher Teil der Zielklasse an.|  
|[size\_is](../windows/size-is.md)|Gibt die Größe des zugeordneten Speichers für sortierte Zeiger, sortierte Zeiger auf sortierten Zeigern und einzel\- oder mehrdimensionalen Felder an.|  
|[source](../windows/source-cpp.md)|Auf einer Klasse gibt die Schnittstellen des COM\-Objekts Quelle für Verbindungspunkte an.  Auf einer Eigenschaft oder einer Methode gibt an, dass der Member ein Objekt oder einen VARIANT zurück, das eine Ereignisquelle ist.|  
|[Threading](../windows/threading-cpp.md)|Gibt das Threadingmodell für ein COM\-Objekt an.|  
|[eindeutig](../windows/unique-cpp.md)|Gibt einen eindeutigen Zeiger an.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Gibt die eindeutige ID für eine Klasse oder eine Schnittstelle an.|  
|[Version](../windows/version-cpp.md)|Identifiziert eine bestimmte Version für mehrere Versionen einer Klasse.|  
|[vi\_progid](../windows/vi-progid.md)|Gibt ein versionsunabhängiges ProgID des Formulars an.|  
  
## Siehe auch  
 [Attributes by Usage](../windows/attributes-by-usage.md)