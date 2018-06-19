---
title: CDynamicStringAccessorW-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicStringAccessorW
dev_langs:
- C++
helpviewer_keywords:
- CDynamicStringAccessorW class
ms.assetid: 9b7fd5cc-3a9b-4b57-b907-f1e35de2c98f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 767add2be1f9f5266a6a66ce4455dec172f63e45
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095741"
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