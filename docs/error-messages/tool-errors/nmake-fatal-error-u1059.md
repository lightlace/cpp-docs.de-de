---
title: 'NMAKE: Schwerwiegender Fehler U1059'
ms.date: 08/27/2018
f1_keywords:
- U1059
helpviewer_keywords:
- U1059
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
ms.openlocfilehash: 3c148bf2feb7ba12686e00b29f5bf90cb9f2f2d7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50645024"
---
# <a name="nmake-fatal-error-u1059"></a>NMAKE: Schwerwiegender Fehler U1059

> Syntaxfehler: '}' fehlt im abhängigen Element

Ein Suchpfad für eine abhängige Datei wurde falsch angegeben. Entweder ist ein Leerzeichen im Pfad oder die schließende geschweifte Klammer (**}**) ausgelassen wurde.

Die Syntax für eine Verzeichnisangabe für ein abhängiges Element ist

> **{** *Verzeichnisse* **} abhängige**

wo *Verzeichnisse* gibt einen oder mehrere Pfade, jeweils getrennt durch ein Semikolon (**;**). Es sind keine Leerzeichen zulässig.

Stellen Sie teilweise oder vollständig einen Suchpfad angeben, die von einem Makro ersetzt wird, sicher, dass keine Leerzeichen enthalten, die in der makroerweiterung vorhanden sind.