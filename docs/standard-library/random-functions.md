---
title: '&lt;random&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
caps.latest.revision: 10
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 3aebef535acb59046fab53d49051df16bd362c3c
ms.lasthandoff: 02/24/2017

---
# <a name="ltrandomgt-functions"></a>&lt;random&gt;-Funktionen
  
##  <a name="a-namegeneratecanonicala--generatecanonical"></a><a name="generate_canonical"></a> generate_canonical  
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


