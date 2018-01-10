---
title: Schwerwiegender Fehler C1004 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1004
dev_langs: C++
helpviewer_keywords: C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 528147eceadd35cc0d9fe656bdc7ce7965339a0a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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