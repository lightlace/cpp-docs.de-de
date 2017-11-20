---
title: 'ICommandImpl:: M_bcancel | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICommandImpl::m_bCancel
- ICommandImpl.m_bCancel
- m_bCancel
- ATL::ICommandImpl::m_bCancel
- ATL.ICommandImpl.m_bCancel
dev_langs: C++
helpviewer_keywords: m_bCancel
ms.assetid: f3b6fb60-4de4-4d81-a5d2-4052c41be0de
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e19b81818d564b3b6e3f7a1623482ef6458defd5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="icommandimplmbcancel"></a>ICommandImpl::m_bCancel
Gibt an, ob der Befehl abgebrochen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
unsigned m_bCancel:1;  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können diese Variable in Abrufen der **Execute** Methode Ihre Befehlsklasse und "Abbrechen", nach Bedarf.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [ICommandImpl-Klasse](../../data/oledb/icommandimpl-class.md)   
 [ICommandImpl::m_bCancelWhenExecuting](../../data/oledb/icommandimpl-m-bcancelwhenexecuting.md)