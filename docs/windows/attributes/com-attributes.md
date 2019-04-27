---
title: COM-Attribute
ms.date: 10/03/2018
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- attributes [COM]
- COM, attributes
ms.assetid: 52a5dd70-e8be-4bba-afd6-daf90fe689a0
ms.openlocfilehash: eb87d3861c6b3066cf482108e2ce2243c8196093
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62148470"
---
# <a name="com-attributes"></a>COM-Attribute

Die COM-Attribute fügen Code um zahlreiche Bereiche von COM-Entwicklung und .NET Framework common Language Runtime-Entwicklung zu unterstützen. Diese Bereiche reichen von benutzerdefinierten schnittstellenimplementierung und Unterstützung von vorhandenen Schnittstellen für die Unterstützung von vordefinierten Eigenschaften, Methoden und Ereignisse. Darüber hinaus Unterstützung für zusammengesetzte und Implementierung des ActiveX-Steuerelements finden.

|Attribut|Beschreibung|
|---------------|-----------------|
|[Aggregierbar](aggregatable.md)|Gibt an, dass ein Steuerelement durch ein anderes Steuerelement aggregiert werden kann.|
|[Aggregate](aggregates.md)|Gibt an, dass ein Steuerelement die Zielklasse aggregiert.|
|[coclass](coclass.md)|Erstellt ein COM-Objekt, die eine COM-Schnittstelle implementieren können.|
|[com_interface_entry](com-interface-entry-cpp.md)|Fügt einen Eintrag für die Schnittstelle eine COM-Zuordnung.|
|[implements_category](implements-category.md)|Gibt an, für die Klasse implementierten Komponentenkategorien.|
|[progid](progid.md)|Definiert die ProgID für ein Steuerelement an.|
|[rdx](rdx.md)|Erstellt oder ändert einen Registrierungsschlüssel.|
|[registration_script](registration-script.md)|Führt die angegebene Registrierungsskript aus.|
|[requires_category](requires-category.md)|Gibt Kategorien von erforderliche Komponente für die Klasse an.|
|[support_error_info](support-error-info.md)|Unterstützt die Windows-Fehlerberichterstattung für das Zielobjekt.|
|[synchronize](synchronize.md)|Synchronisiert den Zugriff auf eine Methode.|
|[threading](threading-cpp.md)|Gibt das Threadingmodell für eine COM-Objekt.|
|[vi_progid](vi-progid.md)|Definiert eine versionsunabhängige Programm-ID für ein Steuerelement an.|

## <a name="see-also"></a>Siehe auch

[Attribute nach Gruppen](attributes-by-group.md)