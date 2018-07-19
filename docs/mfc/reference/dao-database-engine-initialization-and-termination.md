---
title: DAO-Datenbank-Engine Initialisierungs- und Terminierungscode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.data
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f28c0c166bcbf13181161d6afce484fe4a45b80
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369901"
---
# <a name="dao-database-engine-initialization-and-termination"></a>Initialisieren und Beenden des DAO-Datenbankmoduls
Verwendung von MFC-DAO-Objekten, muss zunächst die DAO-Datenbankmoduls werden initialisiert, und klicken Sie dann beendet, bevor Ihre Anwendung oder DLL beendet. Zwei Funktionen `AfxDaoInit` und `AfxDaoTerm`, diese Aufgaben ausführen.  
  
### <a name="dao-database-engine-initialization-and-termination"></a>Initialisieren und Beenden des DAO-Datenbankmoduls  
  
|||  
|-|-|  
|[AfxDaoInit](#afxdaoinit)|Initialisiert die DAO-Datenbankmoduls.|  
|[AfxDaoTerm](#afxdaoterm)|Beendet die DAO-Datenbankmoduls.|  
  
##  <a name="afxdaoinit"></a>  AfxDaoInit  
 Diese Funktion initialisiert den DAO-Datenbankmoduls.  
  
```  
 
void AfxDaoInit();

throw(CDaoException*);  
```  
  
### <a name="remarks"></a>Hinweise  
 In den meisten Fällen müssen Sie nicht aufrufen `AfxDaoInit` da die Anwendung automatisch sie aufruft, wenn er benötigt wird.  
  
 Weitere Informationen und ein Beispiel eines Aufrufs `AfxDaoInit`, finden Sie unter [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  
  
##  <a name="afxdaoterm"></a>  AfxDaoTerm  
 Diese Funktion beendet die DAO-Datenbankmoduls.  
  
```  
 
void AfxDaoTerm();  
```  
  
### <a name="remarks"></a>Hinweise  
 In der Regel müssen Sie nur diese Funktion in einer regulären MFC-DLL aufrufen. eine Anwendung wird automatisch aufrufen `AfxDaoTerm` Wenn es benötigt wird.  
  
 Rufen Sie in der regulären MFC-DLLs `AfxDaoTerm` vor der `ExitInstance` -Funktion, aber erst, nachdem alle MFC-DAO-Objekte zerstört wurden.  
  
 Weitere Informationen finden Sie unter [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  

### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  

## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
