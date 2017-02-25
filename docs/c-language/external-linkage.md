---
title: "Externe Verkn&#252;pfung | Microsoft Docs"
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
  - "Externe Verknüpfung"
  - "Externe Verknüpfung, Informationen über die externe Verknüpfung"
  - "Verknüpfung [C++], Extern"
ms.assetid: a6f8ea69-b405-4cdd-bf12-ad5462b73183
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Externe Verkn&#252;pfung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn die erste Deklaration auf Dateigültigkeitsebene für einen Bezeichner nicht den **static**\-Speicherklassenspezifizierer verwendet, verfügt das Objekt über eine externe Bindung.  
  
 Wenn die Deklaration eines Bezeichners für eine Funktion über keinen *storage\-class\-specifier* verfügt, wird seine Bindung genauso bestimmt, als ob sie mit dem *storage\-class\-specifier* `extern` deklariert worden wäre.  Wenn die Deklaration eines Bezeichners für ein Objekt dateiweit gilt und keinen *storage\-class\-specifier* enthält, ist die Bindung extern.  
  
 Der Name eines Bezeichners mit externer Bindung legt dieselbe Funktion oder dasselbe Datenobjekt fest wie jede andere Deklaration für denselben Namen mit externer Bindung.  Die beiden Deklarationen können sich in derselben Übersetzungseinheit oder in verschiedenen Übersetzungseinheiten befinden.  Wenn das Objekt oder die Funktion auch eine globale Lebensdauer besitzt, ist das Objekt oder die Funktion im gesamten Programm verfügbar.  
  
## Siehe auch  
 [Verwenden von "extern" zur Angabe der Verknüpfung](../cpp/using-extern-to-specify-linkage.md)