---
title: "C-Funktionsdefinitionen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Deklaratoren, Funktionen"
  - "Deklarieren von Funktionen, Informationen über Funktionsdeklarationen"
  - "Deklarieren von Funktionen, Deklaratoren"
  - "Deklarieren von Funktionen, Variablen"
  - "Funktionsrumpf"
  - "Funktionsdeklaratoren"
  - "Funktionsdefinitionen"
  - "Funktionsparameter, Funktionsdefinitionen"
  - "Funktionen [C], Parameter"
ms.assetid: ebab23c8-6eb8-46f3-b21d-570cd8457a80
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# C-Funktionsdefinitionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Funktionsdefinition gibt den Namen der Funktion, die Typen und die Zahl der Parameter, die sie erwartungsgemäß empfangen wird, und ihren Rückgabetyp an.  Eine Funktionsdefinition enthält auch einen Funktionsrumpf mit den Deklarationen ihrer lokalen Variablen und die Anweisungen, die bestimmen, was die Funktion durchführt.  
  
## Syntax  
 *translation\-unit*:  
 *external\-declaration*  
  
 *translation\-unit external\-declaration*  
  
 *external\-declaration*: \/\* Nur für externen \(Datei\-\)Bereich zulässig \*\/  
 *function\-definition*  
  
 `declaration`  
  
 *function\-definition*: \/\* Der Deklarator hier ist der Funktionsdeklarator \*\/  
 *declaration\-specifiers*  opt *attribute\-seq* opt *declarator declaration\-list* opt *compound\-statement*  
  
 \/\* *attribute\-seq* ist Microsoft\-spezifisch \*\/  
  
 Prototypparameter sind:  
  
 *declaration\-specifiers*:  
 *storage\-class\-specifier declaration\-specifiers*  opt  
  
 *type\-specifier declaration\-specifiers*  opt  
  
 *type\-qualifier declaration\-specifiers*  opt  
  
 *declaration\-list*:  
 *declaration*  
  
 *declaration\-list\-Deklaration*  
  
 `declarator`:  
 *pointer*  opt *direct\-declarator*  
  
 *direct\-declarator*: \/\* Ein Funktionsdeklarator \*\/  
 *direct\-declarator*  **\(**  *parameter\-type\-list*  **\)** \/\* Neuer Deklarator\*\/  
  
 *direct\-declarator*  **\(**  *identifier\-list*  opt **\)** \/\* Veralteter Deklarator \*\/  
  
 Die Parameterliste in einer Definition verwendet diese Syntax:  
  
 *parameter\-type\-list*: \/\* Die Parameterliste \*\/  
 *parameter\-list*  
  
 *parameter\-list* **, ...**  
  
 *parameter\-list*:  
 *parameter\-declaration*  
  
 *parameter\-list* **,**  *parameter\-declaration*  
  
 *parameter\-declaration*:  
 *Deklarator "declaration\-specifiers"*  
  
 *declaration\-specifiers abstract declarator*  opt  
  
 Die Parameterliste in einer Funktionsdefinition im alten Format verwendet diese Syntax:  
  
 *identifier\-list*: \/\* Verwendet in veralteten Funktionsdefinitionen und Deklarationen \*\/  
 *identifier*  
  
 *identifier\-list* **,**  *identifier*  
  
 Die Syntax für den Funktionsrumpf lautet:  
  
 *compound\-statement*: \/\* Der Funktionsrumpf\*\/  
 **{**  `declaration`\-*list* opt *statement\-list* opt **}**  
  
 Die einzigen Speicherklassenspezifizierer, die eine Funktionsdeklaration ändern können, sind `extern` und **static**.  Der Bezeichner `extern` gibt an, dass von anderen Dateien auf die Funktion verwiesen werden kann; das bedeutet, der Funktionsname wird in den Linker exportiert.  Der **static**\-Bezeichner gibt an, dass auf die Funktion nicht von anderen Dateien verwiesen werden kann, d. h. der Name wird nicht vom Linker exportiert.  Wenn keine Speicherklasse in einer Funktionsdefinition steht, wird `extern` angenommen.  In jedem Fall ist die Funktion stets vom Definitionspunkt bis an das Ende der Datei sichtbar.  
  
 Der optionale *declaration\-specifiers*\-Bezeichner und der erforderliche `declarator`\-Bezeichner geben gemeinsam den Rückgabetyp und den Namen der Funktion an.  Der `declarator` ist eine Kombination aus dem Bezeichner, der die Funktion benennt, und den Klammern hinter dem Funktionsnamen.  Der optionale *attribute\-seq*\-Nichtterminal ist eine Microsoft\-spezifische Funktion, die unter [Funktionsattribute](../c-language/function-attributes.md) definiert wird.  
  
 *direct\-declarator* \(in der `declarator`\-Syntax\) legt den Namen der Funktion, die definiert wird, fest sowie die Bezeichner ihrer Parameter.  Wenn *direct\-declarator* eine *parameter\-type\-list* enthält, gibt die Liste die Typen aller Parameter an.  Eine solche Deklaration dient auch als Funktionsprototyp für spätere Aufrufe der Funktion.  
  
 Eine `declaration` in der *declaration\-list* in den Funktionsdefinitionen kann keinen *storage\-class\-specifier* außer **register** enthalten.  Der *type\-specifier* in der *declaration\-specifiers*\-Syntax kann nur dann weggelassen werden, wenn die **register**\-Speicherklasse für einen Wert vom Typ `int` angegeben wird.  
  
 Die *compound\-statement* ist der Funktionsrumpf, der lokale Variablendeklarationen, Verweise auf extern deklarierte Elemente und Anweisungen enthält.  
  
 Die Abschnitte [Funktionsattribute](../c-language/function-attributes.md), [Speicherklasse](../c-language/storage-class.md), [Rückgabetyp](../c-language/return-type.md), [Parameter](../c-language/parameters.md) und [Funktionsrumpf](../c-language/function-body.md) beschreiben die Komponenten der Funktionsdefinition im Detail.  
  
## Siehe auch  
 [Funktionen](../c-language/functions-c.md)