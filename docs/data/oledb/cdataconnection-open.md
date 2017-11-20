---
title: 'CDataConnection:: Open | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataConnection.Open
- ATL.CDataConnection.Open
- CDataConnection::Open
- ATL::CDataConnection::Open
dev_langs: C++
helpviewer_keywords: Open method
ms.assetid: 2c6f0c01-4954-43ba-973e-861ac8e82892
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 13a358cd52f56189f157e8ccbfb3ac26be1823fb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cdataconnectionopen"></a>CDataConnection::Open
Öffnet eine Verbindung mit einer Datenquelle mit einer Initialisierungszeichenfolge an.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT Open(   
   LPCOLESTR szInitString    
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 *szInitString*  
 [in] Die Initialisierungszeichenfolge für die Datenquelle.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDataConnection-Klasse](../../data/oledb/cdataconnection-class.md)