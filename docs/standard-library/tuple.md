---
title: '&lt;tuple&gt; | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <tuple>
dev_langs:
- C++
helpviewer_keywords:
- tuple header
ms.assetid: e4ef5c2d-318b-44f6-8bce-fce4ecd796a3
caps.latest.revision: 20
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: b84a2094205e3db7935d5768a3f86ba765487685
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="lttuplegt"></a>&lt;tuple&gt;
Definiert eine Vorlage `tuple`, deren Instanzen Objekte verschiedener Typen enthalten.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <tuple>  
```  
  
### <a name="classes"></a>Klassen  
  
|||  
|-|-|  
|[tuple](../standard-library/tuple-class.md)|Umschließt eine Sequenz von Elementen mit fester Länge.|  
|[tuple_element-Klasse](../standard-library/tuple-element-class-tuple.md)|Umschließt den Typ eines `tuple`-Elements.|  
|[tuple_size-Klasse](../standard-library/tuple-size-class-tuple.md)|Umschließt die `tuple`-Elementanzahl.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[operator==](../standard-library/tuple-operators.md#op_eq_eq)|Vergleich von `tuple`-Objekten, gleich|  
|[operator!=](../standard-library/tuple-operators.md#op_neq)|Vergleich von `tuple`-Objekten, ungleich|  
|[operator<](../standard-library/tuple-operators.md#op_lt)|Vergleich von `tuple`-Objekten, kleiner als|  
|[operator<=](../standard-library/tuple-operators.md#op_lt_eq)|Vergleich von `tuple`-Objekten, kleiner als oder gleich|  
|[operator>](../standard-library/tuple-operators.md#op_gt)|Vergleich von `tuple`-Objekten, größer als|  
|[operator>=](../standard-library/tuple-operators.md#op_gt_eq)|Vergleich von `tuple`-Objekten, größer als oder gleich|  
  
### <a name="functions"></a>Funktionen  
  
|||  
|-|-|  
|[get](../standard-library/tuple-functions.md#get)|Ruft ein Element aus einem `tuple`-Objekt ab.|  
|[make_tuple](../standard-library/tuple-functions.md#make_tuple)|Erstellt eine `tuple` aus Elementwerten.|  
|[tie](../standard-library/tuple-functions.md#tie)|Erstellt eine `tuple` aus Elementverweisen.|  
  
## <a name="see-also"></a>Siehe auch  
 [\<array>](../standard-library/array.md)


