---
title: CDynamicStringAccessorA-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicStringAccessorA
dev_langs:
- C++
helpviewer_keywords:
- CDynamicStringAccessorA class
ms.assetid: ed0d9821-a655-41f1-a902-43c3042ac49c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d6d05ac97846f55cf65d4010179b28d2b543ef66
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096482"
---
# <a name="cdynamicstringaccessora-class"></a>CDynamicStringAccessorA-Klasse
Können Sie eine Datenquelle zugreifen, wenn Sie keine Kenntnisse des Datenbankschemas (zugrunde liegende Struktur) verfügen.  
  
## <a name="syntax"></a>Syntax

```cpp
typedef CDynamicStringAccessorT<CHAR, DBTYPE_STR> CDynamicStringAccessorA;  
```  
  
## <a name="remarks"></a>Hinweise  
 Beide anfordern, dass der Anbieter alle Daten, die aus dem Datenspeicher als die Zeichenfolgedaten zugegriffen abzurufen, aber `CDynamicStringAccessor` Anforderungen ANSI-Zeichenfolgendaten.  
  
 `CDynamicStringAccessorA` erbt **GetString** und `SetString` aus `CDynamicStringAccessor`. Bei Verwendung dieser Methoden in einer `CDynamicStringAccessorA` Objekt ***BaseType*** ist **CHAR**.  
  
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