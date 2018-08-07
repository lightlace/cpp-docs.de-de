---
title: Attribute | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- method attributes
- attributes [C++], reference topics
ms.assetid: b2313352-480d-488b-8c35-6242ffd3a549
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1850507b9d00ab717a2602d4e230968f5222f077
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39604280"
---
# <a name="method-attributes"></a>Methodenattribut
Die folgenden Attribute gelten für die Methoden in einer Klasse, Co-Klasse oder Schnittstelle.  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|[bindable](../windows/bindable.md)|Gibt an, dass die Eigenschaft die Datenbindung unterstützt.|  
|[call_as](../windows/call-as.md)|Aktiviert eine Funktion nicht remotefähige an eine remote-Funktion zugeordnet werden soll.|  
|[Benutzerdefinierte](../windows/custom-cpp.md)|Sie können Ihr eigenes Attribut definieren.|  
|[db_column](../windows/db-column.md)|Bindet eine angegebene Spalte auf das Rowset an.|  
|[db_command](../windows/db-command.md)|Erstellt einen OLE DB-Befehl.|  
|[db_param](../windows/db-param.md)|Ordnet die angegebenen Member-Variable mit einem Eingabe- oder ausgabeadapter-Parameter und Variablen begrenzt.|  
|[db_source](../windows/db-source.md)|Erstellt eine Verbindung mit einer Datenquelle.|  
|[db_table](../windows/db-table.md)|Öffnet eine OLE DB-Tabelle.|  
|[defaultbind](../windows/defaultbind.md)|Gibt an, die einfache, bindbare Eigenschaft, die das Objekt am besten darstellt.|  
|[defaultcollelem](../windows/defaultcollelem.md)|Für die Optimierung für Visual Basic-Code verwendet.|  
|[displaybind](../windows/displaybind.md)|Gibt eine Eigenschaft, die dem Benutzer als bindungsfähig angezeigt werden soll.|  
|[helpcontext](../windows/helpcontext.md)|Gibt eine Kontext-ID, mit dem die Benutzerinformationen zu diesem Element in der Hilfedatei.|  
|[helpfile](../windows/helpfile.md)|Legt den Namen der Hilfedatei für die Typbibliothek.|  
|[helpstring](../windows/helpstring.md)|Gibt eine Zeichenfolge an, die zum Beschreiben des Elements verwendet wird, auf das sie angewendet wird.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Gibt die ID des Hilfethemas in eine .hlp oder CHM-Datei an.|  
|[helpstringdll](../windows/helpstringdll.md)|Gibt den Namen der DLL zu verwenden, um die Suche nach Dokument (Lokalisierung) ausführen.|  
|[hidden](../windows/hidden.md)|Gibt an, dass das Element vorhanden ist, aber nicht in einem benutzerorientierten Browser angezeigt werden soll.|  
|[ID](../windows/id.md)|Gibt eine DISPID für eine Memberfunktion (eine Eigenschaft oder eine Methode, in eine Schnittstelle oder Disp-Schnittstelle).|  
|[immediatebind](../windows/immediatebind.md)|Gibt an, dass die Datenbank über alle Änderungen an einer Eigenschaft eines datengebundenen Objekts sofort benachrichtigt wird.|  
|[in](../windows/in-cpp.md)|Gibt an, dass ein Parameter, die von der aufrufenden Prozedur an die aufgerufene Prozedur übergeben werden.|  
|[local](../windows/local-cpp.md)|Ermöglicht Ihnen die Verwendung den MIDL-Compiler als ein Header-Generator, wenn in der Schnittstelle-Header verwendet. Bei Verwendung in einer einzelnen Funktion kennzeichnet eine lokale Prozedur, die für die keine Stubs generiert werden.|  
|[nonbrowsable](../windows/nonbrowsable.md)|Gibt an, dass ein Schnittstellenmember nicht in einem Eigenschaftenbrowser angezeigt werden soll.|  
|[propget](../windows/propget.md)|Gibt eine Eigenschaft Accessor-Funktion.|  
|[propput](../windows/propput.md)|Gibt eine Eigenschaften festlegende Funktion an.|  
|[propputref](../windows/propputref.md)|Gibt eine Eigenschaften festlegende Funktion an, die einen Verweis anstelle eines Werts verwendet.|  
|[ptr](../windows/ptr.md)|Kennzeichnet einen Zeiger als vollständige Zeiger.|  
|[range](../windows/range-cpp.md)|Gibt einen Bereich der zulässigen Werte für die Argumente oder Felder, deren Werte zur Laufzeit festgelegt werden.|  
|[requestedit](../windows/requestedit.md)|Gibt an, dass die Eigenschaft unterstützt die `OnRequestEdit` Benachrichtigung.|  
|[restricted](../windows/restricted.md)|Gibt an, dass ein Mitglied aus einem Modul, Schnittstelle oder Disp-Schnittstelle nicht beliebig aufgerufen werden kann.|  
|[satype](../windows/satype.md)|Gibt den Datentyp, der die `SAFEARRAY` Struktur.|  
|[source](../windows/source-cpp.md)|Gibt den Schnittstellen des Steuerelements nach Verbindungspunkten für eine Klasse an. Auf eine Eigenschaft oder Methode die `source` Attribut gibt an, dass das Element zurückgibt, ein Objekt oder eine Variante, die eine Ereignisquelle ist.|  
|[synchronize](../windows/synchronize.md)|Synchronisiert den Zugriff auf die Zielmethode.|  
|[vararg](../windows/vararg.md)|Gibt an, dass die Funktion eine Variable Anzahl von Argumenten akzeptieren.|  
  
## <a name="see-also"></a>Siehe auch  
 [Attribute nach Verwendung](../windows/attributes-by-usage.md)