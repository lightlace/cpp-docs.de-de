---
title: '&lt;limits&gt; | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- limits/std::<limits>
- <limits>
dev_langs:
- C++
helpviewer_keywords:
- limits header
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: afcdfd235996c34a9c575e169b5a1c3cf3736478
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ltlimitsgt"></a>&lt;limits&gt;
Definiert die Vorlagenklasse `numeric_limits` und zwei Enumerationen zu Gleitkommadarstellungen und zur Rundung.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <limits>  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Explizite Spezialisierungen der `numeric_limits`-Klasse beschreiben viele Eigenschaften der grundlegenden Typen, einschließlich der Zeichen-, Integer- und Gleitkommatypen sowie `bool`, die nicht von den Regeln der Programmiersprache C++ festgelegt werden, sondern von der Implementierung abhängig sind. In \<limits> beschriebene Eigenschaften umfassen Genauigkeit, Darstellungen minimaler und maximaler Größe, Rundung und Fehler des Signalisierungstyps.  
  
### <a name="enumerations"></a>Enumerationen  
  
|||  
|-|-|  
|[float_denorm_style](../standard-library/limits-enums.md#float_denorm_style)|Die Enumeration beschreibt die verschiedenen Methoden, die eine Implementierung für die Darstellung eines denormalisierten Gleitkommawerts auswählen kann – für Werte, die zu klein sind, um als normalisierte Werte dargestellt zu werden:|  
|[float_round_style](../standard-library/limits-enums.md#float_round_style)|Die Enumeration beschreibt die verschiedenen Methoden, die eine Implementierung für die Rundung eines Gleitkommawerts auf einen ganzzahligen Wert auswählen kann.|  
  
### <a name="classes"></a>Klassen  
  
|||  
|-|-|  
|[numeric_limits-Klasse](../standard-library/numeric-limits-class.md)|Die Vorlagenklasse beschreibt arithmetische Eigenschaften der integrierten numerischen Typen.|  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)



