---
title: 'Ressourcencompiler: Fehler RC2151 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC2151
dev_langs:
- C++
helpviewer_keywords:
- RC2151
ms.assetid: 3c47e535-c78d-4338-aab9-9b47e2c34728
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: beabd61c64c296bf454aa94b8f915673b5f0cfca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rc2151"></a>Ressourcencompiler: Fehler RC2151
Zeichenfolgenkonstanten kann nicht erneut verwendet werden.  
  
 Sie verwenden den gleichen Wert zweimal in eine **STRINGTABLE** Anweisung. Stellen Sie sicher, dass Sie keine überlappenden dezimaler und hexadezimaler Werte.  
  
 Jede ID in einer **STRINGTABLE** muss eindeutig sein. Maximaler Effizienz verwenden zusammenhängenden Konstanten, die auf ein Vielfaches von 16 beginnen.