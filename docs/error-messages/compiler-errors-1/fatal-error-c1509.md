---
title: Schwerwiegender Fehler C1509 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1509
dev_langs:
- C++
helpviewer_keywords:
- C1509
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fec83f6b6138eacc613e560b9da4557079d6677d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198793"
---
# <a name="fatal-error-c1509"></a>Schwerwiegender Fehler C1509
Compilerlimit: zu viele Handler für Ausnahmezustände in Funktion 'Funktion'. Vereinfachen Sie die Funktion  
  
 Der Code überschreitet ein internes Limit auf Handler für Ausnahmezustände (32.768 Staaten).  
  
 Die häufigste Ursache ist, dass die Funktion einen komplexen Ausdruck der benutzerdefinierten Klassenvariablen und arithmetische Operatoren enthält.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)  
  
1.  Gemeinsame Teilausdrücke temporären Variablen zuweisen, um Ausdrücke zu vereinfachen.  
  
2.  Teilen Sie die Funktion in kleinere Funktionen.