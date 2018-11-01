---
title: Alphabetische Attributreferenz
ms.custom: index-page
ms.date: 10/02/2018
ms.topic: conceptual
f1_keywords:
- vc.attributes
helpviewer_keywords:
- attributes [C++/CLI]
ms.assetid: fb2216ef-9fbd-44f4-afed-732aa99450e2
ms.openlocfilehash: ecf59b0d920b39d8f129e3ff25b5518f985d78f5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50516908"
---
# <a name="attributes-alphabetical-reference"></a>Alphabetische Attributreferenz

Die folgenden Attribute sind in Microsoft C++-Compiler verfügbar:

|Attribut|Beschreibung|
|---------------|-----------------|
|[Aggregierbar](aggregatable.md)|Gibt an, dass ein Steuerelement durch ein anderes Steuerelement aggregiert werden kann.|
|[Aggregate](aggregates.md)|Gibt an, dass ein Steuerelement die Zielklasse aggregiert.|
|[appobject](appobject.md)|Identifiziert die Co-Klasse als ein Anwendungsobjekt, das eine vollständige Anwendung für die EXE-Datei zugeordnet ist, und gibt an, dass die Funktionen und Eigenschaften der Co-Klasse in diese Typbibliothek global verfügbar sind.|
|[async_uuid](async-uuid.md)|Gibt an, die UUID, die den MIDL-Compiler definiert synchrone und asynchrone Versionen einer COM-Schnittstelle weiterleitet.|
|[Attribut](attribute.md)|Ermöglicht Ihnen die Erstellung ein benutzerdefiniertes Attributs.|
|[bindable](bindable.md)|Gibt an, dass die Eigenschaft die Datenbindung unterstützt.|
|[call_as](call-as.md)|Aktiviert eine Funktion nicht remotefähige an eine remote-Funktion zugeordnet werden soll.|
|[case](case-cpp.md)|Verwendung der [Switch_type](switch-type.md) Attribut in einer Union.|
|[coclass](coclass.md)|Erstellt ein COM-Objekt, die eine COM-Schnittstelle implementieren können.|
|[com_interface_entry](com-interface-entry-cpp.md)|Fügt einen Eintrag für die Schnittstelle eine COM-Zuordnung.|
|[Steuerelement](control.md)|Gibt an, dass der benutzerdefinierte Typ eines Steuerelements.|
|[cpp_quote](cpp-quote.md)|Gibt die angegebene Zeichenfolge verwendet werden, ohne die Anführungszeichen in der generierten Headerdatei an.|
|[custom](custom-cpp.md)|Können Sie eigene Attribute definieren.|
|[db_accessor](db-accessor.md)|Bindet Spalten in einem Rowset, und bindet sie an der entsprechenden Accessor-Zuordnungen.|
|[db_column](db-column.md)|Bindet eine angegebene Spalte auf das Rowset an.|
|[db_command](db-command.md)|Führt einen OLE DB-Befehl.|
|[db_param](db-param.md)|Ordnet die angegebenen Member-Variable mit einem Eingabe- oder ausgabeadapter-Parameter.|
|[db_source](db-source.md)|Erstellt und eine Verbindung über einen Anbieter, mit einer Datenquelle kapselt.|
|[db_table](db-table.md)|Öffnet eine OLE DB-Tabelle.|
|[default](default-cpp.md)|Gibt an, dass die benutzerdefinierte Schnittstelle oder Disp-Schnittstelle innerhalb einer Co-Klasse die Standard-Programmierschnittstelle darstellt.|
|[defaultbind](defaultbind.md)|Gibt an, die einfache, bindbare Eigenschaft, die das Objekt am besten darstellt.|
|[defaultcollelem](defaultcollelem.md)|Für die Optimierung für Visual Basic-Code verwendet.|
|[defaultvalue](defaultvalue.md)|Ermöglicht die Angabe eines Standardwerts für einen typisierten optionalen Parameter.|
|[defaultvtable](defaultvtable.md)|Definiert eine Schnittstelle als die Vtable-Standardschnittstelle für ein Steuerelement an.|
|[dispinterface](dispinterface.md)|Fügt eine Schnittstelle in die IDL-Datei als Verteilschnittstelle ein.|
|[displaybind](displaybind.md)|Gibt eine Eigenschaft, die dem Benutzer als bindungsfähig angezeigt werden soll.|
|[dual](dual.md)|Fügt eine Schnittstelle in der IDL-Datei als eine duale Schnittstelle an.|
|[emitidl](emitidl.md)|Bestimmt, ob alle nachfolgenden IDL-Attribute verarbeitet und in der generierten IDL-Datei platziert werden.|
|[entry](entry.md)|Gibt eine exportierte Funktion oder Konstante in einem Modul durch identifizieren den Einstiegspunkt in der DLL an.|
|[event_receiver](event-receiver.md)|Erstellt einen Ereignisempfänger an.|
|[event_source](event-source.md)|Erstellt eine Ereignisquelle.|
|[export](export.md)|Bewirkt, dass eine Datenstruktur, in der IDL-Datei platziert wird.|
|[first_is](first-is.md)|Gibt den Index des ersten Arrayelements übertragen werden.|
|[helpcontext](helpcontext.md)|Gibt eine Kontext-ID, mit dem die Benutzerinformationen zu diesem Element in der Hilfedatei.|
|[helpfile](helpfile.md)|Legt den Namen der Hilfedatei für die Typbibliothek.|
|[helpstring](helpstring.md)|Gibt die ID des Hilfethemas in eine .hlp oder CHM-Datei an.|
|[helpstringdll](helpstringdll.md)|Gibt den Namen der DLL zu verwenden, um die Suche nach Dokument (Lokalisierung) ausführen.|
|[hidden](hidden.md)|Gibt an, dass das Element vorhanden ist, aber nicht in einem benutzerorientierten Browser angezeigt werden soll.|
|[ID](id.md)|Gibt eine DISPID für eine Memberfunktion (eine Eigenschaft oder eine Methode, in eine Schnittstelle oder Disp-Schnittstelle).|
|[idl_module](idl-module.md)|Gibt einen Einstiegspunkt in einer DLL an.|
|[idl_quote](idl-quote.md)|Können Sie Attribute verwenden, oder IDL-Konstrukte, die in der aktuellen Version von Visual C++ nicht unterstützt werden.|
|[iid_is](iid-is.md)|Gibt die IID für die COM-Schnittstelle, die einen Schnittstellenzeiger einen verweist.|
|[immediatebind](immediatebind.md)|Gibt an, dass die Datenbank über alle Änderungen an einer Eigenschaft eines datengebundenen Objekts sofort benachrichtigt wird.|
|[implements](implements-cpp.md)|Gibt die Dispatch-Schnittstellen, die erzwungen werden, um die IDL-Co-Klasse angehören.|
|[implements_category](implements-category.md)|Gibt an, für die Klasse implementierten Komponentenkategorien.|
|[import](import.md)|Gibt eine andere IDL, Header oder ODL-Datei enthält Definitionen, die Sie von Ihrem wichtigsten IDL-Datei verweisen möchten.|
|[importidl](importidl.md)|Fügt die angegebenen IDL-Datei in der generierten IDL-Datei an.|
|[importlib](importlib.md)|Stellt Typen, die bereits in einer anderen Typbibliothek kompiliert wurden, der erstellten Typbibliothek zur Verfügung.|
|[in](in-cpp.md)|Gibt an, dass ein Parameter, die von der aufrufenden Prozedur an die aufgerufene Prozedur übergeben werden.|
|[include](include-cpp.md)|Gibt einen oder mehrere Headerdateien, die in der generierten IDL-Datei eingeschlossen werden.|
|[includelib](includelib-cpp.md)|Bewirkt, dass eine IDL- oder h-Datei, die in der generierten IDL-Datei eingeschlossen werden.|
|[last_is](last-is.md)|Gibt den Index des letzten Elements Array übertragen werden.|
|[lcid](lcid.md)|Sie können einen Gebietsschemabezeichner an eine Funktion übergeben.|
|[length_is](length-is.md)|Gibt die Anzahl von Elementen übertragen werden.|
|[library_block](library-block.md)|Fügt ein Konstrukt in bibliotheksblock der IDL-Datei an.|
|[licensed](licensed.md)|Gibt an, dass die Co-Klasse, die auf die es angewendet wird lizenziert, und muss mit instanziiert werden `IClassFactory2`.|
|[local](local-cpp.md)|Ermöglicht Ihnen die Verwendung den MIDL-Compiler als ein Header-Generator, wenn in der Schnittstelle-Header verwendet. Bei Verwendung in einer einzelnen Funktion kennzeichnet eine lokale Prozedur, die für die keine Stubs generiert werden.|
|[max_is](max-is.md)|Legt fest, den maximalen Wert für ein gültiges Array-Index.|
|[module](module-cpp.md)|Definiert den Bibliotheksblock in der IDL-Datei.|
|[ms_union](ms-union.md)|Steuert die Netzwerk-datenausrichtung Darstellung nonencapsulated Unions.|
|[no_injected_text](no-injected-text.md)|Verhindert, dass den Compiler Einfügen von Code durch Verwendung des Attributs.|
|[nonbrowsable](nonbrowsable.md)|Gibt an, dass ein Schnittstellenmember nicht in einem Eigenschaftenbrowser angezeigt werden soll.|
|[noncreatable](noncreatable.md)|Definiert ein Objekt, das allein nicht instanziiert werden kann.|
|[nonextensible](nonextensible.md)|Gibt an, dass die `IDispatch` -Implementierung enthält nur die Eigenschaften und Methoden aufgeführt, die in der schnittstellenbeschreibung und können nicht zur Laufzeit zusätzliche Member erweitert werden.|
|[object](object-cpp.md)|Identifiziert eine benutzerdefinierte Schnittstelle an. gleichbedeutend mit benutzerdefinierten Attribut.|
|[odl](odl.md)|Gibt eine Schnittstelle als Schnittstelle Objekt Description Language (ODL).|
|[oleautomation](oleautomation.md)|Gibt an, dass eine Schnittstelle mit der Automatisierung kompatibel ist.|
|[optional](optional-cpp.md)|Gibt einen optionalen Parameter für eine Memberfunktion an.|
|[out](out-cpp.md)|Gibt die Zeigerparameter an, die von der aufgerufenen Prozedur an die aufrufende Prozedur zurückgegeben werden (vom Server an den Client).|
|[pointer_default](pointer-default.md)|Gibt das Standardattribut für die Zeiger für alle Zeiger, mit Ausnahme der obersten Ebene Zeigern, die angezeigt werden in der Parameterliste.|
|[pragma](pragma.md)|Gibt die angegebene Zeichenfolge verwendet werden, ohne die Anführungszeichen in der generierten IDL-Datei aus.|
|[progid](progid.md)|Gibt an, die ProgID für ein COM-Objekt.|
|[propget](propget.md)|Gibt eine Eigenschaft Accessorfunktion (Get).|
|[propput](propput.md)|Gibt eine Eigenschaftseinstellungsfunktion an.|
|[propputref](propputref.md)|Gibt eine eigenschaftseinstellungsfunktion an, die einen Verweis anstelle eines Werts verwendet.|
|[ptr](ptr.md)|Kennzeichnet einen Zeiger als vollständige Zeiger.|
|[public](public-cpp-attributes.md)|Wird sichergestellt, dass eine Typdefinition in der Typbibliothek wird, auch wenn es nicht in der IDL-Datei verweist.|
|[range](range-cpp.md)|Gibt einen Bereich der zulässigen Werte für die Argumente oder Felder, deren Werte zur Laufzeit festgelegt werden.|
|[rdx](rdx.md)|Erstellt oder ändert einen Registrierungsschlüssel.|
|[readonly](readonly-cpp.md)|Verhindert die Zuweisung zu einer Variablen.|
|[ref](ref-cpp.md)|Identifiziert einen Verweiszeiger an.|
|[registration_script](registration-script.md)|Führt die angegebene Registrierungsskript aus.|
|[requestedit](requestedit.md)|Gibt an, dass die Eigenschaft unterstützt die `OnRequestEdit` Benachrichtigung.|
|[requires_category](requires-category.md)|Gibt Kategorien von erforderliche Komponente für die Klasse an.|
|[restricted](restricted.md)|Gibt an, dass es sich bei einer Bibliothek oder einem Mitglied ein Modul, Schnittstelle oder Disp-Schnittstelle nicht beliebig aufgerufen werden kann.|
|[retval](retval.md)|Legt fest, den Parameter, der den Rückgabewert des Members empfängt.|
|[satype](satype.md)|Gibt den Datentyp, der die `SAFEARRAY`.|
|[size_is](size-is.md)|Gibt an, die Größe des Arbeitsspeichers für Größe Zeiger zugewiesen, die Größe der Zeiger auf Zeiger, die Größe und Einzel- oder mehrdimensionale Arrays.|
|[source](source-cpp.md)|Gibt an, dass ein Member der Klasse, Eigenschaft oder Methode eine Ereignisquelle ist.|
|[string](string-cpp.md)|Gibt an, dass das eindimensionale **Char**, **"wchar_t"**, `byte`, oder das entsprechende Array oder der Zeiger auf ein solches Array muss als Zeichenfolge behandelt werden.|
|[support_error_info](support-error-info.md)|Unterstützt die Windows-Fehlerberichterstattung für das Zielobjekt.|
|[switch_is](switch-is.md)|Gibt den Ausdruck oder einen Bezeichner fungiert als die union kombiniert werden sollen, die die union-Member auswählt.|
|[switch_type](switch-type.md)|Gibt den Typ der Variablen als die union Discriminant verwendet.|
|[synchronize](synchronize.md)|Synchronisiert den Zugriff auf eine Methode.|
|[threading](threading-cpp.md)|Gibt das Threadingmodell für eine COM-Objekt.|
|[transmit_as](transmit-as.md)|Weist den Compiler dargestellt ein, die Client- und serveranwendungen bearbeiten zu können, müssen, mit einem übertragenen Typ zuordnen.|
|[uidefault](uidefault.md)|Gibt an, dass der Typinformationsmember das Standardelement für die Anzeige in der Benutzeroberfläche.|
|[unique](unique-cpp.md)|Gibt einen eindeutigen Zeiger.|
|[usesgetlasterror](usesgetlasterror.md)|Wird dem Aufrufer mitgeteilt, dass der Aufrufer bei wird ein Fehler beim Aufrufen dieser Funktion dann aufrufen kann `GetLastError` auf den Fehlercode abzurufen.|
|[uuid](uuid-cpp-attributes.md)|Gibt die eindeutige ID für eine Klasse oder Schnittstelle an.|
|[v1_enum](v1-enum.md)|Wird angewiesen, der angegebene enumerierten Typ als eine 32-Bit-Entität und nicht als der Standardwert 16-Bit-übertragen werden.|
|[vararg](vararg.md)|Gibt an, dass die Funktion eine Variable Anzahl von Argumenten akzeptieren.|
|[version](version-cpp.md)|Identifiziert eine bestimmte Version mehrere Versionen einer Schnittstelle oder Klasse an.|
|[vi_progid](vi-progid.md)|Gibt eine Art versionsunabhängige Programm-ID an.|
|[wire_marshal](wire-marshal.md)|Gibt einen Datentyp, der für die Übertragung anstelle eines Typs anwendungsspezifische Daten verwendet wird.|

## <a name="see-also"></a>Siehe auch

[C++-Attribute für COM und .NET](cpp-attributes-com-net.md)<br/>
[Attribute nach Gruppen](attributes-by-group.md)<br/>
[Attribute nach Verwendung](attributes-by-usage.md)