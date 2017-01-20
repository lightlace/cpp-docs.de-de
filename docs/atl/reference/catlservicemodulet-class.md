---
title: "CAtlServiceModuleT Class"
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
  - "ATL::CAtlServiceModuleT"
  - "ATL.CAtlServiceModuleT"
  - "CAtlServiceModuleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlServiceModuleT class"
ms.assetid: 8fc753ce-4a50-402b-9b4a-0a4ce5dd496c
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlServiceModuleT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert einen Dienst.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template <  
class T,  
UINT nServiceNameID   
>  
class ATL_NO_VTABLE CAtlServiceModuleT :  
public CAtlExeModuleT< T>  
```  
  
#### Parameter  
 `T`  
 Die Klasse wird von abgeleitet `CAtlServiceModuleT`.  
  
 *nServiceNameID*  
 Der Ressourcenbezeichner des Diensts.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlServiceModuleT::CAtlServiceModuleT](../Topic/CAtlServiceModuleT::CAtlServiceModuleT.md)|Der \-Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlServiceModuleT::Handler](../Topic/CAtlServiceModuleT::Handler.md)|Die Handlerroutine für den Dienst.|  
|[CAtlServiceModuleT::InitializeSecurity](../Topic/CAtlServiceModuleT::InitializeSecurity.md)|Stellt die Standardsicherheitseinstellungen für den Dienst bereit.|  
|[CAtlServiceModuleT::Install](../Topic/CAtlServiceModuleT::Install.md)|Installiert und erstellt den Dienst.|  
|[CAtlServiceModuleT::IsInstalled](../Topic/CAtlServiceModuleT::IsInstalled.md)|Bestätigt, dass der Dienst installiert wurde.|  
|[CAtlServiceModuleT::LogEvent](../Topic/CAtlServiceModuleT::LogEvent.md)|Schreibt in das Ereignisprotokoll.|  
|[CAtlServiceModuleT::OnContinue](../Topic/CAtlServiceModuleT::OnContinue.md)|Überschreiben Sie diese Methode, um den Dienst fortzusetzen.|  
|[CAtlServiceModuleT::OnInterrogate](../Topic/CAtlServiceModuleT::OnInterrogate.md)|Überschreiben Sie diese Methode, um den Dienst zu abfragen.|  
|[CAtlServiceModuleT::OnPause](../Topic/CAtlServiceModuleT::OnPause.md)|Überschreiben Sie diese Methode, um den Dienst angehalten.|  
|[CAtlServiceModuleT::OnShutdown](../Topic/CAtlServiceModuleT::OnShutdown.md)|Überschreiben Sie diese Methode, um den Dienst beenden|  
|[CAtlServiceModuleT::OnStop](../Topic/CAtlServiceModuleT::OnStop.md)|Überschreiben Sie diese Methode, um den Dienst zu beenden|  
|[CAtlServiceModuleT::OnUnknownRequest](../Topic/CAtlServiceModuleT::OnUnknownRequest.md)|Überschreiben Sie diese Methode, um unbekannte Anforderungen zum Dienst zu bearbeiten|  
|[CAtlServiceModuleT::ParseCommandLine](../Topic/CAtlServiceModuleT::ParseCommandLine.md)|Analysiert die Befehlszeile und führt ggf. Registrierung aus.|  
|[CAtlServiceModuleT::PreMessageLoop](../Topic/CAtlServiceModuleT::PreMessageLoop.md)|Diese Methode wird unmittelbar vor dem Eingeben der Nachrichtenschleife aufgerufen.|  
|[CAtlServiceModuleT::RegisterAppId](../Topic/CAtlServiceModuleT::RegisterAppId.md)|Registriert den Dienst in der Registrierung.|  
|[CAtlServiceModuleT::Run](../Topic/CAtlServiceModuleT::Run.md)|Leitet den Dienst.|  
|[CAtlServiceModuleT::ServiceMain](../Topic/CAtlServiceModuleT::ServiceMain.md)|Die Methode aufgerufen aus dem Dienststeuerungs\-Manager.|  
|[CAtlServiceModuleT::SetServiceStatus](../Topic/CAtlServiceModuleT::SetServiceStatus.md)|Aktualisiert den Dienststatus.|  
|[CAtlServiceModuleT::Start](../Topic/CAtlServiceModuleT::Start.md)|Aufgerufen durch `CAtlServiceModuleT::WinMain` wenn die Dienstanfänge.|  
|[CAtlServiceModuleT::Uninstall](../Topic/CAtlServiceModuleT::Uninstall.md)|Beenden und entfernt den Dienst.|  
|[CAtlServiceModuleT::Unlock](../Topic/CAtlServiceModuleT::Unlock.md)|Dekrementiert die Sperrenanzahl des Diensts.|  
|[CAtlServiceModuleT::UnregisterAppId](../Topic/CAtlServiceModuleT::UnregisterAppId.md)|Entfernt den Dienst aus der Registrierung.|  
|[CAtlServiceModuleT::WinMain](../Topic/CAtlServiceModuleT::WinMain.md)|Diese Methode implementiert den Code, der erforderlich ist, um den Dienst auszuführen.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlServiceModuleT::m\_bService](../Topic/CAtlServiceModuleT::m_bService.md)|Das Flag, das das Programm angibt, wird als Dienst.|  
|[CAtlServiceModuleT::m\_dwThreadID](../Topic/CAtlServiceModuleT::m_dwThreadID.md)|Membervariable, die den Threadbezeichner speichert.|  
|[CAtlServiceModuleT::m\_hServiceStatus](../Topic/CAtlServiceModuleT::m_hServiceStatus.md)|Membervariable, der ein Handle zur Statusinformationsstruktur für den aktuellen Dienst speichert.|  
|[CAtlServiceModuleT::m\_status](../Topic/CAtlServiceModuleT::m_status.md)|Membervariable, die die Statusinformationsstruktur für den aktuellen Dienst speichert.|  
|[CAtlServiceModuleT::m\_szServiceName](../Topic/CAtlServiceModuleT::m_szServiceName.md)|Der Name des Diensts, der registriert wird.|  
  
## Hinweise  
 `CAtlServiceModuleT`, abgeleitet von [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md), implementiert einen ATL\-Testmodul.  `CAtlServiceModuleT` stellt Methoden zum Befehlszeilenverarbeiten, \-Installation, \-c$registrieren und \-Entfernen bereit.  Wenn zusätzliche Funktionalität erforderlich, können diese und andere Methoden überschrieben werden.  
  
 Diese Klasse ersetzt veraltete [CComModule\-Klasse](../../atl/reference/ccommodule-class.md), das in früheren Versionen von ATL verwendet wird.  Siehe [ATL\-Modul\-Klassen](../../atl/atl-module-classes.md) für weitere Details.  
  
## Vererbungshierarchie  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)  
  
 `CAtlServiceModuleT`  
  
## Anforderungen  
 **Header:** atlbase.h  
  
## Siehe auch  
 [CAtlExeModuleT Class](../../atl/reference/catlexemodulet-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)