---
title: C – Inkrementierungs- und Dekrementierungsoperatoren in Postfixnotation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- increment operators, syntax
- scalar operators
- types [C], scalar
ms.assetid: 56ba218d-65f9-405f-8684-caccc0ca33aa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7dc0b4c71aafe3435def0b96ae621c60ff640dc0
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751210"
---
# <a name="c-postfix-increment-and-decrement-operators"></a>C - Inkrementierungs- und Dekrementierungsoperatoren in Postfixnotation
Operanden der Postfix-Inkrement- und Postfix-Dekrementoperatoren sind skalare Typen, die änderbare L-Werte sind.  
  
## <a name="syntax"></a>Syntax

*postfix-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **++**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **--**

Das Ergebnis des Postfix-Inkrementoperators oder Postfix-Dekrementoperators ist der Wert des Operanden. Nachdem das Ergebnis erreicht ist, wird der Wert des Operanden (erhöht oder verringert). Der folgende Code veranschaulicht den Postfix-Inkrementoperator.  
  
```  
if( var++ > 0 )  
    *p++ = *q++;  
```  
  
In diesem Beispiel wird die Variable `var` mit 0 verglichen und dann erhöht. Wenn `var` vor der Erhöhung positiv war, wird die nächste Anweisung ausgeführt. Zuerst wird der Wert des Objekts, auf das durch `q` gezeigt wird, dem Objekt zugewiesen, auf das durch `p` gezeigt wird. Anschließend werden `q` und `p` erhöht.  
  
## <a name="see-also"></a>Siehe auch

[Inkrementierungs- und Dekrementierungsoperatoren in Postfixnotation: ++ und --](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)