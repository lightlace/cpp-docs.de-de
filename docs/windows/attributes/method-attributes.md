---
title: Attribute (C++-COM)
ms.date: 10/02/2018
helpviewer_keywords:
- method attributes
- attributes [C++/CLI], reference topics
ms.assetid: b2313352-480d-488b-8c35-6242ffd3a549
ms.openlocfilehash: aa67d45dfc0fadd300caeaaeb8a7c25bb1c38bcb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409174"
---
# <a name="method-attributes"></a>Methodenattribut

Die folgenden Attribute gelten für die Methoden in einer Klasse, Co-Klasse oder Schnittstelle.

|Attribut|Beschreibung|
|---------------|-----------------|
|[bindable](bindable.md)|Gibt an, dass die Eigenschaft die Datenbindung unterstützt.|
|[call_as](call-as.md)|Aktiviert eine Funktion nicht remotefähige an eine remote-Funktion zugeordnet werden soll.|
|[custom](custom-cpp.md)|Sie können Ihr eigenes Attribut definieren.|
|[db_column](db-column.md)|Bindet eine angegebene Spalte auf das Rowset an.|
|[db_command](db-command.md)|Erstellt einen OLE DB-Befehl.|
|[db_param](db-param.md)|Ordnet die angegebenen Member-Variable mit einem Eingabe- oder ausgabeadapter-Parameter und Variablen begrenzt.|
|[db_source](db-source.md)|Erstellt eine Verbindung mit einer Datenquelle.|
|[db_table](db-table.md)|Öffnet eine OLE DB-Tabelle.|
|[defaultbind](defaultbind.md)|Gibt an, die einfache, bindbare Eigenschaft, die das Objekt am besten darstellt.|
|[defaultcollelem](defaultcollelem.md)|Für die Optimierung für Visual Basic-Code verwendet.|
|[displaybind](displaybind.md)|Gibt eine Eigenschaft, die dem Benutzer als bindungsfähig angezeigt werden soll.|
|[helpcontext](helpcontext.md)|Gibt eine Kontext-ID, mit dem die Benutzerinformationen zu diesem Element in der **Hilfe** Datei.|
|[helpfile](helpfile.md)|Legt den Namen der der **Hilfe** -Datei für eine Typbibliothek.|
|[helpstring](helpstring.md)|Gibt eine Zeichenfolge an, die zum Beschreiben des Elements verwendet wird, auf das sie angewendet wird.|
|[helpstringcontext](helpstringcontext.md)|Gibt die ID des Hilfethemas in eine .hlp oder CHM-Datei an.|
|[helpstringdll](helpstringdll.md)|Gibt den Namen der DLL zu verwenden, um die Suche nach Dokument (Lokalisierung) ausführen.|
|[hidden](hidden.md)|Gibt an, dass das Element vorhanden ist, aber nicht in einem benutzerorientierten Browser angezeigt werden soll.|
|[ID](id.md)|Gibt eine DISPID für eine Memberfunktion (eine Eigenschaft oder eine Methode, in eine Schnittstelle oder Disp-Schnittstelle).|
|[immediatebind](immediatebind.md)|Gibt an, dass die Datenbank über alle Änderungen an einer Eigenschaft eines datengebundenen Objekts sofort benachrichtigt wird.|
|[in](in-cpp.md)|Gibt an, dass ein Parameter, die von der aufrufenden Prozedur an die aufgerufene Prozedur übergeben werden.|
|[local](local-cpp.md)|Ermöglicht Ihnen die Verwendung den MIDL-Compiler als ein Header-Generator, wenn in der Schnittstelle-Header verwendet. Bei Verwendung in einer einzelnen Funktion kennzeichnet eine lokale Prozedur, die für die keine Stubs generiert werden.|
|[nonbrowsable](nonbrowsable.md)|Gibt an, dass ein Schnittstellenmember nicht in einem Eigenschaftenbrowser angezeigt werden soll.|
|[propget](propget.md)|Gibt eine Eigenschaft Accessor-Funktion.|
|[propput](propput.md)|Gibt eine Eigenschaften festlegende Funktion an.|
|[propputref](propputref.md)|Gibt eine Eigenschaften festlegende Funktion an, die einen Verweis anstelle eines Werts verwendet.|
|[ptr](ptr.md)|Kennzeichnet einen Zeiger als vollständige Zeiger.|
|[range](range-cpp.md)|Gibt einen Bereich der zulässigen Werte für die Argumente oder Felder, deren Werte zur Laufzeit festgelegt werden.|
|[requestedit](requestedit.md)|Gibt an, dass die Eigenschaft die `OnRequestEdit`-Benachrichtigung unterstützt.|
|[restricted](restricted.md)|Gibt an, dass ein Mitglied aus einem Modul, Schnittstelle oder Disp-Schnittstelle nicht beliebig aufgerufen werden kann.|
|[satype](satype.md)|Gibt den Datentyp, der die `SAFEARRAY` Struktur.|
|[source](source-cpp.md)|Gibt den Schnittstellen des Steuerelements nach Verbindungspunkten für eine Klasse an. Auf eine Eigenschaft oder Methode die `source` Attribut gibt an, dass das Element zurückgibt, ein Objekt oder eine Variante, die eine Ereignisquelle ist.|
|[synchronize](synchronize.md)|Synchronisiert den Zugriff auf die Zielmethode.|
|[vararg](vararg.md)|Gibt an, dass die Funktion eine Variable Anzahl von Argumenten akzeptieren.|

## <a name="see-also"></a>Siehe auch

[Attribute nach Verwendung](attributes-by-usage.md)