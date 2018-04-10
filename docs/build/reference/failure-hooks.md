---
title: Fehlerhooks | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, failure hooks
ms.assetid: 12bb303b-ffe6-4471-bffe-9ef4f8bb2d30
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1609b713fef253e8beab270ee2ed048466da6504
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="failure-hooks"></a>Fehlerhooks
Der Fehlerhook aktiviert ist, auf die gleiche Weise wie die [Benachrichtigungshook](../../build/reference/notification-hooks.md). Der Hook routinemäßige muss einen geeigneten Wert zurück, sodass die Verarbeitung können weiterhin (HINSTANCE oder FARPROC) oder 0, um anzugeben, dass eine Ausnahme ausgelöst werden soll.  
  
 Die Zeigervariable, die auf die benutzerdefinierte Funktion verweist ist:  
  
```  
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}  
ExternC  
PfnDliHook   __pfnDliFailureHook2;  
```  
  
 Die **DelayLoadInfo** Struktur enthält alle relevanten Daten, die erforderlich ist, für die korrekte Meldung des Fehlers, einschließlich des Wertes von `GetLastError`.  
  
 Wenn die Benachrichtigung ist **DliFailLoadLib**, kann die Hookfunktion zurückgeben:  
  
-   0, wenn den Fehler nicht behandeln kann.  
  
-   Ein HMODULE, wenn der Fehlerhook das Problem behoben und die Bibliothek geladen.  
  
 Wenn die Benachrichtigung ist **DliFailGetProc**, kann die Hookfunktion zurückgeben:  
  
-   0, wenn den Fehler nicht behandeln kann.  
  
-   Eine gültige Proc (Adresse Import-Funktion), wenn der Fehler verknüpfen wurde erfolgreich Abrufen der Adresse selbst.  
  
## <a name="see-also"></a>Siehe auch  
 [Fehlerbehandlung und Benachrichtigung](../../build/reference/error-handling-and-notification.md)