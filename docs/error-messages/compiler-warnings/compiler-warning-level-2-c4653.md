---
title: Compilerwarnung (Stufe 2) C4653 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4653
dev_langs: C++
helpviewer_keywords: C4653
ms.assetid: 90ec3317-3d39-4b4c-bcd1-97e7c799e1b6
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8eb855e1c11136cd88c1c1e796d9759581e3ceb3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4653"></a>Compilerwarnung (Stufe 2) C4653
die Compileroption 'Option' inkonsistent mit der vorkompilierten Headerdatei; aktuelle Befehlszeilenoption wird ignoriert  
  
 Eine Option angegeben wird, mit der vorkompilierte Header (["/ Yu"](../../build/reference/yu-use-precompiled-header-file.md))-Option nicht konsistent mit den Optionen, die beim Erstellen des vorkompilierten Headers angegeben wurde. Dieser Kompilierung verwendet die Option beim Erstellen des vorkompilierten Headers angegeben.  
  
 Diese Warnung kann auftreten, wenn ein anderer Wert für die Option Pack Strukturen ([/Zp](../../build/reference/zp-struct-member-alignment.md)) während der Kompilierung des vorkompilierten Headers angegeben wurde.