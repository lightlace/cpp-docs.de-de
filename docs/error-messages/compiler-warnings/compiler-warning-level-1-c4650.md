---
title: Compilerwarnung (Stufe 1) C4650 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4650
dev_langs: C++
helpviewer_keywords: C4650
ms.assetid: 3190b3e3-dcd6-4846-939b-f900ab652b2a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8671b72e244a29698fa31da40de8147cdd348130
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4650"></a>Compilerwarnung (Stufe 1) C4650
die Debuginformationen nicht in der vorkompilierten Headerdatei; nur globale Symbole aus dem Header werden verfügbar sein.  
  
 Die vorkompilierte Headerdatei wurde nicht mit Microsoft symbolischen Debuginformationen kompiliert.  
  
 Wenn verknüpft ist, sind die resultierende ausführbare Datei oder eine Dynamic Link Library-Datei Debuginformationen für lokale Symbole, die in der vorkompilierte Header enthalten.  
  
 Diese Warnung kann vermieden werden, durch das erneute Kompilieren der vorkompilierten Headerdatei mit dem [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) Befehlszeilenoption.