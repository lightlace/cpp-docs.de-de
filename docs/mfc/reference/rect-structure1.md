---
title: RECT-Structure1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LPRECT
- RECT
dev_langs:
- C++
helpviewer_keywords:
- RECT structure [MFC]
- LPRECT structure [MFC]
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b61c794b8fa383eeea62459a5a83948ef2efe10
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372592"
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
  
## <a name="members"></a>Member  
 `left`  
 Gibt die X-Koordinate der oberen linken Ecke eines Rechtecks an.  
  
 `top`  
 Gibt die Y-Koordinate der oberen linken Ecke eines Rechtecks an.  
  
 `right`  
 Gibt die X-Koordinate der unteren rechten Ecke eines Rechtecks an.  
  
 `bottom`  
 Gibt die Y-Koordinate der unteren rechten Ecke eines Rechtecks an.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities#38](../../mfc/codesnippet/cpp/rect-structure1_1.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** windef.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRect-Klasse](../../atl-mfc-shared/reference/crect-class.md)
