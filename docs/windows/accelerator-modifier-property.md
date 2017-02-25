---
title: "Eigenschaft &quot;Modifizierer&quot; von Zugriffstasten | Microsoft Docs"
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
  - "Modifier-Eigenschaft"
ms.assetid: f05a9379-e037-4cfb-b6ef-d2c655bcfa7f
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Eigenschaft &quot;Modifizierer&quot; von Zugriffstasten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Einträge sind für die Eigenschaft **Modifizierer** in der Zugriffstastentabelle zulässig.  
  
|Wert|Beschreibung|  
|----------|------------------|  
|**None**|Der Benutzer drückt nur den Wert unter **Taste**.  Diese Einstellung ist am effizientesten mit den ASCII\/ANSI\-Werten 001 bis 026, die als ^A bis ^Z \(STRG\-A bis STRG\-Z\) interpretiert werden.|  
|**Alt**|Der Benutzer muss erst die ALT\-TASTE und dann den Tastenwert drücken.|  
|**Ctrl**|Der Benutzer muss erst die STRG\-TASTE und dann den Tastenwert drücken.  Nicht zulässig mit dem ASCII\-Typ.|  
|**Shift**|Der Benutzer muss erst die UMSCHALTTASTE und dann den Tastenwert drücken.|  
|**Ctrl\+Alt**|Der Benutzer muss erst die STRG\- und die ALT\-TASTE und dann den Tastenwert drücken.  Nicht zulässig mit dem ASCII\-Typ.|  
|**Ctrl\+Shift**|Der Benutzer muss erst die STRG\- und die UMSCHALTTASTE und dann den Tastenwert drücken.  Nicht zulässig mit dem ASCII\-Typ.|  
|**Alt\+Shift**|Der Benutzer muss erst die ALT\- und die UMSCHALTTASTE und dann den Tastenwert drücken.  Nicht zulässig mit dem ASCII\-Typ.|  
|**Ctrl\+Alt\+Shift**|Der Benutzer muss erst die STRG\-, ALT\- und UMSCHALTTASTE und dann den Tastenwert drücken.  Nicht zulässig mit dem ASCII\-Typ.|  
  
## Anforderungen  
 Win32  
  
## Siehe auch  
 [Setting Accelerator Properties](../windows/setting-accelerator-properties.md)   
 [Accelerator Editor](../mfc/accelerator-editor.md)