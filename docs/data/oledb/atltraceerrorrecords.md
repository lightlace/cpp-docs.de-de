---
title: AtlTraceErrorRecords | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: afea3c3ef1f169e5f1cb5fc675c74b54da1be0d8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093346"
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