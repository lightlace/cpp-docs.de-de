---
title: IDL-Attribute (C++-COM-) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- IDL attributes
- .idl files [C++], attributes
- IDL files [C++], attributes
- .idl files [C++]
ms.assetid: 04c596f4-c97b-4952-8053-316678b1d0b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ebc257d78bf658b722a93e9d7c306c9bcf6e88bd
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791726"
---
# <a name="idl-attributes"></a>IDL-Attribute

In der Vergangenheit mussten eine IDL-Datei verwalten Sie zu:

- Mit der Struktur und Syntax von einer IDL-Datei ändern kann vertraut sein.

- Basieren Sie auf einen Assistenten, der Sie einige Aspekte der IDL-Datei ändern kann.

Jetzt können Sie von innerhalb einer Quellcodedatei, die mithilfe von Visual C++-IDL-Attribute die IDL-Datei ändern. In vielen Fällen müssen die Visual C++-IDL-Attribute den gleichen Namen wie das MIDL-Attribute. Wenn der Name des ein Visual C++-IDL-Attribut und einem MIDL-Attribut identisch sind, bedeutet dies, dass dies ist das Visual C++-Attribut in der Quellcodedatei in einer IDL-Datei führt, die die entwicklungsboard MIDL-Attribut enthält. Allerdings kann ein Visual C++-IDL-Attribut nicht alle Funktionen der MIDL-Attribut bereitstellen.

Bei Verwendung nicht mit [COM-Attributen](com-attributes.md), IDL-Attribute können Sie die Schnittstellen definieren. Wenn der Quellcode kompiliert wird, werden die Attribute zum Definieren der generierten IDL-Datei verwendet. Bei Verwendung mit COM-Attributen in einem ATL-Projekt einige IDL Attribute, z. B. `coclass`, dass Code in das Projekt eingefügt werden.

Beachten Sie, dass [Idl_quote](idl-quote.md) können Sie MIDL-Konstrukte, die in der aktuellen Version von Visual C++ nicht unterstützt werden. Diese und andere Attribute wie z. B. [Importlib](importlib.md) und [Includelib](includelib-cpp.md) finden Sie Informationen zu vorhandenen IDL-Dateien in Ihrem aktuellen Visual C++-Projekt verwenden.

|Attribut|Beschreibung|
|---------------|-----------------|
|[Aggregierbar](aggregatable.md)|Gibt an, dass ein Steuerelement durch ein anderes Steuerelement aggregiert werden kann.|
|[appobject](appobject.md)|Identifiziert die Co-Klasse als ein Anwendungsobjekt, das eine vollständige Anwendung für die EXE-Datei zugeordnet ist, und gibt an, dass die Funktionen und Eigenschaften der Co-Klasse in diese Typbibliothek global verfügbar sind.|
|[async_uuid](async-uuid.md)|Gibt an, die UUID, die den MIDL-Compiler definiert synchrone und asynchrone Versionen einer COM-Schnittstelle weiterleitet.|
|[bindable](bindable.md)|Gibt an, dass die Eigenschaft die Datenbindung unterstützt.|
|[call_as](call-as.md)|Aktiviert eine Funktion nicht remotefähige an eine remote-Funktion zugeordnet werden soll.|
|[case](case-cpp.md)|Verwendung der [Switch_type](switch-type.md) Attribut in einer Union.|
|[coclass](coclass.md)|Stellen Klassendefinition in einer IDL-Datei als Co-Klasse.|
|[Steuerelement](control.md)|Gibt an, dass der benutzerdefinierte Typ eines Steuerelements.|
|[cpp_quote](cpp-quote.md)|Gibt die angegebene Zeichenfolge verwendet werden, ohne die Anführungszeichen in der generierten Headerdatei an.|
|[defaultbind](defaultbind.md)|Gibt an, die einfache, bindbare Eigenschaft, die das Objekt am besten darstellt.|
|[defaultcollelem](defaultcollelem.md)|Für die Optimierung für Visual Basic-Code verwendet.|
|[defaultvalue](defaultvalue.md)|Ermöglicht die Angabe eines Standardwerts für einen typisierten optionalen Parameter.|
|[default](default-cpp.md)|Gibt an, dass die benutzerdefinierte Schnittstelle oder Disp-Schnittstelle innerhalb einer Co-Klasse die Standard-Programmierschnittstelle darstellt.|
|[defaultvtable](defaultvtable.md)|Definiert eine Schnittstelle als die Vtable-Standardschnittstelle für ein Steuerelement an.|
|[dispinterface](dispinterface.md)|Fügt eine Schnittstelle in die IDL-Datei als Verteilschnittstelle ein.|
|[displaybind](displaybind.md)|Gibt eine Eigenschaft, die dem Benutzer als bindungsfähig angezeigt werden soll.|
|[dual](dual.md)|Fügt eine Schnittstelle in der IDL-Datei als eine duale Schnittstelle an.|
|[entry](entry.md)|Gibt eine exportierte Funktion oder Konstante in einem Modul durch identifizieren den Einstiegspunkt in der DLL an.|
|[first_is](first-is.md)|Gibt den Index des ersten Arrayelements übertragen werden.|
|[helpcontext](helpcontext.md)|Gibt eine Kontext-ID, mit dem die Benutzerinformationen zu diesem Element in der Hilfedatei.|
|[helpfile](helpfile.md)|Legt den Namen der Hilfedatei für die Typbibliothek.|
|[helpstringcontext](helpstringcontext.md)|Gibt die ID des Hilfethemas in eine .hlp oder CHM-Datei an.|
|[helpstringdll](helpstringdll.md)|Gibt den Namen der DLL zu verwenden, um die Suche nach Dokument (Lokalisierung) ausführen.|
|[helpstring](helpstring.md)|Gibt eine Zeichenfolge an, die zum Beschreiben des Elements verwendet wird, auf das sie angewendet wird.|
|[hidden](hidden.md)|Gibt an, dass das Element vorhanden ist, aber nicht in einem benutzerorientierten Browser angezeigt werden soll.|
|[idl_module](idl-module.md)|Gibt einen Einstiegspunkt in einer DLL an.|
|[idl_quote](idl-quote.md)|Können Sie Attribute verwenden, oder IDL-Konstrukte, die in der aktuellen Version von Visual C++ nicht unterstützt werden.|
|[ID](id.md)|Gibt eine DISPID für eine Memberfunktion (eine Eigenschaft oder eine Methode, in eine Schnittstelle oder Disp-Schnittstelle).|
|[iid_is](iid-is.md)|Gibt die IID für die COM-Schnittstelle, die einen Schnittstellenzeiger einen verweist.|
|[immediatebind](immediatebind.md)|Gibt an, dass die Datenbank über alle Änderungen an einer Eigenschaft eines datengebundenen Objekts sofort benachrichtigt wird.|
|[importlib](importlib.md)|Stellt Typen, die bereits in einer anderen Typbibliothek kompiliert wurden, der erstellten Typbibliothek zur Verfügung.|
|[import](import.md)|Gibt eine andere IDL, Header oder ODL-Datei enthält Definitionen, die Sie von Ihrem wichtigsten IDL-Datei verweisen möchten.|
|[include](include-cpp.md)|Gibt einen oder mehrere Headerdateien, die in der generierten IDL-Datei eingeschlossen werden.|
|[includelib](includelib-cpp.md)|Bewirkt, dass eine IDL- oder h-Datei, die in der generierten IDL-Datei eingeschlossen werden.|
|[in](in-cpp.md)|Gibt an, dass ein Parameter, die von der aufrufenden Prozedur an die aufgerufene Prozedur übergeben werden.|
|[last_is](last-is.md)|Gibt den Index des letzten Elements Array übertragen werden.|
|[lcid](lcid.md)|Sie können einen Gebietsschemabezeichner an eine Funktion übergeben.|
|[length_is](length-is.md)|Gibt die Anzahl von Elementen übertragen werden.|
|[licensed](licensed.md)|Gibt an, dass die Co-Klasse, die auf die es angewendet wird lizenziert, und muss mit instanziiert werden `IClassFactory2`.|
|[local](local-cpp.md)|Ermöglicht Ihnen die Verwendung den MIDL-Compiler als ein Header-Generator, wenn in der Schnittstelle-Header verwendet. Bei Verwendung in einer einzelnen Funktion kennzeichnet eine lokale Prozedur, die für die keine Stubs generiert werden.|
|[max_is](max-is.md)|Legt fest, den maximalen Wert für ein gültiges Array-Index.|
|[Modul](module-cpp.md)|Definiert den Bibliotheksblock in der IDL-Datei.|
|[ms_union](ms-union.md)|Steuert die Netzwerk-datenausrichtung Darstellung nonencapsulated Unions.|
|[no_injected_text](no-injected-text.md)|Verhindert, dass den Compiler Einfügen von Code durch Verwendung des Attributs.|
|[nonbrowsable](nonbrowsable.md)|Gibt an, dass ein Schnittstellenmember nicht in einem Eigenschaftenbrowser angezeigt werden soll.|
|[noncreatable](noncreatable.md)|Definiert ein Objekt, das allein nicht instanziiert werden kann.|
|[nonextensible](nonextensible.md)|Gibt an, dass die `IDispatch` -Implementierung enthält nur die Eigenschaften und Methoden aufgeführt, die in der schnittstellenbeschreibung und können nicht zur Laufzeit zusätzliche Member erweitert werden.|
|[object](object-cpp.md)|Identifiziert eine benutzerdefinierte Schnittstelle an. gleichbedeutend mit benutzerdefinierten Attribut.|
|[odl](odl.md)|Gibt eine Schnittstelle als Schnittstelle Objekt Description Language (ODL).|
|[oleautomation](oleautomation.md)|Gibt an, dass eine Schnittstelle mit der Automatisierung kompatibel ist.|
|[Optionale](optional-cpp.md)|Gibt einen optionalen Parameter für eine Memberfunktion an.|
|[out](out-cpp.md)|Gibt die Zeigerparameter an, die von der aufgerufenen Prozedur an die aufrufende Prozedur zurückgegeben werden (vom Server an den Client).|
|[pointer_default](pointer-default.md)|Gibt das Standardattribut für die Zeiger für alle Zeiger, mit Ausnahme der obersten Ebene Zeigern, die angezeigt werden in der Parameterliste.|
|[pragma](pragma.md)|Gibt die angegebene Zeichenfolge verwendet werden, ohne die Anführungszeichen in der generierten IDL-Datei aus.|
|[progid](progid.md)|Gibt an, die ProgID für ein COM-Objekt.|
|[propget](propget.md)|Gibt eine Eigenschaft Accessorfunktion (Get).|
|[propputref](propputref.md)|Gibt eine eigenschaftseinstellungsfunktion an, die einen Verweis anstelle eines Werts verwendet.|
|[propput](propput.md)|Gibt eine Eigenschaftseinstellungsfunktion an.|
|[ptr](ptr.md)|Kennzeichnet einen Zeiger als vollständige Zeiger.|
|[public](public-cpp-attributes.md)|Wird sichergestellt, dass eine Typdefinition in der Typbibliothek wird, auch wenn es nicht in der IDL-Datei verweist.|
|[range](range-cpp.md)|Gibt einen Bereich der zulässigen Werte für die Argumente oder Felder, deren Werte zur Laufzeit festgelegt werden.|
|[readonly](readonly-cpp.md)|Verhindert die Zuweisung zu einer Variablen.|
|[ref](ref-cpp.md)|Identifiziert einen Verweiszeiger an.|
|[requestedit](requestedit.md)|Gibt an, dass die Eigenschaft unterstützt die `OnRequestEdit` Benachrichtigung.|
|[restricted](restricted.md)|Gibt an, dass es sich bei einer Bibliothek oder einem Mitglied ein Modul, Schnittstelle oder Disp-Schnittstelle nicht beliebig aufgerufen werden kann.|
|[retval](retval.md)|Legt fest, den Parameter, der den Rückgabewert des Members empfängt.|
|[size_is](size-is.md)|Gibt an, die Größe des Arbeitsspeichers für Größe Zeiger zugewiesen, die Größe der Zeiger auf Zeiger, die Größe und Einzel- oder mehrdimensionale Arrays.|
|[source](source-cpp.md)|Gibt an, dass ein Member der Klasse, Eigenschaft oder Methode eine Ereignisquelle ist.|
|[string](string-cpp.md)|Gibt an, dass das eindimensionale **Char**, **"wchar_t"**, `byte`, oder das entsprechende Array oder der Zeiger auf ein solches Array muss als Zeichenfolge behandelt werden.|
|[switch_is](switch-is.md)|Gibt den Ausdruck oder einen Bezeichner fungiert als die union kombiniert werden sollen, die die union-Member auswählt.|
|[switch_type](switch-type.md)|Gibt den Typ der Variablen als die union Discriminant verwendet.|
|[transmit_as](transmit-as.md)|Weist den Compiler dargestellt ein, die Client- und serveranwendungen bearbeiten zu können, müssen, mit einem übertragenen Typ zuordnen.|
|[uidefault](uidefault.md)|Gibt an, dass der Typinformationsmember das Standardelement für die Anzeige in der Benutzeroberfläche.|
|[unique](unique-cpp.md)|Gibt einen eindeutigen Zeiger.|
|[usesgetlasterror](usesgetlasterror.md)|Wird dem Aufrufer mitgeteilt, dass der Aufrufer bei wird ein Fehler beim Aufrufen dieser Funktion dann aufrufen kann `GetLastError` auf den Fehlercode abzurufen.|
|[uuid](uuid-cpp-attributes.md)|Gibt die eindeutige ID für eine Klasse oder Schnittstelle an.|
|[v1_enum](v1-enum.md)|Wird angewiesen, der angegebene enumerierten Typ als eine 32-Bit-Entität und nicht als der Standardwert 16-Bit-übertragen werden.|
|[vararg](vararg.md)|Gibt an, dass die Funktion eine Variable Anzahl von Argumenten akzeptieren.|
|[vi_progid](vi-progid.md)|Gibt eine Art versionsunabhängige Programm-ID an.|
|[wire_marshal](wire-marshal.md)|Gibt einen Datentyp, der für die Übertragung anstelle eines Typs anwendungsspezifische Daten verwendet wird.|

## <a name="see-also"></a>Siehe auch

[Attribute nach Gruppen](attributes-by-group.md)  
