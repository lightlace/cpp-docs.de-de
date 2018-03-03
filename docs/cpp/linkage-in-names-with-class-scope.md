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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 20e8204510f6f6e924e205b89dc9f95734b4b893
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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