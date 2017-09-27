---
title: "Verknüpfung in Namen mit Klassenbereich | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- scope [C++], linkage rules
- linkage [C++], scope linkage rules
- names [C++], scope linkage rules
- classes [C++], scope
- external linkage, scope linkage rules
- class names [C++], linkage
- classes [C++], names
- scope [C++], class names
- class scope [C++], linkage in names with
ms.assetid: 45275ff3-6e94-4967-82c8-ba540ef4da28
caps.latest.revision: 8
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 37a0dcca1da0ae56a8144adf862eda89bfb1c4d6
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="linkage-in-names-with-class-scope"></a>Verknüpfung in Namen mit Klassenbereich
Die folgenden Verknüpfungsregeln gelten für Namen mit Klassenbereich:  
  
-   Statische Klassenmember verfügen über externe Verknüpfungen.  
  
-   Klassenmemberfunktionen weisen externe Verknüpfungen auf.  
  
-   Enumeratoren und `typedef`-Namen haben keine Verknüpfungen.  
  
 **Microsoft-spezifisch**  
  
-   Die als `friend`-Funktionen deklarierten Funktionen müssen externe Verknüpfungen aufweisen. Das Deklarieren einer statischen Funktion als ein `friend` generiert einen Fehler.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Programm und Verknüpfung](../cpp/program-and-linkage-cpp.md)
