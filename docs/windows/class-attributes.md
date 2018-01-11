---
title: -Klasse Attribute | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- attributes [C++], class attributes
- class attributes
ms.assetid: fad04ea1-d8ff-46d4-bb42-2b4500a6ab60
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: afc3f277170dbbdf92f280d341bffb042ab70af2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="class-attributes"></a>Klassenattribute
Die folgenden Attribute gelten für die [Klasse](../cpp/class-cpp.md) C++-Schlüsselwort.  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|[Aggregierbar](../windows/aggregatable.md)|Gibt an, dass die Klasse Aggregation unterstützt.|  
|[Aggregate](../windows/aggregates.md)|Gibt an, dass ein Steuerelement die Zielklasse aggregiert.|  
|[appobject](../windows/appobject.md)|Identifiziert die Co-Klasse als ein Anwendungsobjekt, die mit einer vollständigen .exe-Anwendung verknüpft ist, und gibt an, dass die Funktionen und Eigenschaften der Co-Klasse in diese Typbibliothek global verfügbar sind.|  
|[case](../windows/case-cpp.md)|Verwendet die [Switch_type](../windows/switch-type.md) Attribut in einer Union.|  
|[coclass](../windows/coclass.md)|Erstellt ein ActiveX-Steuerelement.|  
|[COM_INTERFACE_ENTRY](../windows/com-interface-entry-cpp.md)|Fügt einen Eintrag für die Schnittstelle zu einer COM-Zuordnung.|  
|[Steuerelement](../windows/control.md)|Gibt an, dass der benutzerdefinierte Datentyp eines Steuerelements.|  
|[benutzerdefinierte](../windows/custom-cpp.md)|Sie können Ihr eigenes Attribut definieren.|  
|[db_command](../windows/db-command.md)|Erstellt einen OLE DB-Befehl.|  
|[db_param](../windows/db-param.md)|Ordnet die angegebene Membervariable ein Eingabe- oder Ausgabespalte-Parameter und begrenzt die Variable.|  
|[db_source](../windows/db-source.md)|Erstellt eine Verbindung mit einer Datenquelle.|  
|[db_table](../windows/db-table.md)|Öffnet eine OLE DB-Tabelle.|  
|[default](../windows/default-cpp.md)|Gibt an, dass die benutzerdefinierte Schnittstelle oder Disp-Schnittstelle innerhalb einer Co-Klasse die Standard-Programmierschnittstelle darstellt.|  
|[defaultvtable](../windows/defaultvtable.md)|Definiert eine Schnittstelle als die Vtable Standardschnittstelle für ein Steuerelement an.|  
|[event_receiver](../windows/event-receiver.md)|Erstellt einen Ereignisempfänger.|  
|[event_source](../windows/event-source.md)|Erstellt eine Ereignisquelle.|  
|[helpcontext](../windows/helpcontext.md)|Gibt eine Kontext-ID, mit dem die Benutzerinformationen zu diesem Element in der Hilfedatei.|  
|[helpfile](../windows/helpfile.md)|Legt den Namen der Hilfedatei für eine Typbibliothek.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Gibt die ID des Hilfethemas in einer HLP oder CHM-Datei an.|  
|[helpstring](../windows/helpstring.md)|Gibt eine Zeichenfolge, die verwendet wird, um das Element zu beschreiben, auf dem es angewendet.|  
|[hidden](../windows/hidden.md)|Gibt an, dass das Element vorhanden ist, aber nicht in einem Browser benutzerorientierte angezeigt werden soll.|  
|[implementiert](../windows/implements-cpp.md)|Gibt die Dispatchschnittstellen, die Mitglieder der IDL-Co-Klasse werden erzwungen werden.|  
|[implements_category](../windows/implements-category.md)|Gibt an, für die Klasse implementierten Komponentenkategorien.|  
|[Modul](../windows/module-cpp.md)|Definiert den Bibliotheksblock in der IDL-Datei.|  
|[noncreatable](../windows/noncreatable.md)|Definiert ein Objekt, das allein nicht instanziiert werden kann.|  
|[progid](../windows/progid.md)|Definiert die ProgID für ein Steuerelement an.|  
|[registration_script](../windows/registration-script.md)|Führt die angegebene Registrierungsskript aus.|  
|[requestedit](../windows/requestedit.md)|Gibt an, dass die Eigenschaft unterstützt die **OnRequestEdit** Benachrichtigung.|  
|[Datenquelle](../windows/source-cpp.md)|Gibt das Steuerelement-Schnittstellen für Verbindungspunkte für eine Klasse an. Auf eine Eigenschaft oder Methode die **Quelle** Attribut gibt an, dass das Element zurückgibt, ein Objekt oder eine Variante, die Quelle von Ereignissen ist.|  
|[support_error_info](../windows/support-error-info.md)|Unterstützt die Fehlerberichterstattung für das Zielobjekt.|  
|[Threading](../windows/threading-cpp.md)|Gibt das Threadingmodell für ein Steuerelement an.|  
|[UUID](../windows/uuid-cpp-attributes.md)|Gibt die eindeutige ID für eine Klasse oder Schnittstelle an.|  
|[version](../windows/version-cpp.md)|Identifiziert eine bestimmte Version mehrere Versionen einer Klasse.|  
|[vi_progid](../windows/vi-progid.md)|Gibt eine versionsunabhängige Form der ProgID an.|  
  
## <a name="see-also"></a>Siehe auch  
 [Attribute nach Verwendung](../windows/attributes-by-usage.md)