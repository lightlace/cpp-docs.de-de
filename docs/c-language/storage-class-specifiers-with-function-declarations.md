---
title: Speicherklassenspezifizierer mit Funktionsdeklarationen | Microsoft-Dokumentation
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
- function specifiers, storage class
- declaring functions, specifiers
- external declarations
- specifiers, function
- external linkage, function declarations
- external linkage, storage-class specifiers
ms.assetid: 801d7df2-efa9-4924-a725-274a5654cfd4
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 168125dcae2561cc9aa609dc19a09b1b7dcd6e6a
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="storage-class-specifiers-with-function-declarations"></a>Speicherklassenspezifizierer mit Funktionsdeklarationen
Sie können in Funktionsdeklarationen entweder den **static**-Speicherklassenspezifizierer oder den `extern`-Speicherklassenspezifizierer verwenden. Funktionen besitzen immer eine globale Lebensdauer.  
  
 **Microsoft-spezifisch**  
  
 Funktionsdeklarationen auf der internen Ebene haben dieselbe Bedeutung wie Funktionsdeklarationen auf externer Ebene. Dies bedeutet, dass eine Funktion nach der Deklaration in der gesamten Übersetzungseinheit sichtbar ist, selbst wenn sie im lokalen Gültigkeitsbereich deklariert wurde.  
  
 **Ende Microsoft-spezifisch**  
  
 Die Sichtbarkeitsregeln für Funktionen weichen geringfügig von den Regeln für Variablen ab:  
  
-   Eine Funktion, die als **static** deklariert wird, ist nur innerhalb der Quelldatei sichtbar, in der sie definiert ist. Funktionen in der gleichen Quelldatei können die **static**-Funktion aufrufen, aber Funktionen in anderen Quelldateien können auf sie nicht direkt anhand ihres Namens zugreifen. Sie können eine weitere **static**-Funktion gleichen Namens in einer anderen Quelldatei deklarieren, ohne dass ein Konflikt auftritt.  
  
-   Die Funktionen, die als `extern` deklariert werden, sind in allen Quelldateien im Programm sichtbar (es sei denn, dass Sie später eine solche Funktion erneut als **static** deklarieren). Jede Funktion kann eine `extern`-Funktion aufrufen.  
  
-   Funktionsdeklarationen, die die Speicherklassenspezifizierer auslassen, sind standardmäßig `extern`.  
  
 **Microsoft-spezifisch**  
  
 Microsoft lässt eine Neudefinition eines `extern`-Bezeichners als **static** zu.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [C-Speicherklassen](../c-language/c-storage-classes.md)
