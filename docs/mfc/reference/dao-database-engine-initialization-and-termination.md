---
title: DAO-Datenbank-Engine-Initialisierung und Beendigung | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.data
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
caps.latest.revision: 13
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b6119279234558998fad1f220239a29618c69cc5
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="dao-database-engine-initialization-and-termination"></a>Initialisieren und Beenden des DAO-Datenbankmoduls
Wenn Sie MFC-DAO-Objekte verwenden, muss zuerst die DAO-Datenbankmoduls werden initialisiert, und dann beendet vor dem Beenden der Anwendung oder DLL. Zwei Funktionen: `AfxDaoInit` und `AfxDaoTerm`, diese Aufgaben ausführen.  
  
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
 In den meisten Fällen müssen Sie nicht aufrufen `AfxDaoInit` da die Anwendung automatisch aufgerufen wird, wenn er benötigt wird.  
  
 Weitere Informationen und ein Beispiel für den Aufruf von `AfxDaoInit`, finden Sie unter [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  
  
##  <a name="afxdaoterm"></a>AfxDaoTerm  
 Diese Funktion beendet den DAO-Datenbankmoduls.  
  
```  
 
void AfxDaoTerm();  
```  
  
### <a name="remarks"></a>Hinweise  
 In der Regel müssen Sie nur zum Aufrufen dieser Funktion in einer regulären DLL. Ruft eine Anwendung automatisch `AfxDaoTerm` Wenn es benötigt wird.  
  
 In regulären DLLs aufrufen `AfxDaoTerm` vor der `ExitInstance` -Funktion, aber erst, nachdem alle MFC-DAO-Objekte zerstört wurden.  
  
 Weitere Informationen finden Sie unter [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  

### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  

## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

