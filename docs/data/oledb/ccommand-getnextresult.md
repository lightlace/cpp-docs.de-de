---
title: 'CCommand:: GetNextResult | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CCommand::GetNextResult
- CCommand::GetNextResult
- GetNextResult
- CCommand.GetNextResult
- ATL.CCommand.GetNextResult
dev_langs: C++
helpviewer_keywords: GetNextResult method
ms.assetid: 63df9b55-9490-45c4-934a-879c5c2725d8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a0b4c03d7aa31949752e4362380d1705d7db6e9c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ccommandgetnextresult"></a>CCommand::GetNextResult
Ruft das nächste Resultset, wenn ein solcher verfügbar ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT GetNextResult(  
   DBROWCOUNT* pulRowsAffected,  
   bool bBind = true   
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 *pulRowsAffected*  
 [in/Out] Ein Zeiger auf Speicher, in dem die Anzahl der von einem Befehl betroffenen Zeilen zurückgegeben wird.  
  
 `bBind`  
 [in] Gibt an, ob den Befehl automatisch zu binden, nach der gerade ausgeführt wird. Die Standardeinstellung ist **"true"**, die bewirkt, dass der Befehl automatisch gebunden werden. Festlegen von `bBind` auf **"false"** wird verhindert, dass die automatische Bindung des Befehls, sodass manuell gebunden werden kann. (Manuelle Bindung ist von besonderem Interesse für OLAP-Benutzer).  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn zuvor ein Resultset abgerufen wurde, wird diese Funktion gibt das vorherige Resultset frei und hebt die Bindung der Spalten. Wenn `bBind` ist **"true"**, er die neuen Spalten gebunden werden.  
  
 Nur, wenn Sie mehrere Ergebnisse durch Festlegen von angegeben haben, rufen Sie diese Funktion sollte die `CCommand` Vorlagenparameter *TMultiple*=`CMultipleResults`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CCommand-Klasse](../../data/oledb/ccommand-class.md)