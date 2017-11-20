---
title: AsyncResultType-Enumeration | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncResultType
dev_langs: C++
helpviewer_keywords: AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 32cb9a76a9415fc051faf11ecd3268d461297450
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="asyncresulttype-enumeration"></a>AsyncResultType-Enumeration
Gibt den Typ des durch die Methode „GetResults()“ zurückgegebenen Ergebnisses zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
enum AsyncResultType;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`MultipleResults`|Ein Satz von mehreren Ergebnissen, die zwischen Start- und vor dem Aufruf von Close() progressiv dargestellt werden.|  
|`SingleResult`|Ein einzelnes Ergebnis, die angezeigt wird, nachdem das Abschlussereignis tritt auf.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)