---
title: '&lt;random&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords: std::generate_canonical
caps.latest.revision: "10"
manager: ghogen
ms.openlocfilehash: 0929e7c6749af19065f42f10ee6c15ab4d4a3e88
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ltrandomgt-functions"></a>&lt;random&gt;-Funktionen
  
##  <a name="generate_canonical"></a> generate_canonical  
 Gibt einen Gleitkommawert aus einer zufälligen Sequenz zurück.  
  
> [!NOTE]
>  Der ISO C++-Standard verlangt, dass diese Funktion Werte im Bereich [`0`, `1`) zurückgibt. Visual Studio ist mit dieser Vorgabe noch nicht kompatibel. Verwenden Sie, um das Problem zu umgehen, zum Generieren von Werten in diesem Bereich [uniform_real_distribution](../standard-library/uniform-real-distribution-class.md).  
  
```  
template <class RealType, size_t Bits, class Generator>  
RealType generate_canonical(Generator& Gen);
```  
  
### <a name="parameters"></a>Parameter  
 `RealType`  
 Der ganzzahlige Gleitkommatyp. Die möglichen Typen finden Sie unter [\<random>](../standard-library/random.md).  
  
 `Bits`  
 Der Zufallszahlengenerator.  
  
 `Gen`  
 Der Zufallszahlengenerator.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion ruft wiederholt `operator()` von `Gen` auf und verpackt die zurückgegebenen Werte in einem Gleitkommawert `x` des Typs `RealType`, bis die angegebene Anzahl von Mantissen-Bits in `x` erreicht ist. Die angegebene Anzahl ist die kleinere von `Bits` (die nicht Null sein darf) und die vollständige Anzahl von Mantissen-Bits in `RealType`. Beim ersten Aufruf werden die Bits mit dem geringsten Wert ausgegeben. Die Funktion gibt `x` zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [\<random>](../standard-library/random.md)

