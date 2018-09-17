---
title: Reihenfolge von CL-Optionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- cl
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ffe9a440396df14823775db335e52bca6cacdb3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725022"
---
# <a name="order-of-cl-options"></a>Reihenfolge von CL-Optionen

Optionen können an einer beliebigen Stelle in der CL-Befehlszeile, mit Ausnahme der Option/Link angezeigt, die zuletzt erfolgen muss. Der Compiler beginnt, mit den Optionen, die im angegebenen die [CL-Umgebungsvariablen](../../build/reference/cl-environment-variables.md) und liest dann die Befehlszeile von links nach rechts: Verarbeiten von Befehlsdateien, die in der Reihenfolge gefunden werden. Jede Option gilt für alle Dateien in der Befehlszeile. Wenn CL in Konflikt stehenden Optionen auftritt, wird die äußersten rechten-Option verwendet.

## <a name="see-also"></a>Siehe auch

[Syntax für die Compilerbefehlszeile](../../build/reference/compiler-command-line-syntax.md)