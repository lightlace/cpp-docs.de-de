---
title: Compilerfehler C3398 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3398
dev_langs:
- C++
helpviewer_keywords:
- C3398
ms.assetid: 26f8c8a4-526f-415b-8047-155c5cd4f180
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4b332346dd8e8b7e906e961c86805ad0564f0f79
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3398"></a>Compilerfehler C3398
'Operator': Konvertierung von 'function_signature' in 'function_pointer' nicht möglich. Der Quellausdruck muss ein Funktionssymbol sein.  
  
 Wenn die [__clrcall](../../cpp/clrcall.md) -Aufrufkonvention bei der Kompilierung mit **/clr**nicht angegeben ist, generiert der Compiler zwei Einstiegspunkte (Adressen) für jede Funktion, einen systemeigener Einstiegspunkt und einen verwalteten Einstiegspunkt.  
  
 Standardmäßig gibt der Compiler den systemeigenen Einstiegspunkt zurück, aber es gibt einige Fälle, in denen der verwaltete Einstiegspunkt erwünscht ist (z. B. beim Zuweisen der Adresse zu einem `__clrcall` -Funktionszeiger). Damit der Compiler den verwalteten Einstiegspunkt in einer Zuordnung zuverlässig auswählen kann, muss die rechte Seite ein Funktionssymbol sein.