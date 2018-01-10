---
title: Methodenattribute | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- method attributes
- attributes [C++], reference topics
ms.assetid: b2313352-480d-488b-8c35-6242ffd3a549
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f2413543e7638f47db13799e0549a415ee92c1c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="method-attributes"></a>Methodenattribut
Die folgenden Attribute gelten für die Methoden in einer Klasse, Co-Klasse oder Schnittstelle.  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|[bindable](../windows/bindable.md)|Gibt an, dass die Eigenschaft die Datenbindung unterstützt.|  
|[call_as](../windows/call-as.md)|Ermöglicht es einer nicht remotefähig-Funktion, um eine remote-Funktion zugeordnet werden.|  
|[benutzerdefinierte](../windows/custom-cpp.md)|Sie können Ihr eigenes Attribut definieren.|  
|[db_column](../windows/db-column.md)|Bindet eine angegebene Spalte auf das Rowset an.|  
|[db_command](../windows/db-command.md)|Erstellt einen OLE DB-Befehl.|  
|[db_param](../windows/db-param.md)|Ordnet die angegebene Membervariable ein Eingabe- oder Ausgabespalte-Parameter und begrenzt die Variable.|  
|[db_source](../windows/db-source.md)|Erstellt eine Verbindung mit einer Datenquelle.|  
|[db_table](../windows/db-table.md)|Öffnet eine OLE DB-Tabelle.|  
|[defaultbind](../windows/defaultbind.md)|Gibt an, die einfache, bindbare Eigenschaft, die das Objekt am besten darstellt.|  
|[defaultcollelem](../windows/defaultcollelem.md)|Zur Optimierung der Visual Basic-Code verwendet.|  
|[displaybind](../windows/displaybind.md)|Gibt eine Eigenschaft, die für den Benutzer als bindbar angezeigt werden sollen.|  
|[helpcontext](../windows/helpcontext.md)|Gibt eine Kontext-ID, mit dem die Benutzerinformationen zu diesem Element in der Hilfedatei.|  
|[helpfile](../windows/helpfile.md)|Legt den Namen der Hilfedatei für eine Typbibliothek.|  
|[helpstring](../windows/helpstring.md)|Gibt eine Zeichenfolge, die verwendet wird, um das Element zu beschreiben, auf dem es angewendet.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Gibt die ID des Hilfethemas in einer HLP oder CHM-Datei an.|  
|[helpstringdll](../windows/helpstringdll.md)|Gibt den Namen der DLL zu verwenden, um das Dokument Zeichenfolgensuche (Lokalisierung) ausführen.|  
|[hidden](../windows/hidden.md)|Gibt an, dass das Element vorhanden ist, aber nicht in einem Browser benutzerorientierte angezeigt werden soll.|  
|[ID](../windows/id.md)|Gibt eine DISPID für eine Memberfunktion (eine Eigenschaft oder eine Methode in einer Schnittstelle oder Disp-Schnittstelle).|  
|[immediatebind](../windows/immediatebind.md)|Gibt an, die Datenbank sofort aller Änderungen an eine Eigenschaft eines Objekts von datengebundenen benachrichtigt wird.|  
|[in](../windows/in-cpp.md)|Gibt an, dass ein Parameter von der aufrufenden Prozedur an die aufgerufene Prozedur übergeben werden.|  
|[lokale](../windows/local-cpp.md)|Können Sie die MIDL-Compiler als bei der Verwendung in der Schnittstelle Header einen Header-Generator zu verwenden. Wenn in einer einzelnen Funktion verwendet wird, kennzeichnet eine lokale Prozedur für die keine Stubs generiert werden.|  
|[nonbrowsable](../windows/nonbrowsable.md)|Gibt an, dass ein Schnittstellenmember nicht in einem Eigenschaftenbrowser angezeigt werden soll.|  
|[propget](../windows/propget.md)|Gibt eine Eigenschaft Accessor-Funktion.|  
|[propput](../windows/propput.md)|Gibt eine Eigenschaften festlegende Funktion an.|  
|[propputref](../windows/propputref.md)|Gibt eine Eigenschaften festlegende Funktion, die einen Verweis anstelle eines Werts verwendet.|  
|[ptr](../windows/ptr.md)|Kennzeichnet einen Zeiger als vollständige Zeiger.|  
|[Bereich](../windows/range-cpp.md)|Gibt einen Bereich der zulässigen Werte für die Argumente oder Felder, deren Werte zur Laufzeit festgelegt werden.|  
|[requestedit](../windows/requestedit.md)|Gibt an, dass die Eigenschaft unterstützt die **OnRequestEdit** Benachrichtigung.|  
|[restricted](../windows/restricted.md)|Gibt an, dass ein Mitglied aus einem Modul, Schnittstelle oder Disp-Schnittstelle kann nicht nach dem Zufallsprinzip aufgerufen werden.|  
|[satype](../windows/satype.md)|Gibt den Datentyp, der die **SAFEARRAY** Struktur.|  
|[Datenquelle](../windows/source-cpp.md)|Gibt das Steuerelement-Schnittstellen für Verbindungspunkte für eine Klasse an. Auf eine Eigenschaft oder Methode die **Quelle** Attribut gibt an, dass das Element zurückgibt, ein Objekt oder eine Variante, die Quelle von Ereignissen ist.|  
|[synchronize](../windows/synchronize.md)|Synchronisiert den Zugriff auf die Zielmethode.|  
|[vararg](../windows/vararg.md)|Gibt an, dass die Funktion eine Variable Anzahl von Argumenten akzeptieren.|  
  
## <a name="see-also"></a>Siehe auch  
 [Attribute nach Verwendung](../windows/attributes-by-usage.md)