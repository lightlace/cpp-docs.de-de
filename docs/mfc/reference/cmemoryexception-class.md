---
title: CMemoryException Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMemoryException
- AFX/CMemoryException
- AFX/CMemoryException::CMemoryException
dev_langs:
- C++
helpviewer_keywords:
- CMemoryException class
- memory exceptions
- exceptions, memory type
- C++ exception handling, memory
- memory, exception handling
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
caps.latest.revision: 20
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
ms.openlocfilehash: 87be1b16d546791d24bbffa62207ec9ccb350139
ms.lasthandoff: 02/24/2017

---
# <a name="cmemoryexception-class"></a>CMemoryException-Klasse
Stellt eine Ausnahmebedingung dar, die durch ungenügenden Arbeitsspeicher ausgelöst wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMemoryException : public CSimpleException  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMemoryException::CMemoryException](#cmemoryexception)|Erstellt ein `CMemoryException`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Keine weiteren Qualifizierung ist mehr erforderlich oder möglich. Arbeitsspeicher-Ausnahmen ausgelöst werden, automatisch vom **neue**. Wenn Sie Ihre eigenen Arbeitsspeicher-Funktionen schreiben, `malloc`für Beispiel, können Sie für das Auslösen von Ausnahmen Speicher verantwortlich sind.  
  
 Weitere Informationen zu `CMemoryException`, finden Sie im Artikel [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CMemoryException`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="cmemoryexception"></a>CMemoryException::CMemoryException  
 Erstellt ein `CMemoryException`-Objekt.  
  
```  
CMemoryException();  
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diesen Konstruktor nicht direkt, aber stattdessen rufen Sie die globale Funktion [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception). Diese globale Funktion kann in einer Out-of-Memory-Situation erfolgreich ausgeführt werden, da er das Ausnahmeobjekt in zuvor reservierten Speicher erstellt. Weitere Informationen zur ausnahmeverarbeitung finden Sie im Artikel [Ausnahmen](../exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [CException-Klasse](cexception-class.md)   
 [Hierarchiediagramm](../hierarchy-chart.md)




