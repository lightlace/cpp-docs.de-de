---
title: "Message Map Macros (ATL) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: eefdd546-8934-4a30-b263-9c06a8addcbd
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Message Map Macros (ATL)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Makros definieren Meldungszuordnungen und Einträge.  
  
|||  
|-|-|  
|[ALT\_MSG\_MAP](../Topic/ALT_MSG_MAP.md)|Markiert den Beginn einer alternativen Meldungszuordnung.|  
|[BEGIN\_MSG\_MAP](../Topic/BEGIN_MSG_MAP.md)|Markiert den Beginn der Standardmeldungszuordnung.|  
|[CHAIN\_MSG\_MAP\_ALT](../Topic/CHAIN_MSG_MAP_ALT.md)|Ketten zu einer anderen Meldungszuordnung in der Basisklasse.|  
|[CHAIN\_MSG\_MAP\_ALT\_MEMBER](../Topic/CHAIN_MSG_MAP_ALT_MEMBER.md)|Ketten zu einer anderen Meldungszuordnung in einem Datenmember der Klasse.|  
|[CHAIN\_MSG\_MAP](../Topic/CHAIN_MSG_MAP.md)|Ketten zur Standardmeldungszuordnung in der Basisklasse.|  
|[CHAIN\_MSG\_MAP\_DYNAMIC](../Topic/CHAIN_MSG_MAP_DYNAMIC.md)|Ketten zur Meldungszuordnung in einer anderen Klasse zur Laufzeit.|  
|[CHAIN\_MSG\_MAP\_MEMBER](../Topic/CHAIN_MSG_MAP_MEMBER.md)|Ketten zur Standardmeldungszuordnung in einem Datenmember der Klasse.|  
|[COMMAND\_CODE\_HANDLER](../Topic/COMMAND_CODE_HANDLER.md)|Ordnet eine **WM\_COMMAND** Meldung an eine Handlerfunktion, abhängig vom Benachrichtigungscode zu.|  
|[COMMAND\_HANDLER](../Topic/COMMAND_HANDLER.md)|Ordnet eine **WM\_COMMAND** Meldung an eine Handlerfunktion, abhängig vom Benachrichtigungscode und den Bezeichner des Menüelements, des Steuerelements oder der Zugriffstaste zu.|  
|[COMMAND\_ID\_HANDLER](../Topic/COMMAND_ID_HANDLER.md)|Ordnet eine **WM\_COMMAND** Meldung an eine Handlerfunktion, basierend auf den Bezeichner des Menüelements, des Steuerelements oder der Zugriffstaste zu.|  
|[COMMAND\_RANGE\_CODE\_HANDLER](../Topic/COMMAND_RANGE_CODE_HANDLER.md)|Ordnet eine **WM\_COMMAND** Meldung an eine Handlerfunktion, abhängig vom Benachrichtigungscode und einen zusammenhängenden Bereich von Steuerelement\-ID zu.|  
|[COMMAND\_RANGE\_HANDLER](../Topic/COMMAND_RANGE_HANDLER.md)|Ordnet eine **WM\_COMMAND** Meldung an eine Handlerfunktion, basierend auf einem zusammenhängenden Bereich von Steuerelement\-ID zu.|  
|[DECLARE\_EMPTY\_MSG\_MAP](../Topic/DECLARE_EMPTY_MSG_MAP.md)|Implementiert eine leere Meldungszuordnung.|  
|[DEFAULT\_REFLECTION\_HANDLER](../Topic/DEFAULT_REFLECTION_HANDLER.md)|Stellt einen Standardhandler für reflektierte Meldungen bereit, die andernfalls nicht bearbeitet werden.|  
|[END\_MSG\_MAP](../Topic/END_MSG_MAP.md)|Markiert das Ende einer Meldungszuordnung.|  
|[FORWARD\_NOTIFICATIONS](../Topic/FORWARD_NOTIFICATIONS.md)|Leitet Benachrichtigungsmeldungen an das übergeordnete Fenster weiter.|  
|[MESSAGE\_HANDLER](../Topic/MESSAGE_HANDLER.md)|Ordnet eine Windows\-Meldung auf eine Handlerfunktion zu.|  
|[MESSAGE\_RANGE\_HANDLER](../Topic/MESSAGE_RANGE_HANDLER.md)|Ordnet einen zusammenhängenden Bereich von Windows\-Meldungen auf eine Handlerfunktion zu.|  
|[NOTIFY\_CODE\_HANDLER](../Topic/NOTIFY_CODE_HANDLER.md)|Ordnet eine **WM\_NOTIFY** Meldung an eine Handlerfunktion, abhängig vom Benachrichtigungscode zu.|  
|[NOTIFY\_HANDLER](../Topic/NOTIFY_HANDLER.md)|Ordnet eine **WM\_NOTIFY** Meldung an eine Handlerfunktion, abhängig vom Benachrichtigungscode und das Steuerelement\-ID zu.|  
|[NOTIFY\_ID\_HANDLER](../Topic/NOTIFY_ID_HANDLER.md)|Ordnet eine **WM\_NOTIFY** Meldung an eine Handlerfunktion, auf Grundlage des Steuerelement\-ID zu.|  
|[NOTIFY\_RANGE\_CODE\_HANDLER](../Topic/NOTIFY_RANGE_CODE_HANDLER.md)|Ordnet eine **WM\_NOTIFY** Meldung an eine Handlerfunktion, abhängig vom Benachrichtigungscode und einen zusammenhängenden Bereich von Steuerelement\-ID zu.|  
|[NOTIFY\_RANGE\_HANDLER](../Topic/NOTIFY_RANGE_HANDLER.md)|Ordnet eine **WM\_NOTIFY** Meldung an eine Handlerfunktion, basierend auf einem zusammenhängenden Bereich von Steuerelement\-ID zu.|  
|[REFLECT\_NOTIFICATIONS](../Topic/REFLECT_NOTIFICATIONS.md)|Reflektiert Benachrichtigungsmeldungen zurück zum Fenster, das sie gesendet.|  
|[REFLECTED\_COMMAND\_CODE\_HANDLER](../Topic/REFLECTED_COMMAND_CODE_HANDLER.md)|Ordnet eine **WM\_COMMAND** reflektierte Meldung an eine Handlerfunktion, abhängig vom Benachrichtigungscode zu.|  
|[REFLECTED\_COMMAND\_HANDLER](../Topic/REFLECTED_COMMAND_HANDLER.md)|Ordnet eine **WM\_COMMAND** reflektierte Meldung an eine Handlerfunktion, abhängig vom Benachrichtigungscode und den Bezeichner des Menüelements, des Steuerelements oder der Zugriffstaste zu.|  
|[REFLECTED\_COMMAND\_ID\_HANDLER](../Topic/REFLECTED_COMMAND_ID_HANDLER.md)|Ordnet eine **WM\_COMMAND** reflektierte Meldung an eine Handlerfunktion, basierend auf den Bezeichner des Menüelements, des Steuerelements oder der Zugriffstaste zu.|  
|[REFLECTED\_COMMAND\_RANGE\_CODE\_HANDLER](../Topic/REFLECTED_COMMAND_RANGE_CODE_HANDLER.md)|Ordnet eine **WM\_COMMAND** reflektierte Meldung an eine Handlerfunktion, abhängig vom Benachrichtigungscode und einen zusammenhängenden Bereich von Steuerelement\-ID zu.|  
|[REFLECTED\_COMMAND\_RANGE\_HANDLER](../Topic/REFLECTED_COMMAND_RANGE_HANDLER.md)|Ordnet eine **WM\_COMMAND** reflektierte Meldung an eine Handlerfunktion, basierend auf einem zusammenhängenden Bereich von Steuerelement\-ID zu.|  
|[REFLECTED\_NOTIFY\_CODE\_HANDLER](../Topic/REFLECTED_NOTIFY_CODE_HANDLER.md)|Ordnet eine **WM\_NOTIFY** reflektierte Meldung an eine Handlerfunktion, abhängig vom Benachrichtigungscode zu.|  
|[REFLECTED\_NOTIFY\_HANDLER](../Topic/REFLECTED_NOTIFY_HANDLER.md)|Ordnet eine **WM\_NOTIFY** reflektierte Meldung an eine Handlerfunktion, abhängig vom Benachrichtigungscode und das Steuerelement\-ID zu.|  
|[REFLECTED\_NOTIFY\_ID\_HANDLER](../Topic/REFLECTED_NOTIFY_ID_HANDLER.md)|Ordnet eine **WM\_NOTIFY** reflektierte Meldung an eine Handlerfunktion, auf Grundlage des Steuerelement\-ID zu.|  
|[REFLECTED\_NOTIFY\_RANGE\_CODE\_HANDLER](../Topic/REFLECTED_NOTIFY_RANGE_CODE_HANDLER.md)|Ordnet eine **WM\_NOTIFY** reflektierte Meldung an eine Handlerfunktion, abhängig vom Benachrichtigungscode und einen zusammenhängenden Bereich von Steuerelement\-ID zu.|  
|[REFLECTED\_NOTIFY\_RANGE\_HANDLER](../Topic/REFLECTED_NOTIFY_RANGE_HANDLER.md)|Ordnet eine **WM\_NOTIFY** reflektierte Meldung an eine Handlerfunktion, basierend auf einem zusammenhängenden Bereich von Steuerelement\-ID zu.|  
  
## Siehe auch  
 [Macros](../../atl/reference/atl-macros.md)