---
title: Ausdrucksauswertungsfehler CXX0015 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0015
dev_langs: C++
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6f671b39fcc0027fdad5308192c5cbd8b8973717
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0015"></a>Ausdrucksauswertungsfehler CXX0015
Ausdruck zu komplex (Stapelüberlauf)  
  
 Der eingegebene Ausdruck war zu komplex oder geschachtelte zu tief für die Menge an Speicherplatz verfügbar, um die C#-ausdrucksauswertung.  
  
 Überlauf tritt gewöhnlich aufgrund von zu viele ausstehende Berechnungen.  
  
 Ordnen Sie den Ausdruck so, dass jede Komponente des Ausdrucks ausgewertet werden kann, wie sie entdeckt wird, anstatt zu warten, bis andere Teile des Ausdrucks berechnet werden soll.  
  
 Teilen Sie den Ausdruck in mehrere Befehle.  
  
 Dieser Fehler ist mit CAN0015 identisch.