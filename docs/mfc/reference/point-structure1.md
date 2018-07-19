---
title: POINT-Struktur 1 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- POINT
- LPPOINT
dev_langs:
- C++
helpviewer_keywords:
- LPPOINT structure [MFC]
- POINT structure [MFC]
ms.assetid: 965736d8-4e53-41b6-9b8b-6961992dd21f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de172814db04ab8d057f84a29ce505896f89adc9
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335333"
---
# <a name="point-structure1"></a>POINT-Struktur 1
Die `POINT` Struktur definiert, das "X"*-* und y-Koordinaten eines Punkts.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tagPOINT {  
    LONG x;  
    LONG y;  
} POINT;  
```  
  
#### <a name="parameters"></a>Parameter  
 *w*  
 Gibt die x-Koordinate eines Punkts an.  
  
 *y*  
 Gibt die y-Koordinate eines Punkts an.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities#37](../../mfc/codesnippet/cpp/point-structure1_1.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** windef.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPoint-Klasse](../../atl-mfc-shared/reference/cpoint-class.md)
