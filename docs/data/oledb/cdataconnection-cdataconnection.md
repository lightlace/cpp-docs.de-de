---
title: 'CDataConnection:: CDataConnection | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataConnection.CDataConnection
- ATL.CDataConnection.CDataConnection
- CDataConnection::CDataConnection
- ATL::CDataConnection::CDataConnection
dev_langs: C++
helpviewer_keywords: CDataConnection class, constructor
ms.assetid: ac25c9a0-44d3-4083-b13f-76c07772e12d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e92019f3f49257e297bddb2f717cf416da62a3bc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cdataconnectioncdataconnection"></a>CDataConnection::CDataConnection
Instanziiert und initialisiert ein `CDataConnection` Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      CDataConnection();   
CDataConnection(  
   const CDataConnection &ds  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ds`  
 [in] Ein Verweis auf eine vorhandene Datenverbindung.  
  
## <a name="remarks"></a>Hinweise  
 Die erste Außerkraftsetzung erstellt ein neues `CDataConnection` Objekt mit den Standardeinstellungen.  
  
 Die zweite Außerkraftsetzung erstellt ein neues `CDataConnection` Objekt mit Einstellungen entspricht dem Datenverbindungsobjekt, die Sie angeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDataConnection-Klasse](../../data/oledb/cdataconnection-class.md)