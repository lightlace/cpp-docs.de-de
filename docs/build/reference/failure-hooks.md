---
title: Fehlerhooks | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, failure hooks
ms.assetid: 12bb303b-ffe6-4471-bffe-9ef4f8bb2d30
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be598a77ca48eeee03360a3b598b0567abc6ee4b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371784"
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