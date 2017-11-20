---
title: 'CDataConnection:: Copy | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataConnection.Copy
- ATL.CDataConnection.Copy
- ATL::CDataConnection::Copy
- CDataConnection::Copy
dev_langs: C++
helpviewer_keywords: Copy method
ms.assetid: a3dbd70d-36be-49e0-a527-00e3910a7a56
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6e56547eec870265bcb2e5b77e19a237102c59ef
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cdataconnectioncopy"></a>CDataConnection::Copy
Erstellt eine Kopie einer vorhandenen Verbindung mit Daten.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      CDataConnection& Copy(   
   const CDataConnection & ds    
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `ds`  
 [in] Ein Verweis auf eine vorhandene Datenverbindung zu kopieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDataConnection-Klasse](../../data/oledb/cdataconnection-class.md)