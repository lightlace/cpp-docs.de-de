---
title: Klasse CInvalidArgException | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInvalidArgException
dev_langs:
- C++
helpviewer_keywords:
- CInvalidArgException class
ms.assetid: e43d7c67-1157-47f8-817a-804083e8186e
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 4091c0e8a35320482eba193c89c90982c7e4fca9
ms.lasthandoff: 02/24/2017

---
# <a name="cinvalidargexception-class"></a>CInvalidArgException-Klasse
Diese Klasse stellt eine Ausnahmebedingung für ein ungültiges Argument dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CInvalidArgException : public CSimpleException  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInvalidArgException::CInvalidArgException](#cinvalidargexception)|Der Konstruktor.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `CInvalidArgException` -Objekt stellt eine Ausnahmebedingung Ungültiges Argument dar.  
  
 Weitere Informationen über Ausnahmebehandlung, finden Sie unter der [CException-Klasse](../../mfc/reference/cexception-class.md) Thema und [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CInvalidArgException`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="a-namecinvalidargexceptiona--cinvalidargexceptioncinvalidargexception"></a><a name="cinvalidargexception"></a>CInvalidArgException::CInvalidArgException  
 Der Konstruktor.  
  
```  
CInvalidArgException();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diesen Konstruktor nicht direkt. Rufen Sie die globale Funktion **AfxThrowInvalidArgException**.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CSimpleException-Klasse](../../mfc/reference/csimpleexception-class.md)

