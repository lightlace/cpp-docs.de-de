---
title: CDBPropIDSet-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 67bfd11a46d8e0c852c1881ff8874b7fbd817164
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096950"
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