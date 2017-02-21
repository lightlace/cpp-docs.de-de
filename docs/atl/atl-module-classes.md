---
title: "ATL-Modulklassen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, Modulklassen"
  - "CComModule-Klasse, Neues"
  - "Modulklassen"
ms.assetid: fd75382d-c955-46ba-a38e-37728b7fa00f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ATL-Modulklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema werden die Modulklassen, die in ATL 7.0 neu waren.  
  
## CComModule\-Ersatz\-Klassen  
 In früheren Versionen von ATL verwendete `CComModule`.  In ATL 7.0 wird `CComModule`\-Funktionen über mehrere Klassen ersetzt:  
  
-   [CAtlBaseModule](../atl/reference/catlbasemodule-class.md) enthält die Informationen, die von den meisten Anwendungen benötigt werden, die ATL verwenden.  Enthält das der des Moduls und der Ressourceninstanz.  
  
-   [CAtlComModule](../atl/reference/catlcommodule-class.md) enthält die Informationen, die durch die COM\-Klassen in ATL erfordert.  
  
-   [CAtlWinModule](../atl/reference/catlwinmodule-class.md) enthält die Informationen, die von der Fensterklassen in ATL erfordert.  
  
-   [CAtlDebugInterfacesModule](../atl/reference/catldebuginterfacesmodule-class.md) enthält Unterstützung für Schnittstellendebugging.  
  
-   [CAtlModule](../atl/reference/catlmodule-class.md) folgende `CAtlModule` von abgeleitete Klassen werden angepasst, um die Informationen enthalten, die in einem bestimmten Anwendungstyp erforderlich sind.  Die meisten Member in diesen Klassen können überschrieben werden:  
  
    -   [CAtlDllModuleT](../atl/reference/catldllmodulet-class.md) verwendete in DLL\-Anwendungen.  Stellt Code für die Standardexporte bereit.  
  
    -   [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) verwendete in EXE\-Anwendungen.  Enthält Code, der in einem EXE\-Datei benötigt wird.  
  
    -   [CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) unterstützt, um Windows NT und Windows 2000dienstleistungen zu erstellen.  
  
 `CComModule` ist für Abwärtskompatibilität weiterhin verfügbar.  
  
## Gründe für das Verteilen von CComModule\-Funktionalität  
 Die Funktionalität von `CComModule` wurde in mehrere neue Klassen für die folgenden Gründe verteilt:  
  
-   Führen Sie die Funktionalität in `CComModule` präzise.  
  
     Unterstützung für COM, Fenster, Schnittstellendebugging und anwendungsspezifische \(EXE oder DLL\) Funktionen ist jetzt in separate Klassen.  
  
-   Deklarieren Sie automatisch globale Instanz von jedem dieser Module.  
  
     Eine globale Instanz der erforderlichen Modulklassen wird in das Projekt.  
  
-   Entfernen Sie die Notwendigkeit des Aufrufens von Init und geben Sie als Methoden.  
  
     Methoden Init und des Begriffs haben sich in die Konstruktoren und Destruktoren in die für die Modulklassen bewegt; es gibt nicht mehr eine Anforderung, Init und Begriff aufzurufen.  
  
## Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)   
 [Class Overview](../atl/atl-class-overview.md)