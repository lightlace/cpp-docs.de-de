---
title: Reihenfolge von CL-Optionen | Microsoft Docs
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
ms.openlocfilehash: 165e20eefecd20ad9dec9e01b38c5eaa7926e4eb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372808"
---
# <a name="order-of-cl-options"></a>Reihenfolge von CL-Optionen
Optionen können an einer beliebigen Stelle in der CL-Befehlszeile, mit Ausnahme der Option/Link angezeigt, die zuletzt auftreten muss. Der Compiler beginnt mit den Optionen, die im angegebenen der [CL-Umgebungsvariablen](../../build/reference/cl-environment-variables.md) und liest dann die Befehlszeile von links nach rechts – Befehlsdateien in der Reihenfolge, die er erkennt diese verarbeiten. Jede Option gilt für alle Dateien in der Befehlszeile angegeben. Wenn CL in Konflikt stehenden Optionen auftritt, wird die äußersten rechten-Option verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Syntax für die Compilerbefehlszeile](../../build/reference/compiler-command-line-syntax.md)