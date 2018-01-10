---
title: 'NMAKE: Schwerwiegender Fehler U1070 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U1070
dev_langs: C++
helpviewer_keywords: U1070
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5adf5321c96341cfce633a2329a52360be8a45da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1070"></a>NMAKE: Schwerwiegender Fehler U1070
Wechseln Sie in der Makrodefinition 'Makroname'  
  
 Die angegebene Makrodefinition enthalten ein Makro, dessen Definition das angegebene Makro enthalten sind. Zirkuläre Makrodefinitionen sind ungültig.  
  
## <a name="example"></a>Beispiel  
 Die folgenden Makrodefinitionen  
  
```  
ONE=$(TWO)  
TWO=$(ONE)  
```  
  
 Führen Sie die folgende Fehlermeldung:  
  
```  
cycle in macro definition 'TWO'  
```