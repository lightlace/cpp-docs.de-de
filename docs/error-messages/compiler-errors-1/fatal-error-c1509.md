---
title: Schwerwiegender Fehler C1509 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1509
dev_langs:
- C++
helpviewer_keywords:
- C1509
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 22cb22ea2186b16fd98d2714779b2475c51d15bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1509"></a>Schwerwiegender Fehler C1509
Compilerlimit: zu viele Handler für Ausnahmezustände in Funktion 'Funktion'. Vereinfachen Sie die Funktion  
  
 Der Code überschreitet ein internes Limit auf Handler für Ausnahmezustände (32.768 Staaten).  
  
 Die häufigste Ursache ist, dass die Funktion einen komplexen Ausdruck der benutzerdefinierten Klassenvariablen und arithmetische Operatoren enthält.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)  
  
1.  Gemeinsame Teilausdrücke temporären Variablen zuweisen, um Ausdrücke zu vereinfachen.  
  
2.  Teilen Sie die Funktion in kleinere Funktionen.