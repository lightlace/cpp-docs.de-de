---
title: Schwerwiegender Fehler C1004 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1004
dev_langs:
- C++
helpviewer_keywords:
- C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d88f76c00c8f5b36acf238f0da88e908eac6dbe8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33197168"
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