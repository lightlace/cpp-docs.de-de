---
title: Ausdrucksauswertungsfehler CXX0033 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- CXX0033
dev_langs:
- C++
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 49f2b6221d385587fa5e62af51d37eb7d3b78872
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0033"></a>Ausdrucksauswertungsfehler CXX0033
Fehler in OMF-Typinformationen  
  
 Die ausführbare Datei haben kein gültiges Objekt Modul Format (OMF) für das Debuggen.  
  
 Dieser Fehler ist mit CAN0033 identisch.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Die ausführbare Datei wurde nicht mit dem Linker, die mit dieser Version von Visual C++ erstellt. Verknüpfen Sie den Objektcode, mit der aktuellen Version von LINK.exe.  
  
2.  Die .exe-Datei ist möglicherweise beschädigt. Erneut kompilieren Sie und verknüpfen Sie das Programm.