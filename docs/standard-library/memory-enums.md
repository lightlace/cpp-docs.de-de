---
title: '&lt;memory&gt; enums | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 9c3440495d77b788658cffefc917d9960ca1f833
ms.lasthandoff: 02/24/2017

---
# <a name="ltmemorygt-enums"></a>&lt;memory&gt; enums
||  
|-|  
|[pointer_safety-Enumeration](#pointer_safety_enumeration)|  
  
##  <a name="a-namepointersafetyenumerationa--pointersafety-enumeration"></a><a name="pointer_safety_enumeration"></a> pointer_safety-Enumeration  
 Die Enumeration möglicher Werte, die von `get_pointer_safety` zurückgegeben werden.  
  
Klasse pointer_safety { relaxed, preferred, strict };  
  
### <a name="remarks"></a>Hinweise  
 Mit dem bereichsbezogenen `enum`-Element werden die Werte definiert, die von `get_pointer_safety``()` zurückgegeben werden können:  
  
 `relaxed` – nicht sicher abgeleitete Zeiger (offensichtlich die Zeiger von deklarierten oder zugeordneten Objekte) werden genauso behandelt, wie die sicher abgeleiteten.  
  
 `preferred` – wie zuvor, aber nicht sicher abgeleitete Zeiger sollten nicht dereferenziert werden.  
  
 `strict` – nicht sicher abgeleitete Zeiger werden möglicherweise anders behandelt als sicher berechnete Zeiger.  
  
## <a name="see-also"></a>Siehe auch  
 [\<memory>](../standard-library/memory.md)




