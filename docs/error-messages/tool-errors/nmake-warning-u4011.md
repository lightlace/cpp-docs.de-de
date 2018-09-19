---
title: 'NMAKE: Warnung U4011 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U4011
dev_langs:
- C++
helpviewer_keywords:
- U4011
ms.assetid: e8244514-eba6-4285-8853-7baeefdcd8a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a1038ee86f76789451565ab6799795c851c95a95
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118335"
---
# <a name="nmake-warning-u4011"></a>NMAKE: Warnung U4011

'Target': nicht alle abhängigen Elemente verfügbar. Ziel nicht erstellt

Das angegebene Ziel ein abhängiges Element ist nicht vorhanden oder war nicht mehr aktuell, und ein Befehl zum Aktualisieren des abhängigen zurückgegeben einen Exitcode ungleich NULL. Die Option/k mitgeteilt NMAKE und weiter verarbeitet, nicht zusammengehöriger Teile des Builds und einen Exitcode 1 auszugeben, die NMAKE-Sitzung abgeschlossen ist.

Diese Warnung wird für die Warnung vorangestellt [U4010](../../error-messages/tool-errors/nmake-warning-u4010.md) für jedes abhängige, die nicht erstellt oder aktualisiert werden konnten.