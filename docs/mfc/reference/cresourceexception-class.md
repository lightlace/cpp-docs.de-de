---
title: CResourceException Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CResourceException
- AFXWIN/CResourceException
- AFXWIN/CResourceException::CResourceException
dev_langs:
- C++
helpviewer_keywords:
- CResourceException [MFC], CResourceException
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6fdbfb29b00eaac40b4da2b78753df6a0596764f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371529"
---
# <a name="cresourceexception-class"></a>CResourceException-Klasse
Wird generiert, wenn Windows eine angeforderte Ressource nicht finden oder zuordnen kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CResourceException : public CSimpleException  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CResourceException::CResourceException](#cresourceexception)|Erstellt ein `CResourceException`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Keine weiteren Qualifizierung ist erforderlich, oder unmöglich.  
  
 Weitere Informationen zur Verwendung von `CResourceException`, finden Sie im Artikel [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CResourceException`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cresourceexception"></a>  CResourceException::CResourceException  
 Erstellt ein `CResourceException`-Objekt.  
  
```  
CResourceException();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diesen Konstruktor nicht direkt, aber stattdessen rufen Sie die globale Funktion [AfxThrowResourceException](exception-processing.md#afxthrowresourceexception). Weitere Informationen zu Ausnahmen finden Sie im Artikel [Ausnahmebehandlung in MFC](../exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [CException-Klasse](cexception-class.md)   
 [Hierarchiediagramm](../hierarchy-chart.md)


