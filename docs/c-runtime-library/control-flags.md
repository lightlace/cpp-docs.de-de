---
title: Steuerungsflags
ms.date: 11/04/2016
f1_keywords:
- c.flags
helpviewer_keywords:
- flags, control
- heap allocation, control flags
- debug heap, control flags
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
ms.openlocfilehash: 7ac5f239ea4d242618fb23ba617a3a6539492053
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750113"
---
# <a name="control-flags"></a>Steuerungsflags

Die Debugversion der Microsoft C-Laufzeitbibliothek verwendet die folgenden Flags, um den Heapbelegungs- und Berichterstellungsprozess zu steuern. Weitere Informationen finden Sie unter [CRT-Debugverfahren](/visualstudio/debugger/crt-debugging-techniques).

|Flag|Beschreibung|
|----------|-----------------|
|[_CRTDBG_MAP_ALLOC](../c-runtime-library/crtdbg-map-alloc.md)|Ordnet die grundlegenden Heapfunktionen zu den entsprechenden Funktionen in der Debugversion zu.|
|[_DEBUG](../c-runtime-library/debug.md)|Ermöglicht die Verwendung der Debugversionen der Laufzeitfunktionen.|
|[_crtDbgFlag](../c-runtime-library/crtdbgflag.md)|Steuert, wie der Debugheap-Manager die Belegungen nachverfolgt.|

Diese Flags können mit einer /D-Befehlszeilenoption oder einer `#define`-Direktive definiert werden. Wenn das Flag mit `#define` definiert wird, muss sich die Direktive vor der include-Anweisung der Headerdatei für die Routinedeklarationen befinden.

## <a name="see-also"></a>Siehe auch

[Globale Variablen und Standardtypen](../c-runtime-library/global-variables-and-standard-types.md)
