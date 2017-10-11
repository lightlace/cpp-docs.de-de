---
title: _AtlCreateWndData Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::_AtlCreateWndData
- ATL._AtlCreateWndData
- _AtlCreateWndData
dev_langs:
- C++
helpviewer_keywords:
- _AtlCreateWndData structure
- AtlCreateWndData structure
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: a5b0811e88188bb29ef3153f739804cbdac66083
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="atlcreatewnddata-structure"></a>_AtlCreateWndData-Struktur
Diese Struktur enthält die Klasse Instanzdaten im Windowing Code in ATL  
  
## <a name="syntax"></a>Syntax  
  
```
    struct _AtlCreateWndData{
    void* m_pThis;
    DWORD m_dwThreadID;
    _AtlCreateWndData* m_pNext;
};
```  
  
## <a name="members"></a>Member  
 **m_pThis**  
 Die **dies** Zeiger verwendet, um den Zugriff auf die Klasseninstanz in Fensterprozeduren abzurufen.  
  
 `m_dwThreadID`  
 Die Thread-ID der aktuellen Klasseninstanz.  
  
 **m_pNext**  
 Zeiger auf die nächste `_AtlCreateWndData` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen](../../atl/reference/atl-structures.md)






