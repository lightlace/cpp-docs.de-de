---
title: _com_ptr_t::Detach | Microsoft-Dokumentation
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
ms.openlocfilehash: cf38e433f7042707b502a4cba2088db9412adb29
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405833"
---
# <a name="comptrtdetach"></a>_com_ptr_t::Detach
**Microsoft-spezifisch**  
  
 Extrahiert den gekapselten Schnittstellenzeiger und gibt ihn zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
Interface* Detach( ) throw( );  
```  
  
## <a name="remarks"></a>Hinweise  
 Extrahiert und gibt den gekapselten Schnittstellenzeiger zurück, und löscht dann den Speicher des gekapselten Zeigers auf NULL. Dadurch wird der Schnittstellenzeiger aus der Kapselung entfernt. Es liegt bei Ihnen Aufrufen `Release` für den zurückgegebenen Schnittstellenzeiger auf.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)