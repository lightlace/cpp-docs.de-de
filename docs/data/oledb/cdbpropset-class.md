---
title: CDBPropSet-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBPropSet
- ATL.CDBPropSet
- ATL::CDBPropSet
dev_langs: C++
helpviewer_keywords: CDBPropSet class
ms.assetid: 54190149-c277-4679-b81a-ef484d4d1c00
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2b2523e37c3015bb49d123e99f39c1ea4bdb9045
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdbpropset-class"></a>CDBPropSet-Klasse
Erbt von der **DBPROPSET** strukturieren und fügt einen Konstruktor, Schlüsselfelder initialisiert, sowie die `AddProperty` -Zugriffsmethode.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDBPropSet : public tagDBPROPSET  
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[AddProperty](../../data/oledb/cdbpropset-addproperty.md)|Fügt eine Eigenschaft zum Eigenschaftensatz.|  
|[CDBPropSet](../../data/oledb/cdbpropset-cdbpropset.md)|Konstruktor.|  
|[SetGUID](../../data/oledb/cdbpropset-setguid.md)|Legt die **GuidPropertySet** Feld der **DBPROPSET** Struktur.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator =](../../data/oledb/cdbpropset-operator-equal.md)|Weist den Inhalt einer Eigenschaft zu einem anderen festgelegt.|  
  
## <a name="remarks"></a>Hinweise  
 OLE DB-Anbieter und Consumer verwenden **DBPROPSET** zum Übergeben von Arrays von Strukturen `DBPROP` Strukturen. Jede `DBPROP` Struktur stellt eine einzelne Eigenschaft, die festgelegt werden kann.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB-Consumer-Vorlagenreferenz](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CDBPropIDSet-Klasse](../../data/oledb/cdbpropidset-class.md)   
 [DBPROPSET-Struktur](https://msdn.microsoft.com/en-us/library/ms714367.aspx)   
 [DBPROP-Struktur](https://msdn.microsoft.com/en-us/library/ms717970.aspx)