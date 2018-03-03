---
title: Funktionsrumpf | Microsoft-Dokumentation
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
- functions [C], syntax
- variables, function syntax
- function definitions, function body
- function body
ms.assetid: f7e74822-fac8-4dc8-8f3a-2b1611da4640
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a0c85ecf0752ff34bf5b61e42309360f2bc4d448
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="function-body"></a>Funktionsrumpf
Ein "Funktionsrumpf" entspricht einer Verbundanweisung mit den Anweisungen, die die Aufgabe der Funktion angeben.  
  
## <a name="syntax"></a>Syntax  
 *function-definition*:  
 *declaration-specifiers* opt*attribute-seq* opt*declarator declaration-list* opt*compound-statement*  
  
 /\* *attribute-seq* ist Microsoft-spezifisch */  
  
 *compound-statement*: /\* Der Funktionsrumpf \*/  
 **{**  *declaration-list* opt*statement-list* opt**}**  
  
 Variablen, die in einem Funktionsrumpf „lokal“ deklariert werden, weisen die **auto**-Speicherklasse auf, sofern nicht anders angegeben. Wenn die Funktion aufgerufen wird, wird Speicherplatz für die lokalen Variablen erstellt, und lokale Initialisierungen werden ausgeführt. Die Ausführungssteuerung wird an die erste Anweisung in *compound-statement* übergeben und fährt fort, bis eine `return`-Anweisung ausgeführt wurde oder das Ende des Funktionsrumpfs erreicht ist. Anschließend wird die Steuerung wieder an den Punkt zurückgegeben, an dem die Funktion aufgerufen wurde.  
  
 Eine `return`-Anweisung, die einen Ausdruck enthält, muss ausgeführt werden, wenn die Funktion einen Wert zurückgeben soll. Der Rückgabewert einer Funktion ist nicht definiert, wenn keine `return`-Anweisung ausgeführt wird oder wenn die `return`-Anweisung keinen Ausdruck enthält.  
  
## <a name="see-also"></a>Siehe auch  
 [C-Funktionsdefinitionen](../c-language/c-function-definitions.md)