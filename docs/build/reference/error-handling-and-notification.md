---
title: Fehlerbehandlung und Benachrichtigung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- error handling, and notification
ms.assetid: b621cf60-d869-451a-b05e-dc86d78addaa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e2edec23da89766a45545566b0a689001d3ca75f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="error-handling-and-notification"></a>Fehlerbehandlung und Benachrichtigung
Weitere Informationen zu Fehlerbehandlung und Benachrichtigung, finden Sie unter [die Hilfsfunktion](understanding-the-helper-function.md).  
  
 Weitere Informationen zu Hookfunktionen finden Sie unter [Struktur- und Konstantendefinitionen](../../build/reference/structure-and-constant-definitions.md).  
  
 Wenn Ihr Programm verzögert geladene DLLs verwendet, muss es Fehler stabil behandelt, da der Fehler, die auftreten, während das Programm ausgeführt wird, führt nicht behandelte Ausnahmen. Die Fehlerbehandlung besteht aus zwei Teilen:  
  
 Wiederherstellung über einen Hook.  
 Wenn der Code muss wiederherzustellen, oder geben Sie eine alternative Bibliothek und/oder die Routine bei einem Fehler, kann ein Hook für die Hilfsfunktion bereitgestellt werden, die angeben können, oder die Situation zu vermeiden. Der Hook routinemäßige muss einen geeigneten Wert zurück, sodass die Verarbeitung können weiterhin (HINSTANCE oder FARPROC) oder 0, um anzugeben, dass eine Ausnahme ausgelöst werden soll. Auch eine eigene Ausnahme auslösen oder **Longjmp** Out Hook. Es gibt Benachrichtigungshooks und Fehlerhooks.  
  
 Meldung über eine Ausnahme aus.  
 Wenn für die Behandlung des Fehlers erforderlich ist lediglich um den Vorgang abzubrechen, ist kein Hook erforderlich, solange der Code die Ausnahme behandeln kann.  
  
 Die folgenden Themen behandeln die Fehlerbehandlung und Benachrichtigung:  
  
-   [Benachrichtigungshooks](../../build/reference/notification-hooks.md)  
  
-   [Fehlerhooks](../../build/reference/failure-hooks.md)  
  
-   [Ausnahmen](../../build/reference/exceptions-c-cpp.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)