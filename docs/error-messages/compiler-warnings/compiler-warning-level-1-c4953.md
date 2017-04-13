---
title: Compilerwarnung (Stufe 1) C4953 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4953
dev_langs:
- C++
helpviewer_keywords:
- C4953
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: d0b8ba97d493cb6e840be1023f7c6bd29a5cbd1a
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4953"></a>Compilerwarnung (Stufe 1) C4953
Inlinee "function" wurde bearbeitet, seit die Konfigurationsdaten erfasst wurden. Die Profildaten werden nicht verwendet  
  
 Bei Verwendung [/LTCG: PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), der Compiler ein Eingabemodul, die nach der neu kompilierten `/LTCG:PGINSTRUMENT` und verfügt über eine Funktion (***Funktion***), die bearbeitet wurde und identifiziert Sie die Funktion in vorhandenen Testläufen als Kandidat für inlining. Infolge der Neukompilierung des Moduls ist die Funktion jedoch kein Kandidat für Inlining mehr.  
  
 Diese Warnung dient nur zu Informationszwecken. Um diese Warnung zu beheben, führen Sie `/LTCG:PGINSTRUMENT`aus, wiederholen alle Testläufe und führen `/LTCG:PGOPTIMIZE`aus.  
  
 Bei Verwendung von `/LTCG:PGOPTIMIZE` würde diese Warnung durch einen Fehler ersetzt.
