---
title: NULL-Anweisung (C) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- semicolon, C null statement
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 72576ce6-26d0-4379-be65-fee522088790
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 4ead6c1bb4ad5330ed23c90019ec4e5e03282fb8
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="null-statement-c"></a>NULL-Anweisung (C)
Eine "NULL-Anweisung" ist eine Anweisung, die nur ein Semikolon enthält. Sie kann an jeder Stelle stehen, an der eine Anweisung erwartet wird. Wenn eine NULL-Anweisung ausgeführt wird, passiert nichts. Dies ist die korrekte Methode, eine NULL-Anweisung zu codieren:  
  
## <a name="syntax"></a>Syntax  
  
```  
  
;  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Anweisungen wie **do**, **for**, **if** und `while` erfordern als Anweisungstext eine ausführbare Anweisung. Die NULL-Anweisung erfüllt die Syntaxanforderung in Fällen, die keinen substanziellen Anweisungstext benötigen.  
  
 Wie bei jeder anderen C-Anweisung können Sie vor einer NULL-Anweisung eine Bezeichnung einfügen. Um ein Element zu bezeichnen, das keine Anweisung ist, z. B. die schließende Klammer einer Verbundanweisung, können Sie eine NULL-Anweisung bezeichnen und direkt vor dem Element einfügen, um dasselbe Ergebnis zu erzielen.  
  
 In diesem Beispiel wird die NULL-Anweisung veranschaulicht:  
  
```  
for ( i = 0; i < 10; line[i++] = 0 )  
     ;  
```  
  
 Im Beispiel initialisiert der Schleifenausdruck der **for**-Anweisung `line[i++] = 0` die ersten 10 Elemente von `line` mit 0. Der Anweisungstext ist eine NULL-Anweisung, da keine weiteren Anweisungen erforderlich sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen](../c-language/statements-c.md)
