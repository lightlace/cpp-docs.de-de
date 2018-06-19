---
title: 'CBookmark:: CBookmark | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CBookmark<0>.CBookmark<0>
- CBookmark::CBookmark
- ATL.CBookmark.CBookmark
- CBookmark.CBookmark
- CBookmark
- ATL::CBookmark<0>::CBookmark<0>
- ATL.CBookmark<0>.CBookmark<0>
- CBookmark<0>::CBookmark<0>
- ATL::CBookmark::CBookmark
dev_langs:
- C++
helpviewer_keywords:
- CBookmark class, constructor
ms.assetid: 84f4ad2b-67d4-4ba3-8b2b-656a66fb6298
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f7663c34fc9eea5f4262fea6b347c1b7899ace85
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095234"
---
# <a name="cbookmarkcbookmark"></a>CBookmark::CBookmark
Der Konstruktor.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      CBookmark();   

CBookmark(DBLENGTH nSize);  
```  
  
#### <a name="parameters"></a>Parameter  
 `nSize`  
 [in] Die Größe des Lesezeichenpuffers in Bytes.  
  
## <a name="remarks"></a>Hinweise  
 Die erste Funktion legt die Puffer auf **NULL** und die Größe des Puffers auf 0. Die zweite Funktion legt die Größe des Puffers auf `nSize`, und der Puffer, in ein Bytearray `nSize` Bytes.  
  
> [!NOTE]
>  Diese Funktion steht nur in **CBookmark\<0 >**.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CBookmark-Klasse](../../data/oledb/cbookmark-class.md)