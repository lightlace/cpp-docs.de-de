---
title: 'CBulkRowset:: MoveToBookmark | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CBulkRowset<TAccessor>::MoveToBookmark
- CBulkRowset.MoveToBookmark
- MoveToBookmark
- ATL.CBulkRowset.MoveToBookmark
- CBulkRowset::MoveToBookmark
- ATL::CBulkRowset<TAccessor>::MoveToBookmark
- ATL::CBulkRowset::MoveToBookmark
dev_langs: C++
helpviewer_keywords: MoveToBookmark method
ms.assetid: 76aab025-819e-4ecd-ae0a-d8d3fb2d2099
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1671a0b03b3dbc637d83fd1e0f5125bc4abb1f1d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cbulkrowsetmovetobookmark"></a>CBulkRowset::MoveToBookmark
Dadurch wird die Zeile markiert ein Lesezeichen bzw. die Zeile mit einem angegebenen Offset (`lSkip`) von diesem Lesezeichen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT MoveToBookmark(  
   const CBookmarkBase& bookmark,  
   DBCOUNTITEM lSkip = 0   
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `bookmark`  
 [in] Ein Lesezeichen, markieren den Speicherort, aus dem Daten abgerufen werden sollen.  
  
 `lSkip`  
 [in] Die Anzahl Anzahl von Zeilen aus das Lesezeichen Zielzeile. Wenn `lSkip` NULL ist, wird die erste Zeile abgerufen wird, dem Lesezeichen versehenen Zeile. Wenn `lSkip` 1, ist die erste Zeile abgerufen wird die Zeile nach dem Lesezeichen versehenen Zeile. Wenn `lSkip` ist-1 und die erste Zeile abgerufen wird, die Zeile vor dem Lesezeichen versehenen Zeile.  
  
## <a name="return-value"></a>Rückgabewert  
 Finden Sie unter [IRowset:: GetData](https://msdn.microsoft.com/en-us/library/ms716988.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CBulkRowset-Klasse](../../data/oledb/cbulkrowset-class.md)