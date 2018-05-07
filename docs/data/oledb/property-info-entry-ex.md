---
title: PROPERTY_INFO_ENTRY_EX | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- PROPERTY_INFO_ENTRY_EX
dev_langs:
- C++
helpviewer_keywords:
- PROPERTY_INFO_ENTRY_EX macro
ms.assetid: af32dfcd-4c50-449d-af3b-48d21bd67a04
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 186c30584c5c5844614994700bf2a7958a73ce2d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="propertyinfoentryex"></a>PROPERTY_INFO_ENTRY_EX
Stellt eine bestimmte Eigenschaft in einem Eigenschaftensatz dar.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
PROPERTY_INFO_ENTRY_EX(dwPropID  
, vt, dwFlags, value, options )  
```  
  
#### <a name="parameters"></a>Parameter  
 *dwPropID*  
 [in] Ein [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) -Wert, der in Verbindung mit dem GUID-Eigenschaftensatz verwendet werden kann, um eine Eigenschaft zu identifizieren.  
  
 *vt*  
 [in] Die [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) dieses Eigenschaftseintrags.  
  
 `dwFlags`  
 [in] Ein [DBPROPFLAGS](https://msdn.microsoft.com/en-us/library/ms724342.aspx) -Wert, der diesen Eigenschaftseintrag beschreibt.  
  
 *Wert*  
 [in] Der Eigenschaftswert von Typ `DWORD`.  
  
 `options`  
 Entweder **DBPROPOPTIONS_REQUIRED** oder **DBPROPOPTIONS_SETIFCHEAP**. In der Regel muss ein Anbieter `options` nicht festlegen, da dies vom Consumer festgelegt wird.  
  
## <a name="remarks"></a>Hinweise  
 Mit diesem Makro können Sie den Wert der Eigenschaft des Typs `DWORD` sowie Optionen und Flags direkt angeben. Um lediglich einen in ATLDB.H definierten Standardwert für eine Eigenschaft festzulegen, verwenden Sie [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md). Um einen Wert Ihrer Wahl für eine Eigenschaft festzulegen, verwenden Sie [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md).  
  
## <a name="example"></a>Beispiel  
 Siehe [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [Makros für OLE DB-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)