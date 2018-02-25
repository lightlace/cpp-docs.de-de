---
title: CDBPropIDSet-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDBPropIDSet
- ATL.CDBPropIDSet
- ATL::CDBPropIDSet
dev_langs:
- C++
helpviewer_keywords:
- CDBPropIDSet class
ms.assetid: 52bb806c-9581-494d-9af7-50d8a4834805
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ee03feb715ebf96bd4de1af5374a2029f52bbf86
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cdbpropidset-class"></a>CDBPropIDSet-Klasse
Erbt von der **DBPROPIDSET** strukturieren und fügt einen Konstruktor, Schlüsselfelder initialisiert, sowie die [AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md) -Zugriffsmethode.  
  
## <a name="syntax"></a>Syntax

```cpp
class CDBPropIDSet : public tagDBPROPIDSET  
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md)|Fügt eine Eigenschaft-ID-Eigenschaftensatz.|  
|[CDBPropIDSet](../../data/oledb/cdbpropidset-cdbpropidset.md)|Konstruktor.|  
|[SetGUID](../../data/oledb/cdbpropidset-setguid.md)|Legt fest, die die GUID der Eigenschafts-ID.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[operator =](../../data/oledb/cdbpropidset-operator-equal.md)|Weist den Inhalt einer Eigenschafts-ID auf eine andere festgelegt.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden von OLE DB-Consumer **DBPROPIDSET** Strukturen, die ein Array von Eigenschaften-IDs zu übergeben, für die der Consumer die Eigenschaftsinformationen abrufen möchte. Die Eigenschaften in einer einzelnen identifiziert [DBPROPIDSET](https://msdn.microsoft.com/en-us/library/ms717981.aspx) Struktur zu einem Eigenschaftensatz gehören.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)