---
title: AtlTraceErrorRecords | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.AtlTraceErrorRecords
- ATL::AtlTraceErrorRecords
- AtlTraceErrorRecords
dev_langs:
- C++
helpviewer_keywords:
- AtlTraceErrorRecords function
ms.assetid: b83970b3-dc2a-445c-9142-f52218719905
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 024a4331b71b3414aa7d83f27ecaca4e5d2f11de
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="atltraceerrorrecords"></a>AtlTraceErrorRecords
Sichert OLE DB-Fehlerdatensatz Informationen auf dem Sicherungsmedium aus, wenn ein Fehler zurückgegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      inline void AtlTraceErrorRecords(HRESULT hrErr = S_OK);  
```  
  
#### <a name="parameters"></a>Parameter  
 `hErr`  
 [in] Ein `HRESULT` von einer OLE DB-Consumervorlagen Memberfunktion zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `hErr` nicht `S_OK`, `AtlTraceErrorRecords` gibt Informationen von OLE DB-Fehlerdatensatz auf dem Sicherungsmedium (die **Debuggen** Registerkarte dem Fenster "Ausgabe" oder eine Datei). Die Error-Datensatzes-Informationen, die vom Anbieter abgerufen wird, enthält die Nummer der Zeile, Quelle, Beschreibung, Hilfedatei, Kontext und GUID für jeden Datensatz Eintrag der Fehler. `AtlTraceErrorRecords` gibt diese Informationen nur in Debug-Builds. In Releasebuilds kann es sich um einen leeren Stub, der Sie optimiert ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Funktionen für OLE DB-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [CDBErrorInfo-Klasse](../../data/oledb/cdberrorinfo-class.md)