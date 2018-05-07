---
title: Compilerwarnung (Stufe 1) C4650 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4650
dev_langs:
- C++
helpviewer_keywords:
- C4650
ms.assetid: 3190b3e3-dcd6-4846-939b-f900ab652b2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6cb1c9979141e7958b6c2802aaf321efe41e9570
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4650"></a>Compilerwarnung (Stufe 1) C4650
die Debuginformationen nicht in der vorkompilierten Headerdatei; nur globale Symbole aus dem Header werden verfügbar sein.  
  
 Die vorkompilierte Headerdatei wurde nicht mit Microsoft symbolischen Debuginformationen kompiliert.  
  
 Wenn verknüpft ist, sind die resultierende ausführbare Datei oder eine Dynamic Link Library-Datei Debuginformationen für lokale Symbole, die in der vorkompilierte Header enthalten.  
  
 Diese Warnung kann vermieden werden, durch das erneute Kompilieren der vorkompilierten Headerdatei mit dem [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) Befehlszeilenoption.