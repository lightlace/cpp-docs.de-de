---
title: "Registry and TypeLib Global Functions"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RegistryDataExchange function, Globale Funktionen"
ms.assetid: d58b8a4e-975c-4417-8b34-d3c847f679b3
caps.latest.revision: 22
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Registry and TypeLib Global Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Funktionen bieten Unterstützung für das Laden und Registrieren einer Typbibliothek.  
  
> [!IMPORTANT]
>  Die Funktionen, die in den folgenden Tabellen aufgeführt sind, können nicht in Anwendungen verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
|||  
|-|-|  
|[AtlRegisterTypeLib](../Topic/AtlRegisterTypeLib.md)|Diese Funktion wird aufgerufen, um eine Typbibliothek zu registrieren.|  
|[AtlUnRegisterTypeLib](../Topic/AtlUnRegisterTypeLib.md)|Diese Funktion wird aufgerufen, um eine Typbibliothek Registrierung der|  
|[AtlLoadTypeLib](../Topic/AtlLoadTypeLib.md)|Diese Funktion wird aufgerufen, um eine Typbibliothek zu laden.|  
|[AtlUpdateRegistryFromResourceD](../Topic/AtlUpdateRegistryFromResourceD.md)|Diese Funktion wird aufgerufen, um die Registrierung von der angegebenen Ressource zu aktualisieren.|  
|[RegistryDataExchange](../Topic/RegistryDataExchange.md)|Diese Funktion wird aufgerufen, um von zu lesen, oder schreiben Sie zu, die Systemregistrierung.  Aufgerufen durch [Registrierungs\-Daten\-Exchange\-Makros](../../atl/reference/registry-data-exchange-macros.md).|  
  
 Steuerelement dieser Funktionen, dem Knoten in der Registrierung das Programm verwendet, um Informationen zu speichern.  
  
|||  
|-|-|  
|[AtlGetPerUserRegistration](../Topic/AtlGetPerUserRegistration.md)|Ruft ab, ob die Anwendung die Registrierung zum Knoten **HKEY\_CURRENT\_USER** \(**HKCU**\) umgeleitet werden.|  
|[AtlSetPerUserRegistration](../Topic/AtlSetPerUserRegistration.md)|Legt fest, ob die Anwendung die Registrierung zum Knoten **HKEY\_CURRENT\_USER** \(**HKCU**\) umgeleitet werden.|  
  
## Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)