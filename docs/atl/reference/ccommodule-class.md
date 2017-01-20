---
title: "CComModule Class"
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
  - "CComModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComModule class"
  - "DLL modules [C++], ATL"
ms.assetid: f5face2c-8fd8-40e6-9ec3-54ab74701769
caps.latest.revision: 23
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CComModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ab ATL 7.0 wird `CComModule` veraltet: finden Sie unter [ATL\-Modul\-Klassen](../../atl/atl-module-classes.md) für weitere Details.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
class CComModule : public _ATL_MODULE  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CComModule::GetClassObject](../Topic/CComModule::GetClassObject.md)|Erstellt ein Objekt eines angegebenen CLSID.  Für nur DLLs.|  
|[CComModule::GetModuleInstance](../Topic/CComModule::GetModuleInstance.md)|Gibt `m_hInst` zurück.|  
|[CComModule::GetResourceInstance](../Topic/CComModule::GetResourceInstance.md)|Gibt `m_hInstResource` zurück.|  
|[CComModule::GetTypeLibInstance](../Topic/CComModule::GetTypeLibInstance.md)|Gibt `m_hInstTypeLib` zurück.|  
|[CComModule::Init](../Topic/CComModule::Init.md)|Initialisiert Datenmember.|  
|[CComModule::RegisterClassHelper](../Topic/CComModule::RegisterClassHelper.md)|Gibt Standardklassenregistrierung eines Objekts in der Systemregistrierung ein.|  
|[CComModule::RegisterClassObjects](../Topic/CComModule::RegisterClassObjects.md)|Registriert das Klassenobjekt.  Nur für EXE\-Anwendungen.|  
|[CComModule::RegisterServer](../Topic/CComModule::RegisterServer.md)|Aktualisiert die Systemregistrierung für jedes Objekt in der Objektzuordnung.|  
|[CComModule::RegisterTypeLib](../Topic/CComModule::RegisterTypeLib.md)|Registriert eine Typbibliothek.|  
|[CComModule::RevokeClassObjects](../Topic/CComModule::RevokeClassObjects.md)|Widerruft das Klassenobjekt.  Nur für EXE\-Anwendungen.|  
|[CComModule::Term](../Topic/CComModule::Term.md)|Befreit Datenmember.|  
|[CComModule::UnregisterClassHelper](../Topic/CComModule::UnregisterClassHelper.md)|Entfernt Standardklassenregistrierung eines Objekts aus der Systemregistrierung.|  
|[CComModule::UnregisterServer](../Topic/CComModule::UnregisterServer.md)|Hebt jedes Objekt in der Registrierung Objektzuordnung auf.|  
|[CComModule::UpdateRegistryClass](../Topic/CComModule::UpdateRegistryClass.md)|Register oder hebt Standardklassenregistrierung eines Objekts Registrierung auf.|  
|[CComModule::UpdateRegistryFromResourceD](../Topic/CComModule::UpdateRegistryFromResourceD.md)|Führt das Skript, das in einer angegebenen Ressource enthalten ist, ein Objekt zu registrieren oder deren Registrierung aufzuheben.|  
|[CComModule::UpdateRegistryFromResourceS](../Topic/CComModule::UpdateRegistryFromResourceS.md)|Statisch Links zur ATL\-Registrierungs\-Komponente.  Führt das Skript, das in einer angegebenen Ressource enthalten ist, ein Objekt zu registrieren oder deren Registrierung aufzuheben.|  
  
### Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CComModule::m\_csObjMap](../Topic/CComModule::m_csObjMap.md)|Ensures synchronisierte Zugriff auf Objektzuordnungsinformationen.|  
|[CComModule::m\_csTypeInfoHolder](../Topic/CComModule::m_csTypeInfoHolder.md)|Ensures synchronisierte Zugriff auf Typbibliotheksinformationen.|  
|[CComModule::m\_csWindowCreate](../Topic/CComModule::m_csWindowCreate.md)|Ensures synchronisierte Zugriff auf Fensterklasseninformationen und \-statischen Daten, die während der Fenstererstellung verwendet wurden.|  
|[CComModule::m\_hInst](../Topic/CComModule::m_hInst.md)|Enthält das Handle zur Modulinstanz.|  
|[CComModule::m\_hInstResource](../Topic/CComModule::m_hInstResource.md)|Standardmäßig enthält das Handle zur Modulinstanz.|  
|[CComModule::m\_hInstTypeLib](../Topic/CComModule::m_hInstTypeLib.md)|Standardmäßig enthält das Handle zur Modulinstanz.|  
|[CComModule::m\_pObjMap](../Topic/CComModule::m_pObjMap.md)|Punkte zur Objektzuordnung, die vom Modul verwaltet wird, führen als Beispiel.|  
  
## Hinweise  
  
> [!NOTE]
>  Diese Klasse ist veraltet und die ATL\-Codegenerierungsassistenten verwenden nun die [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) und [CAtlModule](../../atl/reference/catlmodule-class.md) abgeleiteten Klassen.  Siehe [ATL\-Modul\-Klassen](../../atl/atl-module-classes.md) weitere Informationen.  Die Informationen, die erfolgreich ist, sind für die Verwendung mit Anwendungen, die mit älteren Versionen von ATL erstellt werden.  `CComModule` ist weiterhin Teil ATL für rückwärts Funktion.  
  
 `CComModule` implementiert ein COM\-Server\-Modul und ermöglicht einem Client, um auf die Komponenten des Moduls zuzugreifen.  `CComModule` unterstützt Module DLL \(prozessintern\) und EXE\-Datei \(lokal\).  
  
 Eine `CComModule`\-Instanz verwendet eine Objektzuordnung, um einen Satz von Klassenobjektdefinitionen beizubehalten.  Diese Objektzuordnung wird als Array `_ATL_OBJMAP_ENTRY`\-Strukturen implementiert und Informationen für enthält:  
  
-   Objektbeschreibungen in der Systemregistrierung eingeben und Entfernen von.  
  
-   Instanziieren von Objekten durch eine Klassenfactory.  
  
-   Herstellen von Verbindungen zwischen einem Client und dem übergeordneten in der Komponente.  
  
-   Ausführen der Verwaltung der Lebensdauer der Klassenobjekte.  
  
 Wenn Sie den ATL Anwendungs\-Assistenten COM ausführen, generiert der Assistent automatisch `_Module`, eine globale Instanz von `CComModule` oder eine Klasse, die davon abgeleitet wird.  Weitere Informationen zu den ATL\-Projekt\-Assistenten, finden Sie im Artikel [Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md).  
  
 Zusätzlich zu `CComModule` stellt ATL [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), das ein ApartmentModell Modul für EXE\-Dateien und Windows\-Dienste implementiert.  Leiten Sie das Modul von `CComAutoThreadModule`, wenn Sie Objekte in mehreren Apartments erstellen möchten.  
  
## Vererbungshierarchie  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CComModule`  
  
## Anforderungen  
 `Header:` atlbase.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)