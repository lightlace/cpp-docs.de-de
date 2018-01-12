---
title: BEGIN_PROPSET_MAP | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BEGIN_PROPSET_MAP
dev_langs: C++
helpviewer_keywords: BEGIN_PROPSET_MAP macro
ms.assetid: c3a30618-6025-4d49-8688-a171294d2e93
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 24fe8ed41888ab2b3d303a29cd9d004f26b6c6b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="beginpropsetmap"></a>BEGIN_PROPSET_MAP
Markiert der Anfang der Eigenschaft festlegen Zuordnungseinträge.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
BEGIN_PROPSET_MAP(  
Class   
)  
  
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