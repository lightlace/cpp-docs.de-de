---
title: Reihenfolge von CL-Optionen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- cl
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ef67792b01d4d4dab535bfb180cd70beb2316b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="order-of-cl-options"></a>Reihenfolge von CL-Optionen
Optionen können an einer beliebigen Stelle in der CL-Befehlszeile, mit Ausnahme der Option/Link angezeigt, die zuletzt auftreten muss. Der Compiler beginnt mit den Optionen, die im angegebenen der [CL-Umgebungsvariablen](../../build/reference/cl-environment-variables.md) und liest dann die Befehlszeile von links nach rechts – Befehlsdateien in der Reihenfolge, die er erkennt diese verarbeiten. Jede Option gilt für alle Dateien in der Befehlszeile angegeben. Wenn CL in Konflikt stehenden Optionen auftritt, wird die äußersten rechten-Option verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Syntax für die Compilerbefehlszeile](../../build/reference/compiler-command-line-syntax.md)