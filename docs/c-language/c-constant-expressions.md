---
title: "C-Ausdr&#252;cke (konstant) | Microsoft Docs"
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
  - "Konstante Ausdrücke"
  - "Konstante Ausdrücke, Syntax"
  - "Ausdrücke [C++], Konstant"
ms.assetid: d48a6c47-e44c-4be2-9c8b-7944c7ef8de7
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# C-Ausdr&#252;cke (konstant)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein konstanter Ausdruck wird zur Kompilierzeit, nicht zur Laufzeit, ausgewertet und kann an einem beliebigen Ort verwendet werden, an dem eine Konstante verwendet werden kann.  Der konstante Ausdruck muss eine Konstante auswerten, die sich im Bereich der darstellbaren Werte für diesen Typ befindet.  Die Operanden eines konstanten Ausdrucks können ganzzahlige Konstanten, Zeichenkonstanten, Gleitkommakonstanten, Enumerationskonstanten, Typumwandlungen, `sizeof`\-Ausdrücke und andere konstante Ausdrücke sein.  
  
## Syntax  
 *constant\-expression*:  
 *conditional\-expression*  
  
 *Bedingter Ausdruck*:  
 *Ausdruck für 'logisches OR'*  
  
 *logical\-OR\-expression* **?**  *expression* **:**  *conditional\-expression*  
  
 *expression*:  
 *assignment\-expression*  
  
 *expression* **,**  *assignment\-expression*  
  
 *assignment\-expression*:  
 *conditional\-expression*  
  
 *unary\-expression assignment\-operator assignment\-expression*  
  
 *assignment\-operator*: Einer von  
 **\= \*\= \/\= %\= \+\= –\= \<\<\= \>\>\= &\= ^\= &#124;\=**  
  
 Die Non\-Terminals für den Strukturdeklarator, den Enumerator, den direkten Deklarator, den direkt\-abstrakten Deklarator und die gekennzeichnete Anweisung enthält das Non\-Terminal *constant\-expression*.  
  
 Ein ganzzahliger konstanter Ausdruck muss verwendet werden, um die Größe eines Bitfeldmembers einer Struktur, den Wert einer Enumerationskonstante, die Größe eines Arrays oder den Wert einer **case**\-Konstante anzugeben.  
  
 Konstante Ausdrücke, die in den Präprozessordirektiven verwendet werden, unterliegen zusätzlichen Einschränkungen.  Daher sind sie als "eingeschränkte konstante Ausdrücke" bekannt. Ein eingeschränkter konstanter Ausdruck kann keine `sizeof`\-Ausdrücke, Enumerationskonstanten, Typumwandlungen zu keinem Typ oder Float\-Konstanten enthalten.  Er kann jedoch den speziellen konstanten Ausdruck `defined (`*identifier*`)` enthalten.  
  
## Siehe auch  
 [Operanden und Ausdrücke](../c-language/operands-and-expressions.md)