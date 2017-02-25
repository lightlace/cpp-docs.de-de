---
title: "Umwandlungsoperatoren | Microsoft Docs"
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
  - "Umwandlungsoperatoren"
  - "Operatoren [C++], Umwandlung"
  - "Typumwandlungen, Operatoren"
  - "Typkonvertierung, Umwandlungsoperatoren"
ms.assetid: 43b90bbd-39ef-43e6-ae5d-e8a67a01de40
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Umwandlungsoperatoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Typumwandlung stellt eine Möglichkeit zum expliziten Konvertieren des Typs eines Objekts in einer bestimmten Situation bereit.  
  
## Syntax  
 *Umwandlungsausdruck*:  
 *unary\-expression*  
  
 **\(**  *type\-name*  **\)**  *cast\-expression*  
  
 Der Compiler behandelt *cast\-expression* als *type\-name*\-Typ, nachdem eine Typumwandlung vorgenommen wurde.  Umwandlungen können verwendet werden, um Objekte eines beliebigen skalaren Typs in einen oder aus einem anderen skalaren Typ zu konvertieren.  Explizite Typumwandlungen werden durch dieselben Regeln eingeschränkt, die die Auswirkungen von impliziten Konvertierungen bestimmen, die unter [Zuweisungskonvertierungen](../c-language/assignment-conversions.md) erläutert werden.  Zusätzliche Einschränkungen für Typumwandlungen ergeben sich möglicherweise aus den tatsächlichen Größen oder der Darstellung bestimmter Typen.  Weitere Informationen zu den tatsächlichen Größen ganzzahliger Typen finden Sie unter [Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md).  Weitere Informationen zu Typumwandlungen finden Sie unter [Typumwandlungskonvertierungen](../c-language/type-cast-conversions.md).  
  
## Siehe auch  
 [Umwandlungsoperator: \(\)](../cpp/cast-operator-parens.md)