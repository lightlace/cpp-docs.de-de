---
title: CNotSupportedException Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CNotSupportedException
- AFX/CNotSupportedException
- AFX/CNotSupportedException::CNotSupportedException
dev_langs:
- C++
helpviewer_keywords:
- CNotSupportedException [MFC], CNotSupportedException
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4013b26e3c07d6ec2a729bf9868db48923e35f86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cnotsupportedexception-class"></a>CNotSupportedException-Klasse
Stellt eine Ausnahme dar, die das Ergebnis der Anforderung einer nicht unterstützten Funktion ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CNotSupportedException : public CSimpleException  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CNotSupportedException::CNotSupportedException](#cnotsupportedexception)|Erstellt ein `CNotSupportedException`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Keine weiteren Qualifizierung ist erforderlich, oder unmöglich.  
  
 Weitere Informationen zur Verwendung von `CNotSupportedException`, finden Sie im Artikel [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CNotSupportedException`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="cnotsupportedexception"></a>CNotSupportedException::CNotSupportedException  
 Erstellt ein `CNotSupportedException`-Objekt.  
  
```  
CNotSupportedException();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diesen Konstruktor nicht direkt, aber stattdessen rufen Sie die globale Funktion [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception). Weitere Informationen zur ausnahmeverarbeitung finden Sie im Artikel [Ausnahmebehandlung in MFC](../exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [CException-Klasse](cexception-class.md)   
 [Hierarchiediagramm](../hierarchy-chart.md)


