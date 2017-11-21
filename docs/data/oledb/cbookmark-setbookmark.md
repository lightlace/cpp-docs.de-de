---
title: 'CBookmark:: SetBookmark | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CBookmark<0>::SetBookmark
- ATL.CBookmark<0>.SetBookmark
- CBookmark<0>.SetBookmark
- SetBookmark
- ATL::CBookmark::SetBookmark
- ATL::CBookmark<0>::SetBookmark
- CBookmark.SetBookmark
- ATL.CBookmark.SetBookmark
- CBookmark::SetBookmark
dev_langs: C++
helpviewer_keywords: SetBookmark method
ms.assetid: bcd26831-6045-4e69-96d6-abf8037fc18d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4c265eaf2103f895198d029c231bf29755ea2c17
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cbookmarksetbookmark"></a>CBookmark::SetBookmark
Kopiert die Lesezeichenwert verweist `pBuffer` auf die `CBookmark` gepuffert und legt die Größe des Puffers auf `nSize`.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT SetBookmark(  
   DBLENGTH nSize,  
   BYTE* pBuffer   
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 *nSize*  
 [in] Die Größe des Lesezeichenpuffers.  
  
 `pBuffer`  
 [in] Ein Zeiger auf das Bytearray, das den Lesezeichenwert enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion steht nur in **CBookmark\<0 >**.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CBookmark-Klasse](../../data/oledb/cbookmark-class.md)