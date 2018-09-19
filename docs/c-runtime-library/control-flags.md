---
title: Steuerungsflags | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.flags
dev_langs:
- C++
helpviewer_keywords:
- flags, control
- heap allocation, control flags
- debug heap, control flags
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 716e597be5d337d11d58df944bbba468e496f078
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078061"
---
# <a name="control-flags"></a>Steuerungsflags

Die Debugversion der Microsoft C-Laufzeitbibliothek verwendet die folgenden Flags, um den Heapbelegungs- und Berichterstellungsprozess zu steuern. Weitere Informationen finden Sie unter [CRT-Debugverfahren](/visualstudio/debugger/crt-debugging-techniques).

|Flag|Beschreibung |
|----------|-----------------|
|[_CRTDBG_MAP_ALLOC](../c-runtime-library/crtdbg-map-alloc.md)|Ordnet die grundlegenden Heapfunktionen zu den entsprechenden Funktionen in der Debugversion zu.|
|[_DEBUG](../c-runtime-library/debug.md)|Ermöglicht die Verwendung der Debugversionen der Laufzeitfunktionen.|
|[_crtDbgFlag](../c-runtime-library/crtdbgflag.md)|Steuert, wie der Debugheap-Manager die Belegungen nachverfolgt.|

Diese Flags können mit einer /D-Befehlszeilenoption oder einer `#define`-Direktive definiert werden. Wenn das Flag mit `#define` definiert wird, muss sich die Direktive vor der include-Anweisung der Headerdatei für die Routinedeklarationen befinden.

## <a name="see-also"></a>Siehe auch

[Globale Variablen und Standardtypen](../c-runtime-library/global-variables-and-standard-types.md)