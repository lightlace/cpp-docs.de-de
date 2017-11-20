---
title: COM-Attribute | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- attributes [C++], reference topics
- attributes [COM]
- COM, attributes
ms.assetid: 52a5dd70-e8be-4bba-afd6-daf90fe689a0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f9cd3657426a2a51a582ab695376287a3e975056
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="com-attributes"></a>COM-Attribute
Die COM-Attribute fügen Code um mehrere Bereiche von COM-Entwicklung und .NET Framework common Language Runtime-Entwicklung zu unterstützen. Diese Bereiche reichen von benutzerdefinierten Implementierung und Unterstützung von vorhandenen Schnittstellen zur Unterstützung von vordefinierten Eigenschaften, Methoden und Ereignisse. Darüber hinaus kann die Unterstützung für zusammengesetzte und ActiveX-Steuerelement Implementierung gefunden werden.  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|[Aggregierbar](../windows/aggregatable.md)|Gibt an, dass ein Steuerelement durch ein anderes Steuerelement aggregiert werden kann.|  
|[Aggregate](../windows/aggregates.md)|Gibt an, dass ein Steuerelement die Zielklasse aggregiert.|  
|[coclass](../windows/coclass.md)|Erstellt ein COM-Objekt, die eine COM-Schnittstelle implementieren können.|  
|[COM_INTERFACE_ENTRY](../windows/com-interface-entry-cpp.md)|Fügt einen Eintrag für die Schnittstelle zu einer COM-Zuordnung.|  
|[implements_category](../windows/implements-category.md)|Gibt an, für die Klasse implementierten Komponentenkategorien.|  
|[progid](../windows/progid.md)|Definiert die ProgID für ein Steuerelement an.|  
|[rdx](../windows/rdx.md)|Erstellt oder ändert einen Registrierungsschlüssel.|  
|[registration_script](../windows/registration-script.md)|Führt die angegebene Registrierungsskript aus.|  
|[requires_category](../windows/requires-category.md)|Gibt die erforderliche Komponente von Kategorien für die Klasse an.|  
|[support_error_info](../windows/support-error-info.md)|Unterstützt die Fehlerberichterstattung für das Zielobjekt.|  
|[synchronize](../windows/synchronize.md)|Synchronisiert den Zugriff auf eine Methode an.|  
|[Threading](../windows/threading-cpp.md)|Gibt das Threadingmodell für ein COM-Objekt.|  
|[vi_progid](../windows/vi-progid.md)|Definiert eine versionsunabhängige ProgID eines Steuerelements an.|  
  
## <a name="see-also"></a>Siehe auch  
 [Attribute nach Gruppen](../windows/attributes-by-group.md)