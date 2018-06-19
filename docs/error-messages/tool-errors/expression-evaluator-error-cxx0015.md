---
title: Ausdrucksauswertungsfehler CXX0015 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0015
dev_langs:
- C++
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 945dbda4759fa2989acb0411d1a3216a5e9a036c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33297608"
---
# <a name="expression-evaluator-error-cxx0015"></a>Ausdrucksauswertungsfehler CXX0015
Ausdruck zu komplex (Stapelüberlauf)  
  
 Der eingegebene Ausdruck war zu komplex oder geschachtelte zu tief für die Menge an Speicherplatz verfügbar, um die C#-ausdrucksauswertung.  
  
 Überlauf tritt gewöhnlich aufgrund von zu viele ausstehende Berechnungen.  
  
 Ordnen Sie den Ausdruck so, dass jede Komponente des Ausdrucks ausgewertet werden kann, wie sie entdeckt wird, anstatt zu warten, bis andere Teile des Ausdrucks berechnet werden soll.  
  
 Teilen Sie den Ausdruck in mehrere Befehle.  
  
 Dieser Fehler ist mit CAN0015 identisch.