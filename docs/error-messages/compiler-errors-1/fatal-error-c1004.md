---
title: Schwerwiegender Fehler C1004 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1004
dev_langs:
- C++
helpviewer_keywords:
- C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c6a9e74d7918e1cb2c9190c87f4f1ec75f89237b
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1004"></a>Schwerwiegender Fehler C1004
Unerwartetes Dateiende gefunden  
  
 Der Compiler hat das Ende einer Quelldatei erreicht, ohne ein Konstrukt aufzulösen. Der Code möglicherweise eines der folgenden Elemente fehlen:  
  
-   Eine schließende Klammer  
  
-   Eine schließende Klammer  
  
-   Ein schließendes Kommentarzeichen (* /)  
  
-   Ein Semikolon  
  
 Um diesen Fehler zu beheben, überprüfen Sie Folgendes:  
  
-   Das Standard-Laufwerk verfügt nicht über genügend Speicherplatz für temporäre Dateien, die über doppelt so viel Speicherplatz wie die Quelldatei erforderlich sind.  
  
-   Ein `#if` -Direktive, die auf "false" fehlt eine schließende ergibt `#endif` Richtlinie.  
  
-   Eine Quelldatei endet nicht mit einem Wagenrücklauf und Zeilenvorschub.  
  
 Im folgenden Beispiel wird C1004 generiert:  
  
```  
// C1004.cpp  
#if TEST  
int main() {}  
// C1004  
```  
  
 Mögliche Lösung:  
  
```  
// C1004b.cpp  
#if TEST  
#endif  
  
int main() {}  
```
