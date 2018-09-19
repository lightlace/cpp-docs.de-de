---
title: 'NMAKE: Schwerwiegender Fehler U1059 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1059
dev_langs:
- C++
helpviewer_keywords:
- U1059
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b54919398c757bfe05f747ff57341f31decfc61
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43200789"
---
# <a name="nmake-fatal-error-u1059"></a>NMAKE: Schwerwiegender Fehler U1059

> Syntaxfehler: '}' fehlt im abhängigen Element

Ein Suchpfad für eine abhängige Datei wurde falsch angegeben. Entweder ist ein Leerzeichen im Pfad oder die schließende geschweifte Klammer (**}**) ausgelassen wurde.

Die Syntax für eine Verzeichnisangabe für ein abhängiges Element ist

> **{** *Verzeichnisse* **} abhängige**

wo *Verzeichnisse* gibt einen oder mehrere Pfade, jeweils getrennt durch ein Semikolon (**;**). Es sind keine Leerzeichen zulässig.

Stellen Sie teilweise oder vollständig einen Suchpfad angeben, die von einem Makro ersetzt wird, sicher, dass keine Leerzeichen enthalten, die in der makroerweiterung vorhanden sind.