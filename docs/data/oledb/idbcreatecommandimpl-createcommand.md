---
title: 'Idbcreatecommandimpl:: CreateCommand | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBCreateCommandImpl.CreateCommand
- CreateCommand
- IDBCreateCommandImpl::CreateCommand
dev_langs:
- C++
helpviewer_keywords:
- CreateCommand method
ms.assetid: 50ffbf8b-2c07-4bcb-96c5-ffce4519c7f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 709f734ad0349ea7908466958e282a8ca2a5c2db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101613"
---
# <a name="idbcreatecommandimplcreatecommand"></a>IDBCreateCommandImpl::CreateCommand
Erstellt einen neuen Befehl, und gibt die angeforderte Schnittstelle zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(CreateCommand)(IUnknown * pUnkOuter,   
   REFIID riid,   
   IUnknown ** ppvCommand);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IDBCreateCommand:: CreateCommand](https://msdn.microsoft.com/en-us/library/ms709772.aspx) in der *OLE DB Programmer's Reference*.  
  
 Einige Parameter entsprechen den *OLE DB Programmer's Reference* Parameter unterschiedliche Namen verwendet, die in beschriebenen **IDBCreateCommand:: CreateCommand**:  
  
|OLE DB-Vorlagenparameter|*OLE DB Programmer's Reference* Parameter|  
|--------------------------------|------------------------------------------------|  
|*ppvCommand*|*ppCommand*|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IDBCreateCommandImpl-Klasse](../../data/oledb/idbcreatecommandimpl-class.md)