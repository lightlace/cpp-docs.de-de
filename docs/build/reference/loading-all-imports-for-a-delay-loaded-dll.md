---
title: Laden aller Importe für eine verzögert geladene DLL
ms.date: 11/04/2016
helpviewer_keywords:
- __HrLoadAllImportsForDll linker option
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
ms.openlocfilehash: e855b648dc7a9ee0670c3704a11aa1897a238403
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301668"
---
# <a name="loading-all-imports-for-a-delay-loaded-dll"></a>Laden aller Importe für eine verzögert geladene DLL

Die **__HrLoadAllImportsForDll** -Funktion, die im delayhlp.cpp definiert ist, weist den Linker an alle Importe aus einer DLL zu laden, die mit angegeben wurde der [/DELAYLOAD](delayload-delay-load-import.md) -Linkeroption.

Laden aller Importe, können Sie für die Fehlerbehandlung an einem Ort in Ihrem Code platzieren und nicht um die tatsächlichen Aufrufe der Importe für die Ausnahmebehandlung zu verwenden. ADSI vermeidet außerdem eine Situation, in dem Ihre Anwendung teilweise durch einen Prozess als Ergebnis des hilfscodes, der nicht geladen werden einen Import fehlschlägt.

Aufrufen von **__HrLoadAllImportsForDll** ändert sich nicht auf das Verhalten von Hooks und Fehler behandeln, finden Sie unter [Fehlerbehandlung und Benachrichtigung](error-handling-and-notification.md) für Weitere Informationen.

Name der DLL übergeben **__HrLoadAllImportsForDll** im Vergleich zu den Namen in die DLL selbst gespeichert und Groß-/Kleinschreibung beachtet.

Das folgende Beispiel zeigt das Aufrufen von **__HrLoadAllImportsForDll**:

```
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {
   printf ( "failed on snap load, exiting\n" );
   exit(2);
}
```

## <a name="see-also"></a>Siehe auch

[Linkerunterstützung für verzögertes Laden von DLLs](linker-support-for-delay-loaded-dlls.md)
