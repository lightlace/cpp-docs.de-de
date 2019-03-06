---
title: Reihenfolge von CL-Optionen
ms.date: 11/04/2016
f1_keywords:
- cl
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
ms.openlocfilehash: d87e3214d4829f81258acd00abebced34d7d969d
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423689"
---
# <a name="order-of-cl-options"></a>Reihenfolge von CL-Optionen

Optionen können an einer beliebigen Stelle in der CL-Befehlszeile, mit Ausnahme der Option/Link angezeigt, die zuletzt erfolgen muss. Der Compiler beginnt, mit den Optionen, die im angegebenen die [CL-Umgebungsvariablen](../../build/reference/cl-environment-variables.md) und liest dann die Befehlszeile von links nach rechts: Verarbeiten von Befehlsdateien, die in der Reihenfolge gefunden werden. Jede Option gilt für alle Dateien in der Befehlszeile. Wenn CL in Konflikt stehenden Optionen auftritt, wird die äußersten rechten-Option verwendet.

## <a name="see-also"></a>Siehe auch

[Syntax für die Compilerbefehlszeile](../../build/reference/compiler-command-line-syntax.md)
