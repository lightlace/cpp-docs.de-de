---
title: Laden aller Importe für eine verzögert geladene DLL
ms.date: 11/04/2016
helpviewer_keywords:
- __HrLoadAllImportsForDll linker option
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
ms.openlocfilehash: a144f3d4e0d6dbf306938dcc3fddd4faca73c17c
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57421167"
---
# <a name="loading-all-imports-for-a-delay-loaded-dll"></a>Laden aller Importe für eine verzögert geladene DLL

Die **__HrLoadAllImportsForDll** -Funktion, die im delayhlp.cpp definiert ist, weist den Linker an alle Importe aus einer DLL zu laden, die mit angegeben wurde der [/DELAYLOAD](../../build/reference/delayload-delay-load-import.md) -Linkeroption.

Laden aller Importe, können Sie für die Fehlerbehandlung an einem Ort in Ihrem Code platzieren und nicht um die tatsächlichen Aufrufe der Importe für die Ausnahmebehandlung zu verwenden. ADSI vermeidet außerdem eine Situation, in dem Ihre Anwendung teilweise durch einen Prozess als Ergebnis des hilfscodes, der nicht geladen werden einen Import fehlschlägt.

Aufrufen von **__HrLoadAllImportsForDll** ändert sich nicht auf das Verhalten von Hooks und Fehler behandeln, finden Sie unter [Fehlerbehandlung und Benachrichtigung](../../build/reference/error-handling-and-notification.md) für Weitere Informationen.

Name der DLL übergeben **__HrLoadAllImportsForDll** im Vergleich zu den Namen in die DLL selbst gespeichert und Groß-/Kleinschreibung beachtet.

Das folgende Beispiel zeigt das Aufrufen von **__HrLoadAllImportsForDll**:

```
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {
   printf ( "failed on snap load, exiting\n" );
   exit(2);
}
```

## <a name="see-also"></a>Siehe auch

[Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)
