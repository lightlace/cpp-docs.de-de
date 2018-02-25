---
title: CDynamicStringAccessorW-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDynamicStringAccessorW
dev_langs:
- C++
helpviewer_keywords:
- CDynamicStringAccessorW class
ms.assetid: 9b7fd5cc-3a9b-4b57-b907-f1e35de2c98f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ca472dd2834a6992d8a4af6c0372e353aaf48a54
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicstringaccessorw-class"></a>CDynamicStringAccessorW-Klasse
Können Sie eine Datenquelle zugreifen, wenn Sie keine Kenntnisse des Datenbankschemas (zugrunde liegende Struktur) verfügen.  
  
## <a name="syntax"></a>Syntax

```cpp
typedef CDynamicStringAccessorT<WCHAR, DBTYPE_WSTR> CDynamicStringAccessorW;  
```  
  
## <a name="remarks"></a>Hinweise  
 Beide anfordern, dass der Anbieter alle Daten, die aus dem Datenspeicher als die Zeichenfolgedaten zugegriffen abzurufen, aber `CDynamicStringAccessor` Unicode-Zeichenfolgendaten anfordert.  
  
 `CDynamicStringAccessorW` erbt **GetString** und `SetString` aus `CDynamicStringAccessor`. Bei Verwendung dieser Methoden in einer `CDynamicStringAccessorW` Objekt ***BaseType*** ist **WCHAR**.  
  
## <a name="requirements"></a>Anforderungen  
 **Header**: atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB-Consumer-Vorlagenreferenz](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor-Klasse](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor-Klasse](../../data/oledb/cmanualaccessor-class.md)   
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessor-Klasse](../../data/oledb/cdynamicstringaccessor-class.md)