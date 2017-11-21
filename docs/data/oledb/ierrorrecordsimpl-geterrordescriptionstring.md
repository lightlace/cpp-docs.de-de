---
title: 'IErrorRecordsImpl:: Geterrordescriptionstring | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetErrorDescriptionString
- IErrorRecordsImpl.GetErrorDescriptionString
- IErrorRecordsImpl::GetErrorDescriptionString
dev_langs: C++
helpviewer_keywords: GetErrorDescriptionString method
ms.assetid: 8bc71c45-ca9f-4632-bb02-1aa9ed8086c4
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a2acdf2cf0ba658077ea9f57fe8087326b3f7b2f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ierrorrecordsimplgeterrordescriptionstring"></a>IErrorRecordsImpl::GetErrorDescriptionString
Ruft die Zeichenfolge zur fehlerbeschreibung aus Error-Datensatzes ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      LPOLESTR GetErrorDescriptionString(  
   ERRORINFO& rCurError   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `rCurError`  
 Ein `ERRORINFO` Datensatz in einer **IErrorInfo** Schnittstelle.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine Zeichenfolge, die den Fehler beschreibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IErrorRecordsImpl-Klasse](../../data/oledb/ierrorrecordsimpl-class.md)