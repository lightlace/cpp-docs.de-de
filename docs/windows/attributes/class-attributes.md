---
title: Klassenattribute (C++-COM)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], class attributes
ms.assetid: fad04ea1-d8ff-46d4-bb42-2b4500a6ab60
ms.openlocfilehash: d0913d09c51734f5255271c0d06e639810e0cb58
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025415"
---
# <a name="class-attributes"></a>Klassenattribute

Die folgenden Attribute gelten für die [Klasse](../../cpp/class-cpp.md) C++-Schlüsselwort.

|Attribut|Beschreibung|
|---------------|-----------------|
|[Aggregierbar](aggregatable.md)|Gibt an, dass die Klasse Aggregation unterstützt.|
|[Aggregate](aggregates.md)|Gibt an, dass ein Steuerelement die Zielklasse aggregiert.|
|[appobject](appobject.md)|Identifiziert die Co-Klasse als ein Anwendungsobjekt, das eine vollständige .exe-Anwendung zugeordnet ist, und gibt an, dass die Funktionen und Eigenschaften der Co-Klasse in diese Typbibliothek global verfügbar sind.|
|[case](case-cpp.md)|Verwendung der [Switch_type](switch-type.md) Attribut in einer Union.|
|[coclass](coclass.md)|Erstellt ein ActiveX-Steuerelement.|
|[com_interface_entry](com-interface-entry-cpp.md)|Fügt einen Eintrag für die Schnittstelle eine COM-Zuordnung.|
|[Steuerelement](control.md)|Gibt an, dass der benutzerdefinierte Typ eines Steuerelements.|
|[custom](custom-cpp.md)|Sie können Ihr eigenes Attribut definieren.|
|[db_command](db-command.md)|Erstellt einen OLE DB-Befehl.|
|[db_param](db-param.md)|Ordnet die angegebenen Member-Variable mit einem Eingabe- oder ausgabeadapter-Parameter und Variablen begrenzt.|
|[db_source](db-source.md)|Erstellt eine Verbindung mit einer Datenquelle.|
|[db_table](db-table.md)|Öffnet eine OLE DB-Tabelle.|
|[default](default-cpp.md)|Gibt an, dass die benutzerdefinierte Schnittstelle oder Disp-Schnittstelle innerhalb einer Co-Klasse die Standard-Programmierschnittstelle darstellt.|
|[defaultvtable](defaultvtable.md)|Definiert eine Schnittstelle als die Vtable-Standardschnittstelle für ein Steuerelement an.|
|[event_receiver](event-receiver.md)|Erstellt einen Ereignisempfänger an.|
|[event_source](event-source.md)|Erstellt eine Ereignisquelle.|
|[helpcontext](helpcontext.md)|Gibt eine Kontext-ID, mit dem die Benutzerinformationen zu diesem Element in der **Hilfe** Datei.|
|[helpfile](helpfile.md)|Legt den Namen der Hilfedatei für die Typbibliothek.|
|[helpstringcontext](helpstringcontext.md)|Gibt die ID des Hilfethemas in eine .hlp oder CHM-Datei an.|
|[helpstring](helpstring.md)|Gibt eine Zeichenfolge an, die zum Beschreiben des Elements verwendet wird, auf das sie angewendet wird.|
|[hidden](hidden.md)|Gibt an, dass das Element vorhanden ist, aber nicht in einem benutzerorientierten Browser angezeigt werden soll.|
|[implements](implements-cpp.md)|Gibt die Dispatch-Schnittstellen, die erzwungen werden, um die IDL-Co-Klasse angehören.|
|[implements_category](implements-category.md)|Gibt an, für die Klasse implementierten Komponentenkategorien.|
|[module](module-cpp.md)|Definiert den Bibliotheksblock in der IDL-Datei.|
|[noncreatable](noncreatable.md)|Definiert ein Objekt, das allein nicht instanziiert werden kann.|
|[progid](progid.md)|Definiert die ProgID für ein Steuerelement an.|
|[registration_script](registration-script.md)|Führt die angegebene Registrierungsskript aus.|
|[requestedit](requestedit.md)|Gibt an, dass die Eigenschaft die `OnRequestEdit`-Benachrichtigung unterstützt.|
|[source](source-cpp.md)|Gibt den Schnittstellen des Steuerelements nach Verbindungspunkten für eine Klasse an. Auf eine Eigenschaft oder Methode die `source` Attribut gibt an, dass das Element ein Objekt zurückgibt oder `VARIANT` , die eine Quelle von Ereignissen.|
|[support_error_info](support-error-info.md)|Unterstützt die Windows-Fehlerberichterstattung für das Zielobjekt.|
|[threading](threading-cpp.md)|Gibt das Threadingmodell für ein Steuerelement an.|
|[uuid](uuid-cpp-attributes.md)|Gibt die eindeutige ID für eine Klasse oder Schnittstelle an.|
|[version](version-cpp.md)|Identifiziert eine bestimmte Version mehrere Versionen einer Klasse.|
|[vi_progid](vi-progid.md)|Gibt eine Art versionsunabhängige Programm-ID an.|

## <a name="see-also"></a>Siehe auch

[Attribute nach Verwendung](attributes-by-usage.md)