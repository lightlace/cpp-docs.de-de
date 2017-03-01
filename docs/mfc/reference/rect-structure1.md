---
title: RECT-Structure1 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LPRECT
- RECT
dev_langs:
- C++
helpviewer_keywords:
- RECT structure
- LPRECT structure
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
caps.latest.revision: 13
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
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: bc91b22f291f23ed396a054b0c929410718286a3
ms.lasthandoff: 02/24/2017

---
# <a name="rect-structure1"></a>RECT-Structure1
Die `RECT`-Struktur definiert die Koordinaten der oberen linken und der unteren rechten Ecke eines Rechtecks.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tagRECT {  
    LONG left;  
    LONG top;  
    LONG right;  
    LONG bottom;  
} RECT;  
```  
  
## <a name="members"></a>Mitglieder  
 `left`  
 Gibt die X-Koordinate der oberen linken Ecke eines Rechtecks an.  
  
 `top`  
 Gibt die Y-Koordinate der oberen linken Ecke eines Rechtecks an.  
  
 `right`  
 Gibt die X-Koordinate der unteren rechten Ecke eines Rechtecks an.  
  
 `bottom`  
 Gibt die Y-Koordinate der unteren rechten Ecke eines Rechtecks an.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities&#38;](../../mfc/codesnippet/cpp/rect-structure1_1.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** windef.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRect-Klasse](../../atl-mfc-shared/reference/crect-class.md)

