---
title: Makros und C++ | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- macros, C++
- macros
ms.assetid: 83a344c1-73c9-4ace-8b93-cccfb62c6133
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b2af5a370502069befa4a9410e8b324ccc3756e6
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="macros-and-c"></a>Makros und C++
C++ bietet neue Funktionen, von denen einige die Funktionen ablösen, die vom ANSI-C-Präprozessor bereitgestellt werden. Diese neuen Funktionen erweitern die Typsicherheit und die Voraussagbarkeit der Sprache:  
  
-   In C++ können Objekte, die als deklariert **const** in Konstanten Ausdrücken verwendet werden können. Dadurch können Programme Konstanten deklarieren, die Typ- und Wertinformationen haben, und Enumerationen, die mit dem Debugger symbolisch angezeigt werden können. Die Verwendung der `#define`-Präprozessordirektive zum Definieren von Konstanten ist weniger genau. Kein Speicherplatz zugeordnet, für eine **const** -Objekt, es sei denn, ein Ausdruck, der die Adresse akzeptiert im Programm gefunden wird.  
  
-   Funktionstypmakros werden von der C++-Inlinefunktion abgelöst. Im Vergleich zu Makros haben Inlinefunktionen folgende Vorteile:  
  
    -   Typsicherheit. Inlinefunktionen unterliegen derselben Typüberprüfung wie normale Funktionen. Makros sind nicht typsicher.  
  
    -   Korrekte Behandlung von Argumenten, die Nebeneffekte haben. Inlinefunktionen werten vor dem Eintreten in den Funktionstext die Ausdrücke aus, die als Argumente bereitgestellt werden. Daher ist es nicht möglich, dass ein Ausdruck mit Nebeneffekten unsicher ist.  
  
 Weitere Informationen zu Inlinefunktionen finden Sie unter [Inline __inline, \__forceinline](../cpp/inline-functions-cpp.md).  
  
 Aus Gründen der Abwärtskompatibilität werden alle Präprozessorfunktionen, die in ANSI C und in früheren C++-Spezifikationen vorhanden sind, für Microsoft C++ beibehalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Vordefinierte Makros](../preprocessor/predefined-macros.md)   
 [Makros (C/C++)](../preprocessor/macros-c-cpp.md)