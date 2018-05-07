---
title: 'Ressourcencompiler: Fehler RC2151 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2151
dev_langs:
- C++
helpviewer_keywords:
- RC2151
ms.assetid: 3c47e535-c78d-4338-aab9-9b47e2c34728
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8349aa14de6aec96fa1b526cbcffbe79036f804d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="resource-compiler-error-rc2151"></a>Ressourcencompiler: Fehler RC2151
Zeichenfolgenkonstanten kann nicht erneut verwendet werden.  
  
 Sie verwenden den gleichen Wert zweimal in eine **STRINGTABLE** Anweisung. Stellen Sie sicher, dass Sie keine überlappenden dezimaler und hexadezimaler Werte.  
  
 Jede ID in einer **STRINGTABLE** muss eindeutig sein. Maximaler Effizienz verwenden zusammenhängenden Konstanten, die auf ein Vielfaches von 16 beginnen.