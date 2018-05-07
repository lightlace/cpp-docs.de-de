---
title: 'CDataSource:: OpenFromInitializationString | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataSource.OpenFromInitializationString
- OpenFromInitializationString
- CDataSource::OpenFromInitializationString
- ATL::CDataSource::OpenFromInitializationString
- ATL.CDataSource.OpenFromInitializationString
dev_langs:
- C++
helpviewer_keywords:
- OpenFromInitializationString method
ms.assetid: 5ef1f1fd-92a9-4e1c-ad80-d3601b094b8c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dac964f7c6c863f85769a164fab8c418e1c45430
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cdatasourceopenfrominitializationstring"></a>CDataSource::OpenFromInitializationString
Öffnet eine Datenquelle, die vom Benutzer bereitgestellte Initialisierungszeichenfolge angegeben.  
  
## <a name="syntax"></a>Syntax  
  
```
HRESULT OpenFromInitializationString(LPCOLESTR szInitializationString,   
   bool fPromptForInfo= false) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 *szInitializationString*  
 [in] Die Initialisierungszeichenfolge.  
  
 *fPromptForInfo*  
 [in] Wenn dieses Argument, um festgelegt wird **"true"**, klicken Sie dann `OpenFromInitializationString` wird festgelegt, die **DBPROP_INIT_PROMPT** Eigenschaft, um **DBPROMPT_COMPLETEREQUIRED**, der angibt, dass der Benutzer sein dazu aufgefordert werden, nur, wenn Sie weitere Informationen erforderlich ist. Dies eignet sich für Situationen, in dem die Initialisierungszeichenfolge eine Datenbank an, die ein Kennwort erforderlich ist, aber die Zeichenfolge enthält nicht das Kennwort. Der Benutzer wird aufgefordert, ein Kennwort (oder eine beliebige andere Informationen zu fehlenden) beim Versuch, mit der Datenbank herstellen.  
  
 Der Standardwert ist **"false"**, der angibt, dass der Benutzer niemals aufgefordert werden (legt **DBPROP_INIT_PROMPT** auf **DBPROMPT_NOPROMPT**).  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode öffnet ein Datenquellenobjekt mit den Dienstkomponenten im oledb32.dll; Diese DLL enthält die Implementierung von Dienstkomponentenfunktionen wie z. B. Ressourcenpooling, automatische Transaktionseintragung usw.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDataSource-Klasse](../../data/oledb/cdatasource-class.md)