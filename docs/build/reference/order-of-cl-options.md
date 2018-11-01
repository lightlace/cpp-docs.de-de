---
title: Reihenfolge von CL-Optionen
ms.date: 11/04/2016
f1_keywords:
- cl
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
ms.openlocfilehash: e5dd07f52f853b17bf663e2fbad7dbe66a3a1db7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633533"
---
# <a name="order-of-cl-options"></a>Reihenfolge von CL-Optionen

Optionen können an einer beliebigen Stelle in der CL-Befehlszeile, mit Ausnahme der Option/Link angezeigt, die zuletzt erfolgen muss. Der Compiler beginnt, mit den Optionen, die im angegebenen die [CL-Umgebungsvariablen](../../build/reference/cl-environment-variables.md) und liest dann die Befehlszeile von links nach rechts: Verarbeiten von Befehlsdateien, die in der Reihenfolge gefunden werden. Jede Option gilt für alle Dateien in der Befehlszeile. Wenn CL in Konflikt stehenden Optionen auftritt, wird die äußersten rechten-Option verwendet.

## <a name="see-also"></a>Siehe auch

[Syntax für die Compilerbefehlszeile](../../build/reference/compiler-command-line-syntax.md)