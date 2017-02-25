---
title: "CAtlExeModuleT Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAtlExeModuleT<T>"
  - "CAtlExeModuleT"
  - "ATL.CAtlExeModuleT<T>"
  - "ATL::CAtlExeModuleT"
  - "ATL.CAtlExeModuleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlExeModuleT class"
ms.assetid: 82245f3d-91d4-44fa-aa86-7cc7fbd758d9
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CAtlExeModuleT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt das Modul für eine Anwendung dar.  
  
## Syntax  
  
```  
  
      template <  
   class T   
>  
class ATL_NO_VTABLE CAtlExeModuleT :  
   public CAtlModuleT< T >  
```  
  
#### Parameter  
 `T`  
 Die Klasse wird von abgeleitet `CAtlExeModuleT`.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlExeModuleT::CAtlExeModuleT](../Topic/CAtlExeModuleT::CAtlExeModuleT.md)|Der \-Konstruktor.|  
|[CAtlExeModuleT::~CAtlExeModuleT](../Topic/CAtlExeModuleT::~CAtlExeModuleT.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlExeModuleT::InitializeCom](../Topic/CAtlExeModuleT::InitializeCom.md)|Initialisiert COM.|  
|[CAtlExeModuleT::ParseCommandLine](../Topic/CAtlExeModuleT::ParseCommandLine.md)|Analysiert die Befehlszeile und führt ggf. Registrierung aus.|  
|[CAtlExeModuleT::PostMessageLoop](../Topic/CAtlExeModuleT::PostMessageLoop.md)|Diese Methode wird sofort nach der Nachrichtenschleifenbeendigungen aufgerufen.|  
|[CAtlExeModuleT::PreMessageLoop](../Topic/CAtlExeModuleT::PreMessageLoop.md)|Diese Methode wird unmittelbar vor dem Eingeben der Nachrichtenschleife aufgerufen.|  
|[CAtlExeModuleT::RegisterClassObjects](../Topic/CAtlExeModuleT::RegisterClassObjects.md)|Registriert das Klassenobjekt.|  
|[CAtlExeModuleT::RevokeClassObjects](../Topic/CAtlExeModuleT::RevokeClassObjects.md)|Widerruft das Klassenobjekt.|  
|[CAtlExeModuleT::Run](../Topic/CAtlExeModuleT::Run.md)|Diese Methode führt Code im EXE\-Modul aus, um zu initialisieren, führt die Meldungsschleife aus und bereinigt auf.|  
|[CAtlExeModuleT::RunMessageLoop](../Topic/CAtlExeModuleT::RunMessageLoop.md)|Diese Methode führt die Meldungsschleife aus.|  
|[CAtlExeModuleT::UninitializeCom](../Topic/CAtlExeModuleT::UninitializeCom.md)|Deinitialisiert COM.|  
|[CAtlExeModuleT::Unlock](../Topic/CAtlExeModuleT::Unlock.md)|Dekrementiert die Sperrenanzahl des Moduls.|  
|[CAtlExeModuleT::WinMain](../Topic/CAtlExeModuleT::WinMain.md)|Diese Methode implementiert den Code, der erforderlich ist, eine EXE\-Datei auszuführen.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlExeModuleT::m\_bDelayShutdown](../Topic/CAtlExeModuleT::m_bDelayShutdown.md)|Ein Flag, das angibt, dass es eine Verzögerung geben soll, die das Modul beendet wird.|  
|[CAtlExeModuleT::m\_dwPause](../Topic/CAtlExeModuleT::m_dwPause.md)|Ein Pausenwert, der verwendet wird, um alle Objekte sicherzustellen, werden vor dem Herunterfahren freigegeben.|  
|[CAtlExeModuleT::m\_dwTimeOut](../Topic/CAtlExeModuleT::m_dwTimeOut.md)|Ein Timeoutwert verwendet, um das Entladen des Moduls verzögert werden.|  
  
## Hinweise  
 `CAtlExeModuleT` stellt das Modul für eine Anwendung \(.exe\) dar und enthält Code, der das Erstellen einer EXE\-Datei, die Verarbeitung der Befehlszeile, Registrieren von Klassenobjekten, das Ausführen der Nachrichtenschleife und auf Beendigung bereinigen unterstützt.  
  
 Diese Klasse wurde entworfen, um die Leistung zu verbessern, wenn COM\-Objekte im EXE\-Server ständig erstellt und zerstört werden.  Nachdem das letzte COM\-Objekt freigegeben ist, wartet die EXE\-Datei auf eine Dauer, die vom [CAtlExeModuleT::m\_dwTimeOut](../Topic/CAtlExeModuleT::m_dwTimeOut.md) Datenmember angegeben wird.  Wenn keine Aktivität während dieses Zeitraums \(das heißt, werden keine COM\-Objekte erstellt\), gibt, wird der Herunterfahrenprozess initiiert.  
  
 Der [CAtlExeModuleT::m\_bDelayShutdown](../Topic/CAtlExeModuleT::m_bDelayShutdown.md) Datenmember ist ein Flag, das verwendet wird, um zu bestimmen, ob die EXE\-Datei den Mechanismus verwendet, der oben definiert ist.  Wenn es auf false festgelegt ist, dann wird das Modul sofort.  
  
 Weitere Informationen zu Modulen in ATL, finden Sie unter [ATL\-Modul\-Klassen](../../atl/atl-module-classes.md).  
  
## Vererbungshierarchie  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CAtlExeModuleT`  
  
## Anforderungen  
 **Header:** atlbase.h  
  
## Siehe auch  
 [ATLDuck\-Beispiel](../../top/visual-cpp-samples.md)   
 [CAtlModuleT Class](../../atl/reference/catlmodulet-class.md)   
 [CAtlDllModuleT Class](../../atl/reference/catldllmodulet-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)