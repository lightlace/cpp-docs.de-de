---
title: Klasse von Attributen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], class attributes
- class attributes
ms.assetid: fad04ea1-d8ff-46d4-bb42-2b4500a6ab60
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0a2fe111028f952482dbd6b2eedebc157d39a9a4
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645174"
---
# <a name="class-attributes"></a>Klassenattribute
Die folgenden Attribute gelten für die [Klasse](../cpp/class-cpp.md) C++-Schlüsselwort.  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|[Aggregierbar](../windows/aggregatable.md)|Gibt an, dass die Klasse Aggregation unterstützt.|  
|[Aggregate](../windows/aggregates.md)|Gibt an, dass ein Steuerelement die Zielklasse aggregiert.|  
|[appobject](../windows/appobject.md)|Identifiziert die Co-Klasse als ein Anwendungsobjekt, das eine vollständige .exe-Anwendung zugeordnet ist, und gibt an, dass die Funktionen und Eigenschaften der Co-Klasse in diese Typbibliothek global verfügbar sind.|  
|[case](../windows/case-cpp.md)|Verwendung der [Switch_type](../windows/switch-type.md) Attribut in einer Union.|  
|[coclass](../windows/coclass.md)|Erstellt ein ActiveX-Steuerelement.|  
|[COM_INTERFACE_ENTRY](../windows/com-interface-entry-cpp.md)|Fügt einen Eintrag für die Schnittstelle eine COM-Zuordnung.|  
|[Steuerelement](../windows/control.md)|Gibt an, dass der benutzerdefinierte Typ eines Steuerelements.|  
|[Benutzerdefinierte](../windows/custom-cpp.md)|Sie können Ihr eigenes Attribut definieren.|  
|[db_command](../windows/db-command.md)|Erstellt einen OLE DB-Befehl.|  
|[db_param](../windows/db-param.md)|Ordnet die angegebenen Member-Variable mit einem Eingabe- oder ausgabeadapter-Parameter und Variablen begrenzt.|  
|[db_source](../windows/db-source.md)|Erstellt eine Verbindung mit einer Datenquelle.|  
|[db_table](../windows/db-table.md)|Öffnet eine OLE DB-Tabelle.|  
|[default](../windows/default-cpp.md)|Gibt an, dass die benutzerdefinierte Schnittstelle oder Disp-Schnittstelle innerhalb einer Co-Klasse die Standard-Programmierschnittstelle darstellt.|  
|[defaultvtable](../windows/defaultvtable.md)|Definiert eine Schnittstelle als die Vtable-Standardschnittstelle für ein Steuerelement an.|  
|[event_receiver](../windows/event-receiver.md)|Erstellt einen Ereignisempfänger an.|  
|[event_source](../windows/event-source.md)|Erstellt eine Ereignisquelle.|  
|[helpcontext](../windows/helpcontext.md)|Gibt eine Kontext-ID, mit dem die Benutzerinformationen zu diesem Element in der **Hilfe** Datei.|  
|[helpfile](../windows/helpfile.md)|Legt den Namen der Hilfedatei für die Typbibliothek.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Gibt die ID des Hilfethemas in eine .hlp oder CHM-Datei an.|  
|[helpstring](../windows/helpstring.md)|Gibt eine Zeichenfolge an, die zum Beschreiben des Elements verwendet wird, auf das sie angewendet wird.|  
|[hidden](../windows/hidden.md)|Gibt an, dass das Element vorhanden ist, aber nicht in einem benutzerorientierten Browser angezeigt werden soll.|  
|[Implementiert](../windows/implements-cpp.md)|Gibt die Dispatch-Schnittstellen, die erzwungen werden, um die IDL-Co-Klasse angehören.|  
|[implements_category](../windows/implements-category.md)|Gibt an, für die Klasse implementierten Komponentenkategorien.|  
|[Modul](../windows/module-cpp.md)|Definiert den Bibliotheksblock in der IDL-Datei.|  
|[noncreatable](../windows/noncreatable.md)|Definiert ein Objekt, das allein nicht instanziiert werden kann.|  
|[progid](../windows/progid.md)|Definiert die ProgID für ein Steuerelement an.|  
|[registration_script](../windows/registration-script.md)|Führt die angegebene Registrierungsskript aus.|  
|[requestedit](../windows/requestedit.md)|Gibt an, dass die Eigenschaft unterstützt die `OnRequestEdit` Benachrichtigung.|  
|[source](../windows/source-cpp.md)|Gibt den Schnittstellen des Steuerelements nach Verbindungspunkten für eine Klasse an. Auf eine Eigenschaft oder Methode die `source` Attribut gibt an, dass das Element ein Objekt zurückgibt oder `VARIANT` , die eine Quelle von Ereignissen.|  
|[support_error_info](../windows/support-error-info.md)|Unterstützt die Windows-Fehlerberichterstattung für das Zielobjekt.|  
|[Threading](../windows/threading-cpp.md)|Gibt das Threadingmodell für ein Steuerelement an.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Gibt die eindeutige ID für eine Klasse oder Schnittstelle an.|  
|[version](../windows/version-cpp.md)|Identifiziert eine bestimmte Version mehrere Versionen einer Klasse.|  
|[vi_progid](../windows/vi-progid.md)|Gibt eine Art versionsunabhängige Programm-ID an.|  
  
## <a name="see-also"></a>Siehe auch  
 [Attribute nach Verwendung](../windows/attributes-by-usage.md)