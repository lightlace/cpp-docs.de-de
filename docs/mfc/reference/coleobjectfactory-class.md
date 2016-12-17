---
title: "COleObjectFactory Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "COleObjectFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "class factories, COleObjectFactory class"
  - "COleObjectFactory class"
  - "Objekterstellung, OLE-Objekte"
  - "Objekte [C++], Erstellen von OLE"
  - "OLE class factory"
  - "OLE-Objekte"
  - "OLE-Objekte, Erstellen"
  - "OLE, class factory"
ms.assetid: ab179c1e-4af2-44aa-a576-37c48149b427
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# COleObjectFactory Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert die OLE\-Klassenfactory, die OLE\-Objekte wie Server, Automatisierungsobjekte und Dokumente erstellt.  
  
## Syntax  
  
```  
class COleObjectFactory : public CCmdTarget  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleObjectFactory::COleObjectFactory](../Topic/COleObjectFactory::COleObjectFactory.md)|Erstellt ein `COleObjectFactory`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleObjectFactory::GetClassID](../Topic/COleObjectFactory::GetClassID.md)|Gibt die OLE\-Klassen\-ID der Objekte zurück, die diese Factory erstellt.|  
|[COleObjectFactory::IsLicenseValid](../Topic/COleObjectFactory::IsLicenseValid.md)|Bestimmt, ob die Lizenz des Steuerelements gültig ist.|  
|[COleObjectFactory::IsRegistered](../Topic/COleObjectFactory::IsRegistered.md)|Gibt an, ob die Objektfactory mit den OLE\-Systemen\-DLL registriert wird.|  
|[COleObjectFactory::Register](../Topic/COleObjectFactory::Register.md)|Registriert diese Objektfactory mit den OLE\-Systemen\-DLL.|  
|[COleObjectFactory::RegisterAll](../Topic/COleObjectFactory::RegisterAll.md)|Registriert Objektfactorys aller Anwendung mit OLE\-Systemen\-DLL.|  
|[COleObjectFactory::Revoke](../Topic/COleObjectFactory::Revoke.md)|Widerruft die Registrierung dieser Objektfactorys mit den OLE\-Systemen\-DLL.|  
|[COleObjectFactory::RevokeAll](../Topic/COleObjectFactory::RevokeAll.md)|Widerruft der Objekt\-Factorys einer Anwendung die Registrierungen mit den OLE\-Systemen\-DLL.|  
|[COleObjectFactory::UnregisterAll](../Topic/COleObjectFactory::UnregisterAll.md)|Hebt alle Objektfactorys einer Anwendung Registrierung auf.|  
|[COleObjectFactory::UpdateRegistry](../Topic/COleObjectFactory::UpdateRegistry.md)|Registriert diese Objektfactory mit der OLE\-Systemregistrierung.|  
|[COleObjectFactory::UpdateRegistryAll](../Topic/COleObjectFactory::UpdateRegistryAll.md)|Registriert Objektfactorys aller Anwendung mit der OLE\-Systemregistrierung.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleObjectFactory::GetLicenseKey](../Topic/COleObjectFactory::GetLicenseKey.md)|Fordert einen eindeutigen Schlüssel aus der DLL des Steuerelements.|  
|[COleObjectFactory::OnCreateObject](../Topic/COleObjectFactory::OnCreateObject.md)|Aufgerufen durch das Framework, um ein neues Objekt vom Typ dieser Factory zu erstellen.|  
|[COleObjectFactory::VerifyLicenseKey](../Topic/COleObjectFactory::VerifyLicenseKey.md)|Überprüft, ob die Schlüssel, die im \- Steuerelement eingebettet ist, die Schlüssel entspricht, die im Container eingebettet ist.|  
|[COleObjectFactory::VerifyUserLicense](../Topic/COleObjectFactory::VerifyUserLicense.md)|Überprüft, ob das Steuerelement für Entwurfszeitverwendung lizenziert wird.|  
  
## Hinweise  
 Die Klasse verfügt über `COleObjectFactory`\-Memberfunktionen für das Ausführen der folgenden Funktionen:  
  
-   Verwalten der Registrierung der Objekte.  
  
-   Das OLE\-Systemregister sowie die Ablaufregistrierung aktualisieren, die OLE informiert, dass Objekte ausgeführt und bereit sind, Nachrichten zu empfangen.  
  
-   Lizenzierung erzwingen, durch Verwendung des Steuerelements zur Entwurfszeit einschränken zu den lizenzierten Entwicklern und zu den lizenzierten Anwendungen zur Laufzeit.  
  
-   Registrieren von Steuerobjektfactorys mit der OLE\-Systemregistrierung.  
  
 Weitere Informationen zur Objekterstellung, finden Sie in Artikel [Datenobjekte und Datenquellen \(OLE\)](../../mfc/data-objects-and-data-sources-ole.md) und [Datenobjekte und Datenquellen: Erstellen und Zerstörung](../../mfc/data-objects-and-data-sources-creation-and-destruction.md).  Weitere Informationen zur Registrierung, finden Sie im Artikel [Registrierung](../../mfc/registration.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleObjectFactory`  
  
## Anforderungen  
 **Header:**  afxdisp.h  
  
## Siehe auch  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleTemplateServer Class](../../mfc/reference/coletemplateserver-class.md)