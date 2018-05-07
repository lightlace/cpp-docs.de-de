---
title: CMemoryException Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMemoryException
- AFX/CMemoryException
- AFX/CMemoryException::CMemoryException
dev_langs:
- C++
helpviewer_keywords:
- CMemoryException [MFC], CMemoryException
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 12971af6bed7c04c6f6f214f0b583a4f7e6eb7a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cmemoryexception-class"></a>CMemoryException-Klasse
Stellt eine Ausnahmebedingung dar, die durch ungenügenden Arbeitsspeicher ausgelöst wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMemoryException : public CSimpleException  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMemoryException::CMemoryException](#cmemoryexception)|Erstellt ein `CMemoryException`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Keine weiteren Qualifizierung ist erforderlich, oder unmöglich. Arbeitsspeicher-Ausnahmen werden ausgelöst, automatisch vom **neue**. Wenn Sie Ihre eigenen Arbeitsspeicher-Funktionen schreiben, verwenden `malloc`für Beispiel und dann für das Auslösen von Ausnahmen Arbeitsspeicher verantwortlich sind.  
  
 Weitere Informationen zu `CMemoryException`, finden Sie im Artikel [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CMemoryException`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="cmemoryexception"></a>  CMemoryException::CMemoryException  
 Erstellt ein `CMemoryException`-Objekt.  
  
```  
CMemoryException();  
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diesen Konstruktor nicht direkt, aber stattdessen rufen Sie die globale Funktion [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception). Diese globale Funktion kann in einer Out-of-Memory-Situation erfolgreich ausgeführt werden, da es das Ausnahmeobjekt im zuvor zugeordnete Arbeitsspeicher erstellt. Weitere Informationen zur ausnahmeverarbeitung finden Sie im Artikel [Ausnahmen](../exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [CException-Klasse](cexception-class.md)   
 [Hierarchiediagramm](../hierarchy-chart.md)



