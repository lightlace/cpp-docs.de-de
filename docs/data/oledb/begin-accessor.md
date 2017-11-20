---
title: BEGIN_ACCESSOR | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BEGIN_ACCESSOR
dev_langs: C++
helpviewer_keywords:
- BEGIN_ACCESSOR macro, syntax
- BEGIN_ACCESSOR macro
ms.assetid: 59d0ff3e-7cfd-4ce8-9a1c-d664c0892a52
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 74d8d2197553f9fd2b1f5452236b343424d29148
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="beginaccessor"></a>BEGIN_ACCESSOR
Markiert den Beginn eines Eintrags Accessor.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
BEGIN_ACCESSOR(  
num  
,   
bAuto  
 )  
  
```  
  
#### <a name="parameters"></a>Parameter  
 *num*  
 [in] Die Anzahl der 0 (null)-Offset für den Accessor in dieser accessorzuordnung.  
  
 *bAuto*  
 [in] Gibt an, ob diese Zugriffsmethode einen Accessor für die automatische oder manuelle-Accessor. Wenn **"true"**, der Accessor ist Auto; Wenn **"false"**, ist "manuell die Zugriffsmethode". Ein Autoaccessor bedeutet, dass es sich bei abgerufene Daten für die Sie verschieben.  
  
## <a name="remarks"></a>Hinweise  
 Bei mehreren Accessoren für ein Rowset, müssen Sie angeben `BEGIN_ACCESSOR_MAP` und Verwenden der `BEGIN_ACCESSOR` -Makro für jede einzelne Zugriffsmethode. Das `BEGIN_ACCESSOR` -Makro wird mit dem `END_ACCESSOR` -Makro abgeschlossen. Die `BEGIN_ACCESSOR_MAP` Makro erfolgt mit der `END_ACCESSOR_MAP` Makro.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Funktionen für OLE DB-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [END_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)