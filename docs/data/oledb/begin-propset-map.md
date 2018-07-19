---
title: BEGIN_PROPSET_MAP | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- BEGIN_PROPSET_MAP
dev_langs:
- C++
helpviewer_keywords:
- BEGIN_PROPSET_MAP macro
ms.assetid: c3a30618-6025-4d49-8688-a171294d2e93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5b1596797672c0fff92531ff90f67b94bfd6101e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089463"
---
# <a name="beginpropsetmap"></a>BEGIN_PROPSET_MAP
Markiert der Anfang der Eigenschaft festlegen Zuordnungseinträge.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
BEGIN_PROPSET_MAP(Class)  
  
```  
  
#### <a name="parameters"></a>Parameter  
 *Klasse*  
 [in] Die Klasse, in denen diese Eigenschaft festgelegt, wird angegeben. Als Eigenschaftensatz kann in die folgenden OLE DB-Objekte angegeben werden:  
  
-   [Datenquellenobjekte](https://msdn.microsoft.com/en-us/library/ms721278.aspx)  
  
-   [Session-Objekte](https://msdn.microsoft.com/en-us/library/ms711572.aspx)  
  
-   [Befehle](https://msdn.microsoft.com/en-us/library/ms724608.aspx)  
  
## <a name="example"></a>Beispiel  
 Hier ist eine Beispiel-eigenschaftenzuordnungen festlegen:  
  
 [!code-cpp[NVC_OLEDB_Provider#3](../../data/oledb/codesnippet/cpp/begin-propset-map_1.h)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [Makros für OLE DB-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)