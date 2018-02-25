---
title: CManualAccessor-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CManualAccessor
- ATL.CManualAccessor
- CManualAccessor
dev_langs:
- C++
helpviewer_keywords:
- CManualAccessor class
ms.assetid: a0088074-7135-465c-b228-69097a50b8cc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ecb9f31c862f62ddc2422f201aa824a959e961a0
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cmanualaccessor-class"></a>CManualAccessor-Klasse
Stellt einen Accessor für die erweiterte Verwendung vorgesehen.  
  
## <a name="syntax"></a>Syntax

```cpp
class CManualAccessor : public CAccessorBase  
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md)|Fügt einen Eintrag für die Bindung den Ausgabespalten.|  
|[AddParameterEntry](../../data/oledb/cmanualaccessor-addparameterentry.md)|Der Parameteraccessor wird ein Parametereintrag eines hinzugefügt.|  
|[CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md)|Belegt Speicher für die Spalte Strukturen binden, und die spaltendatenmember initialisiert.|  
|[CreateParameterAccessor](../../data/oledb/cmanualaccessor-createparameteraccessor.md)|Belegt Speicher für den Parameter Strukturen binden, und die Parameterdatenmember initialisiert.|  
  
## <a name="remarks"></a>Hinweise  
 Mithilfe von `CManualAccessor`, geben Sie den Parameter und Ausgabeinstanz spaltenbindung von Laufzeitfunktion aufrufen zu können.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [DBViewer](../../visual-cpp-samples.md)   
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB-Consumer-Vorlagenreferenz](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor-Klasse](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicParameterAccessor-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)