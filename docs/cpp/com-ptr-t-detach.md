---
title: _com_ptr_t::Detach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6fbe8fd203c3fda75e83aee623254676dacaf1da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="comptrtdetach"></a>_com_ptr_t::Detach
**Microsoft-spezifisch**  
  
 Extrahiert den gekapselten Schnittstellenzeiger und gibt ihn zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
Interface* Detach( ) throw( );  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Gibt den gekapselten Schnittstellenzeiger zurück, extrahiert und löscht dann den Speicher des gekapselten Zeigers auf **NULL**. Dadurch wird der Schnittstellenzeiger aus der Kapselung entfernt. Es liegt bei Ihnen Aufrufen **Version** für den zurückgegebenen Schnittstellenzeiger auf.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)