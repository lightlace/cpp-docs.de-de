---
title: Compilerwarnung (Stufe 1) C4124 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4124
dev_langs: C++
helpviewer_keywords: C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 38588fb242b5b4167984e15d101594d1b015ec86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4124"></a>Compilerwarnung (Stufe 1) C4124
__fastcall mit stapelüberprüfung ist ineffizient  
  
 Die `__fastcall` Schlüsselwort mit stapelüberprüfung aktiviert verwendet wurde.  
  
 Die `__fastcall` Konvention generiert einen schnelleren Code, aber die stapelüberprüfung verursacht langsamere Code. Bei Verwendung `__fastcall`, deaktivieren Sie die stapelüberprüfung mit der **Check_stack** Pragma oder/GS.  
  
 Diese Warnung wird nur für die erste Funktion deklariert, die unter diesen Bedingungen ausgegeben.