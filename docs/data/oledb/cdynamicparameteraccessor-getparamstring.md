---
title: 'CDynamicParameterAccessor:: Getparamstring | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicParameterAccessor.GetParamString
- GetParamString
- CDynamicParameterAccessor::GetParamString
- ATL.CDynamicParameterAccessor.GetParamString
- ATL::CDynamicParameterAccessor::GetParamString
dev_langs: C++
helpviewer_keywords: GetParamString method
ms.assetid: 078c2b1c-7072-47c1-a203-f47e75363f91
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ed04d3258ad5f4d5ed68a32b32923432577453ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicparameteraccessorgetparamstring"></a>CDynamicParameterAccessor::GetParamString
Ruft die Zeichenfolgendaten Status des angegebenen Parameters ab, der im Puffer gespeichert ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      bool GetParamString(  
   DBORDINAL nParam,  
   CSimpleStringA& strOutput  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   CSimpleStringW& strOutput  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   CHAR* pBuffer,  
   size_t* pMaxLen  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   WCHAR* pBuffer,  
   size_t* pMaxLen  
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `nParam`  
 [in] Die Parameteranzahl (Offset von 1). Parameter 0 ist für Rückgabewerte reserviert. Die Parameteranzahl ist der Index des Parameters basierend auf der Reihenfolge der SQL-oder einen Aufruf einer gespeicherten Prozedur. Finden Sie unter [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) ein Beispiel.  
  
 `strOutput`  
 [out] Die ANSI (**CSimpleStringA**) oder Unicode (**CSimpleStringW**) Zeichenfolgendaten des angegebenen Parameters. Übergeben Sie einen Parameter vom Typ `CString`, beispielsweise:  
  
 [!code-cpp[NVC_OLEDB_Consumer#9](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-getparamstring_1.cpp)]  
  
 `pBuffer`  
 [out] Ein Zeiger auf das ANSI (**CHAR**) oder Unicode (**WCHAR**) Zeichenfolgendaten des angegebenen Parameters.  
  
 `pMaxLen`  
 [out] Ein Zeiger auf die Größe des Puffers verweist `pBuffer` (in Zeichen, einschließlich das abschließende NULLZEICHEN).  
  
## <a name="remarks"></a>Hinweise  
 Gibt **"true"** bei Erfolg oder **"false"** bei einem Fehler.  
  
 Wenn `pBuffer` NULL ist, wird diese Methode die erforderliche Puffergröße festgelegt, in den Speicher verweist `pMaxLen` und zurückgeben **"true"** ohne die Daten zu kopieren.  
  
 Diese Methode schlägt fehl, wenn der Puffer `pBuffer` ist nicht groß genug für die gesamte Zeichenfolge enthalten.  
  
 Verwendung `GetParamString` abzurufenden Zeichenfolge Parameterdaten aus dem Puffer. Verwendung [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) abzurufenden Objektressourcen Parameterdaten aus dem Puffer.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicParameterAccessor-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)