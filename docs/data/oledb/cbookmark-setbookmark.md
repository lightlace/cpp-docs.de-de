---
title: 'CBookmark:: SetBookmark | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- SetBookmark method
ms.assetid: bcd26831-6045-4e69-96d6-abf8037fc18d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6d8f4402a6caf01f4d813e6ee8f9fd2d95512394
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093676"
---
# <a name="cbookmarksetbookmark"></a>CBookmark::SetBookmark
Kopiert die Lesezeichenwert verweist `pBuffer` auf die `CBookmark` gepuffert und legt die Größe des Puffers auf `nSize`.  
  
## <a name="syntax"></a>Syntax  
  
```
HRESULT SetBookmark(DBLENGTH nSize,  
  BYTE* pBuffer) throw();  
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