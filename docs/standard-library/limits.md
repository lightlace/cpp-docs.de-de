---
title: '&lt;limits&gt; | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.<limits>
- std::<limits>
- limits/std::<limits>
- <limits>
dev_langs:
- C++
helpviewer_keywords:
- limits header
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
caps.latest.revision: 18
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 86978cd4549f0672dac7cad0e4713380ea189c27
ms.openlocfilehash: bd4d0e1dbc7b350cd0683fdd5e6ad3fc1dc1f781
ms.contentlocale: de-de
ms.lasthandoff: 04/18/2017

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
 [Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)




