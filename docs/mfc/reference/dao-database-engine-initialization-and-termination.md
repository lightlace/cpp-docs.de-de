---
title: DAO-Datenbank-Engine Initialisierungs- und Terminierungscode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros.data
dev_langs: C++
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 32dbcb02615f552a2bb26ec047b0b817bb828a95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="dao-database-engine-initialization-and-termination"></a>Initialisieren und Beenden des DAO-Datenbankmoduls
Verwendung von MFC-DAO-Objekten, muss zunächst die DAO-Datenbankmoduls werden initialisiert, und klicken Sie dann beendet, bevor Ihre Anwendung oder DLL beendet. Zwei Funktionen `AfxDaoInit` und `AfxDaoTerm`, diese Aufgaben ausführen.  
  
### <a name="dao-database-engine-initialization-and-termination"></a>Initialisieren und Beenden des DAO-Datenbankmoduls  
  
|||  
|-|-|  
|[AfxDaoInit](#afxdaoinit)|Initialisiert die DAO-Datenbankmoduls.|  
|[AfxDaoTerm](#afxdaoterm)|Beendet die DAO-Datenbankmoduls.|  
  
##  <a name="afxdaoinit"></a>AfxDaoInit  
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
  
##  <a name="afxdaoterm"></a>AfxDaoTerm  
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
