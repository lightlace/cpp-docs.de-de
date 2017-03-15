---
title: "Fehlerhooks | Microsoft Docs"
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
  - "Verzögertes Laden von DLLs, Fehlerhooks"
ms.assetid: 12bb303b-ffe6-4471-bffe-9ef4f8bb2d30
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Fehlerhooks
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Fehlerhook wird auf dieselbe Weise wie der [Benachrichtigungshook](../../build/reference/notification-hooks.md) aktiviert.  Von der Hookroutine muss entweder ein geeigneter Wert \(einen `HINSTANCE`\-Wert oder einen **FARPROC**\-Wert\) zurückgegeben werden, sodass die Verarbeitung fortgesetzt werden kann, oder der Rückgabewert muss 0 sein, um anzuzeigen, dass eine Ausnahme ausgelöst werden soll.  
  
 Die Zeigervariable, die auf die benutzerdefinierte Funktion verweist, ist wie folgt definiert:  
  
```  
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}  
ExternC  
PfnDliHook   __pfnDliFailureHook2;  
```  
  
 Die **DelayLoadInfo**\-Struktur enthält alle relevanten Daten, die für die korrekte Meldung des Fehlers erforderlich sind, einschließlich des Werts von `GetLastError`.  
  
 Handelt es sich bei der Benachrichtigung um **dliFailLoadLib**, können von der Hookfunktion folgende Werte zurückgegeben werden:  
  
-   0, wenn der Fehler nicht von ihr behandelt werden kann.  
  
-   ein **HMODULE**, wenn der Fehlerhook das Problem behoben und die Bibliothek geladen hat.  
  
 Handelt es sich bei der Benachrichtigung um **dliFailGetProc**, können von der Hookfunktion folgende Werte zurückgegeben werden:  
  
-   0, wenn der Fehler nicht von ihr behandelt werden kann.  
  
-   eine gültige Prozeduradresse \(Importfunktionsadresse\), wenn der Fehlerhook die Adresse erfolgreich abrufen konnte.  
  
## Siehe auch  
 [Fehlerbehandlung und Benachrichtigung](../../build/reference/error-handling-and-notification.md)