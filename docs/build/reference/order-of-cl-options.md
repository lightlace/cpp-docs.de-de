---
title: Reihenfolge von CL-Optionen (C++) (Visual Studio
ms.date: 12/14/2018
f1_keywords:
- cl
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
ms.openlocfilehash: 93907265bed8141b5c63edd5e75d632e060351fe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320941"
---
# <a name="order-of-cl-options"></a>Reihenfolge von CL-Optionen

Optionen können an einer beliebigen Stelle in der CL-Befehlszeile, mit Ausnahme der Option/Link angezeigt, die zuletzt erfolgen muss. Der Compiler beginnt, mit den Optionen, die im angegebenen die [CL-Umgebungsvariablen](cl-environment-variables.md) und liest dann die Befehlszeile von links nach rechts: Verarbeiten von Befehlsdateien, die in der Reihenfolge gefunden werden. Jede Option gilt für alle Dateien in der Befehlszeile. Wenn CL in Konflikt stehenden Optionen auftritt, wird die äußersten rechten-Option verwendet.

## <a name="see-also"></a>Siehe auch

[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
