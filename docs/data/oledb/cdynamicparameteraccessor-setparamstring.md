---
title: 'CDynamicParameterAccessor:: Setparamstring | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDynamicParameterAccessor.SetParamString
- ATL::CDynamicParameterAccessor::SetParamString
- SetParamString
- CDynamicParameterAccessor::SetParamString
- CDynamicParameterAccessor.SetParamString
dev_langs: C++
helpviewer_keywords: SetParamString method
ms.assetid: 77a38d23-7e33-4e5a-bda6-c12c4c3fe2e4
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ff96f451bc60469df0469d6a002ec51d91743b89
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicparameteraccessorsetparamstring"></a>CDynamicParameterAccessor::SetParamString
Legt die Zeichenfolgendaten des angegebenen Parameters fest, der im Puffer gespeichert ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      bool SetParamString(   
   DBORDINAL nParam,   
   const CHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK    
) throw( );  
bool SetParamString(   
   DBORDINAL nParam,   
   const WCHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK    
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `nParam`  
 [in] Die Parameteranzahl (Offset von 1). Parameter 0 ist für Rückgabewerte reserviert. Die Parameteranzahl ist der Index des Parameters basierend auf der Reihenfolge der SQL-oder einen Aufruf einer gespeicherten Prozedur. Finden Sie unter [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) ein Beispiel.  
  
 `pString`  
 [in] Ein Zeiger auf das ANSI (**CHAR**) oder Unicode (**WCHAR**) Zeichenfolgendaten des angegebenen Parameters. Finden Sie unter `DBSTATUS` in "OleDb.h".  
  
 *status*  
 [in] Die `DBSTATUS` Status des angegebenen Parameters. Informationen zu `DBSTATUS` -Werte finden Sie in [Status](https://msdn.microsoft.com/en-us/library/ms722617.aspx) in der *OLE DB Programmer's Reference*, oder suchen Sie nach `DBSTATUS` in "OleDb.h".  
  
## <a name="remarks"></a>Hinweise  
 Gibt **"true"** bei Erfolg oder **"false"** bei einem Fehler.  
  
 `SetParamString`schlägt fehl, wenn Sie versuchen, eine Zeichenfolge festlegen, die größer ist als die maximale Größe für angegebene `pString`.  
  
 Verwendung `SetParamString` Abfragezeichenfolge-Parameterdaten zur im Puffer festgelegt. Verwendung [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) Zeichenfolgendaten-Parameter im Puffer festgelegt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicParameterAccessor-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)