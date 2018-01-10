---
title: Compilerwarnung (Stufe 4) C4234 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4234
dev_langs: C++
helpviewer_keywords: C4234
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 68f4b2c3b51caf5e0438c2ead293823885b73157
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4234"></a>Compilerwarnung (Stufe 4) C4234
nicht dem Standard entsprechende Erweiterung: ' Schlüsselwort ' für die zukünftige Verwendung reserviert  
  
 Der Compiler implementiert nicht noch das Schlüsselwort, das Sie verwendet.  
  
 Diese Warnung wird automatisch zu einem Fehler heraufgestuft. Wenn Sie dieses Verhalten ändern möchten, verwenden Sie [#pragma Warning](../../preprocessor/warning.md). Geben Sie beispielsweise Folgendes ein, um C4234 in eine Warnung der Stufe 4 Stellen,  
  
```  
#pragma warning(2:4234)  
```  
  
 in der Quellcodedatei.