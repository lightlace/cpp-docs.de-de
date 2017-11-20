---
title: C-Funktionsdefinitionen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- function declarators
- function definitions
- declaring functions, about function declarations
- declaring functions, declarators
- functions [C], parameters
- declarators, functions
- function parameters, function definitions
- function body
- declaring functions, variables
ms.assetid: ebab23c8-6eb8-46f3-b21d-570cd8457a80
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c57536aed0c53e8f74ac6031632e60a403e5ce30
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="c-function-definitions"></a>C-Funktionsdefinitionen
Eine Funktionsdefinition gibt den Namen der Funktion, die Typen und die Zahl der Parameter, die sie erwartungsgemäß empfangen wird, und ihren Rückgabetyp an. Eine Funktionsdefinition enthält auch einen Funktionsrumpf mit den Deklarationen ihrer lokalen Variablen und die Anweisungen, die bestimmen, was die Funktion durchführt.  
  
## <a name="syntax"></a>Syntax  
 *translation-unit*:  
 *external-declaration*  
  
 *translation-unit external-declaration*  
  
 *external-declaration*: /\* Nur für externen (Datei-) Bereich zulässig \*/  
 *function-definition*  
  
 `declaration`  
  
 *function-definition*: /\* Der Deklarator hier ist der Funktionsdeklarator \*/  
 *declaration-specifiers* opt*attribute-seq* opt*declarator declaration-list* opt*compound-statement*  
  
 /\* *attribute-seq* ist Microsoft-spezifisch */  
  
 Prototypparameter sind:  
  
 *declaration-specifiers*:  
 *storage-class-specifier declaration-specifiers* opt  
  
 *type-specifier declaration-specifiers* opt  
  
 *type-qualifier declaration-specifiers* opt  
  
 *declaration-list*:  
 *declaration*  
  
 *declaration-list-Deklaration*  
  
 `declarator`:  
 *pointer* opt*direct-declarator*  
  
 *direct-declarator*: /\* Ein Funktionsdeklarator \*/  
 *direct-declarator*  **(**  *parameter-type-list*  **)** /* Neuer Deklarator \*/  
  
 *direct-declarator*  **(**  *identifier-list* opt**)** /* Veralteter Deklarator \*/  
  
 Die Parameterliste in einer Definition verwendet diese Syntax:  
  
 *parameter-type-list*: /\* Die Parameterliste \*/  
 *parameter-list*  
  
 *parameter-list* **, ...**  
  
 *parameter-list*:  
 *parameter-declaration*  
  
 *parameter-list* **,**  *parameter-declaration*  
  
 *parameter-declaration*:  
 *declaration-specifiers-Deklarator*  
  
 *declaration-specifiers abstract declarator* opt  
  
 Die Parameterliste in einer Funktionsdefinition im alten Format verwendet diese Syntax:  
  
 *identifier-list*: /\* Verwendet in veralteten Funktionsdefinitionen und Deklarationen \*/  
 *identifier*  
  
 *identifier-list* **,**  *identifier*  
  
 Die Syntax für den Funktionsrumpf lautet:  
  
 *compound-statement*: /\* Der Funktionsrumpf \*/  
 **{**  `declaration`-*list* opt*statement-list* opt**}**  
  
 Die einzigen Speicherklassenspezifizierer, die eine Funktionsdeklaration ändern können, sind `extern` und **static**. Der Bezeichner `extern` gibt an, dass von anderen Dateien auf die Funktion verwiesen werden kann; das bedeutet, der Funktionsname wird in den Linker exportiert. Der **static**-Bezeichner gibt an, dass auf die Funktion nicht von anderen Dateien verwiesen werden kann, d.h., der Name wird nicht vom Linker exportiert. Wenn keine Speicherklasse in einer Funktionsdefinition steht, wird `extern` angenommen. In jedem Fall ist die Funktion stets vom Definitionspunkt bis an das Ende der Datei sichtbar.  
  
 Der optionale *declaration-specifiers*-Bezeichner und der erforderliche `declarator`-Bezeichner geben gemeinsam den Rückgabetyp und den Namen der Funktion an. Der `declarator` ist eine Kombination aus dem Bezeichner, der die Funktion benennt, und den Klammern hinter dem Funktionsnamen. Der optionale *attribute-seq*-Nichtterminal ist eine Microsoft-spezifische Funktion, die unter [Funktionsattribute](../c-language/function-attributes.md) definiert wird.  
  
 *direct-declarator* (in der `declarator`-Syntax) legt den Namen der Funktion fest, die definiert wird, sowie die Bezeichner ihrer Parameter. Wenn *direct-declarator* eine *parameter-type-list* enthält, gibt die Liste die Typen aller Parameter an. Eine solche Deklaration dient auch als Funktionsprototyp für spätere Aufrufe der Funktion.  
  
 Eine `declaration` in der *declaration-list* in den Funktionsdefinitionen kann keinen *storage-class-specifier* außer **register** enthalten. *type-specifier* in der *declaration-specifiers*-Syntax kann nur dann weggelassen werden, wenn die **register**-Speicherklasse für einen Wert vom Typ `int` angegeben wird.  
  
 Die *compound-statement* ist der Funktionsrumpf, der lokale Variablendeklarationen, Verweise auf extern deklarierte Elemente und Anweisungen enthält.  
  
 Die Abschnitte [Funktionsattribute](../c-language/function-attributes.md), [Speicherklasse](../c-language/storage-class.md), [Rückgabetyp](../c-language/return-type.md), [Parameter](../c-language/parameters.md) und [Funktionsrumpf](../c-language/function-body.md) beschreiben die Komponenten der Funktionsdefinition im Detail.  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../c-language/functions-c.md)