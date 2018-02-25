---
title: "Präprozessor-Operatoren | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor operators
- operators [C++], preprocessor
ms.assetid: 884126d1-0ce2-48b6-9e06-8a2d7c4a9656
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 551b2c3ba8a5055fc6b6dfd1b94c461c37e72209
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="preprocessor-operators"></a>Präprozessoroperatoren
Vier präprozessorspezifische Operatoren werden im Kontext der `#define`-Direktive verwendet (die jeweilige Zusammenfassung finden Sie in der nachfolgenden Liste). Zeichenfolgenoperatoren, Zeichenoperatoren und Operatoren zum Einfügen eines Tokens werden in den nächsten drei Abschnitten erläutert. Informationen zu den **definiert** -Operator, finden Sie unter [#if-, #elif, #else- und #endif-Direktiven](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).  
  
|Operator|Aktion|  
|--------------|------------|  
|[Zeichenfolgenoperator (#)](../preprocessor/stringizing-operator-hash.md)|Bewirkt, dass das entsprechende tatsächliche Argument in doppelte Anführungszeichen eingeschlossen wird.|  
|[Zeichenoperator (#@)](../preprocessor/charizing-operator-hash-at.md)|Bewirkt, dass das entsprechende Argument in einfache Anführungszeichen eingeschlossen und als Zeichen behandelt wird (Microsoft-spezifisch).|  
|[Tokeneinfügender Operator (##)](../preprocessor/token-pasting-operator-hash-hash.md)|Ermöglicht das Verketten der Token, die als tatsächliche Argumente verwendet werden, um andere Token zu bilden.|  
|[definierter operator](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|Vereinfacht das Schreiben von zusammengesetzten Ausdrücken in bestimmten Makroanweisungen.|  
  
## <a name="see-also"></a>Siehe auch  
 [Präprozessordirektiven](../preprocessor/preprocessor-directives.md)   
 [Vordefinierte Makros](../preprocessor/predefined-macros.md)   
 [C/C++-Präprozessorreferenz](../preprocessor/c-cpp-preprocessor-reference.md)