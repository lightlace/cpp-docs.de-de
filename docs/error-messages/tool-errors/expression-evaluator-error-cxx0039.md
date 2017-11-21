---
title: Ausdrucksauswertungsfehler CXX0039 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0039
dev_langs: C++
helpviewer_keywords:
- CXX0039
- CAN0039
ms.assetid: 8bf698d2-e015-4595-944f-72b81aa43d22
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 51f222db839917cf7ebd5cd849ab20377ad6d7e4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluator-error-cxx0039"></a>Ausdrucksauswertungsfehler CXX0039
Symbol ist nicht eindeutig  
  
 Die C-ausdrucksauswertung kann nicht welche Instanz eines Symbols für die Verwendung in einem Ausdruck bestimmt werden. Das Symbol tritt höchstens einmal in der Vererbungsstruktur.  
  
 Sie müssen den Bereichsauflösungsoperator verwenden (`::`) der Instanz, mit der im Ausdruck explizit angeben.  
  
 Dieser Fehler ist mit CAN0039 identisch.