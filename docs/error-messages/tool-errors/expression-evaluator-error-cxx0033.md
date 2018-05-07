---
title: Ausdrucksauswertungsfehler CXX0033 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0033
dev_langs:
- C++
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 720b1aec6c9be16879119bc0e8148a301507577a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="expression-evaluator-error-cxx0033"></a>Ausdrucksauswertungsfehler CXX0033
Fehler in OMF-Typinformationen  
  
 Die ausführbare Datei haben kein gültiges Objekt Modul Format (OMF) für das Debuggen.  
  
 Dieser Fehler ist mit CAN0033 identisch.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Die ausführbare Datei wurde nicht mit dem Linker, die mit dieser Version von Visual C++ erstellt. Verknüpfen Sie den Objektcode, mit der aktuellen Version von LINK.exe.  
  
2.  Die .exe-Datei ist möglicherweise beschädigt. Erneut kompilieren Sie und verknüpfen Sie das Programm.