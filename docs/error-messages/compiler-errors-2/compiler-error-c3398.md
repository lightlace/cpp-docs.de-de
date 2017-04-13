---
title: Compilerfehler C3398 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3398
dev_langs:
- C++
helpviewer_keywords:
- C3398
ms.assetid: 26f8c8a4-526f-415b-8047-155c5cd4f180
caps.latest.revision: 7
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
ms.openlocfilehash: 66bd229369456da18d8bed60b25b6e6b07e03f27
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3398"></a>Compilerfehler C3398
'Operator': Konvertierung von 'function_signature' in 'function_pointer' nicht möglich. Der Quellausdruck muss ein Funktionssymbol sein.  
  
 Wenn die [__clrcall](../../cpp/clrcall.md) -Aufrufkonvention wird nicht angegeben, bei der Kompilierung mit **"/ CLR"**, generiert der Compiler zwei Einstiegspunkte (Adressen) für jede Funktion, einen systemeigener Einstiegspunkt und einen verwalteten Einstiegspunkt.  
  
 Standardmäßig gibt der Compiler den systemeigenen Einstiegspunkt zurück, aber es gibt einige Fälle, in denen der verwaltete Einstiegspunkt erwünscht ist (z. B. beim Zuweisen der Adresse zu einem `__clrcall` -Funktionszeiger). Damit der Compiler den verwalteten Einstiegspunkt in einer Zuordnung zuverlässig auswählen kann, muss die rechte Seite ein Funktionssymbol sein.
