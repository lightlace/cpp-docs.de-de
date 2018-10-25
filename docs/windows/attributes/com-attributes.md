---
title: COM-Attribute | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- attributes [COM]
- COM, attributes
ms.assetid: 52a5dd70-e8be-4bba-afd6-daf90fe689a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2aa88f88fe26b96202f2a917bddf5c8bb07c0d3c
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071127"
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